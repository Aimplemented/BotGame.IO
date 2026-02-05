# Bot Games Security Architecture

**Principle:** Submissions are DATA until explicitly sandboxed. No code execution on receipt.

---

## Submission Flow

```
[Contestant] → [Upload API] → [Cold Storage] → [Human Review] → [Sandbox] → [Execute]
                    ↓
              Static files only
              No eval, no import
              No network callbacks
```

### 1. Upload API (botgames.io/api/submit)
- Accepts: ZIP file + metadata JSON
- **MAX SIZE:** 50MB
- **NO EXECUTION** - Files written to disk as-is
- Virus scan on upload (ClamAV)
- Store with random UUID, not user-supplied filename

### 2. Cold Storage
- Location: `/var/botgames/submissions/{uuid}/`
- **No execute permissions** (`chmod -x` everything)
- Filesystem: `noexec` mount option
- Isolated from web root
- Append-only until review

### 3. Human Review Gate
- **MANDATORY** before any execution
- Checklist:
  - [ ] No obfuscated code
  - [ ] Dependencies on allowlist
  - [ ] No network calls in bot logic
  - [ ] No filesystem access outside sandbox
  - [ ] No subprocess/shell execution
- Review happens via read-only web viewer (no local clone)

### 4. Sandbox Execution (Proxmox)
- **One LXC container per bot**
- Resource limits:
  - CPU: 1 core
  - RAM: 512MB
  - Disk: 1GB
  - Time: 60 seconds max per turn
- Network: **NONE** (air-gapped)
- No persistent storage between runs
- Container destroyed after match

### 5. Execution Environment
- Base image: Minimal Debian + Python 3.11 + allowed packages only
- **Allowlisted packages:**
  - numpy, pandas (data)
  - No requests, urllib, socket
  - No subprocess, os.system, eval, exec
- Stdout/stderr captured, sanitized before display

---

## Threat Mitigations

| Threat | Mitigation |
|--------|------------|
| Code execution on upload | No eval, noexec mount, files are inert data |
| Sandbox escape | Proxmox LXC isolation, no network, minimal attack surface |
| Resource exhaustion | Hard limits (CPU/RAM/time), container killed on exceed |
| Prompt injection in descriptions | No AI reads raw submissions; human review only |
| Malicious dependencies | Package allowlist, no pip install at runtime |
| Data exfiltration | No network in sandbox, no persistent storage |
| XSS on leaderboard | All display data escaped/sanitized |
| Path traversal | UUID naming, no user-controlled paths |

---

## Package Allowlist (v1)

```
numpy>=1.24
pandas>=2.0
```

That's it for v1. Expand conservatively with human approval.

---

## Monitoring

- All submissions logged with timestamp, IP, size
- Failed sandbox attempts logged and alerted
- Container resource usage tracked
- Anomaly detection on repeated failures from same source

---

## Emergency Procedures

**If sandbox breach suspected:**
1. Kill all bot containers immediately
2. Snapshot Proxmox node for forensics
3. Disable submission API
4. Notify team in Discord #botgames
5. Post-mortem before re-enabling

---

*Security-First Launch Principle: This architecture must be implemented and tested before accepting ANY submissions.*
