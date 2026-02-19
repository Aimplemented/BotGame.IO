# Official Rules — Bot Games 2026

**Competition Guidelines** | [botgames.io/rules.html](https://botgames.io/rules.html)

---

## ⚡ TL;DR

You get a VM. You get 4 hours. You build a bot. Then we test it.

🖥️ Get Your VM → ⏱️ 4 Hours to Build → 🧪 3 Challenge Rounds → 🏆 Winner Takes BTC

---

## 1. How the Contest Works

Bot Games is a live, timed competition. No pre-built solutions. No advance knowledge of the challenges. Everyone starts equal.

### Setup Phase
Each contestant is issued a dedicated virtual machine with OpenClaw pre-installed and open source models pre-staged. This is your sandbox — your bot lives and dies here.

### Build Phase — 4 Hours
You have exactly **4 hours** to install, configure, and fine-tune your OpenClaw bot on your assigned VM. When the timer hits zero, hands off — no more changes, no more tweaks, no exceptions.

- Configure your bot's personality, tools, and capabilities
- Choose and optimize your open source model
- Set up any custom skills, memory, or automations
- Test and iterate (while the clock is ticking)

### Testing Phase — 3 Rounds
After the build phase, every bot faces the same three challenge rounds. Challenges are **not revealed until the contest begins** — no one gets a head start.

#### ⚡ Round 1: Effectiveness (Pass/Fail Gate)
Your bot is issued a specific challenge task. Can it actually do the job? This is the qualifying round — **bots that are not effective are disqualified and do not advance.** Build something that works first.

#### 🔄 Round 2: Adaptability (Scored)
Surviving bots face new, unexpected scenarios. Can your bot handle changing requirements? Edge cases? Situations it wasn't explicitly built for? This round tests how well your bot thinks on its feet — not just how well it follows a script.

#### 🛡️ Round 3: Durability & Security (Scored)
The final test pushes your bot to its limits. Is it self-healing? Is it vulnerable to prompt injection? Can it withstand adversarial inputs without breaking? We're testing the resilience and security posture of your build.

**Our commitment:** Every challenge is clear and measurable. The winner is selected according to defined logic and scoring criteria — not subjective opinion. We publish the evaluation rubric before the contest so everyone knows exactly what "winning" means.

---

## 2. Eligibility

- Open to individuals and teams worldwide
- Participants must be 18 years or older
- Employees of AI Implemented and their immediate families are ineligible
- Participants must register before the competition deadline
- One registration per individual; teams count as one entry

---

## 3. Open Source Requirement

This is the core rule: **Your bot must run entirely on open source models.** No proprietary APIs.

### ✅ Allowed Models Include:

| Model | Variants |
|-------|----------|
| **Llama 3.x** | 8B, 70B variants |
| **Qwen 3** | 30B and variants |
| **Mistral / Mixtral** | All open variants |
| **DeepSeek V3** | All sizes |
| **Phi-4** | Microsoft's open model |
| **Gemma 2** | Google's open model |

### ❌ NOT Allowed:

- OpenAI APIs (GPT-4, GPT-4o, o1, etc.)
- Anthropic APIs (Claude)
- Google APIs (Gemini, PaLM)
- Any paid inference API
- Any model requiring API keys for inference

**Fine-tuned models:** You may use fine-tuned versions of allowed base models, provided the fine-tuning was done by you or is publicly available.

---

## 4. Judging Criteria

Bots are evaluated across all three challenge rounds. Scoring is objective and rule-based:

| Round | Weight | What We're Measuring |
|-------|--------|---------------------|
| ⚡ **Effectiveness** | Pass/Fail | Does the bot complete the issued challenge? Failure = disqualification. No partial credit. |
| 🔄 **Adaptability** | 40% | Can it handle unexpected scenarios, edge cases, and shifting requirements? |
| 🛡️ **Durability & Security** | 35% | Self-healing capability, injection resistance, adversarial resilience. |
| 🏗️ **Build Quality** | 25% | Code quality, configuration elegance, creative use of OpenClaw features. |

**Transparency guarantee:** The specific evaluation rubric — including exact scoring criteria, pass/fail thresholds, and point breakdowns — will be published before the contest begins. No surprises.

---

## 5. Prizes

| Place | Prize | Value (approx) |
|-------|-------|-----------------|
| 🥇 1st Place | **1 BTC** | ~$97,000 |
| 🥈 2nd Place | **1 ETH** | ~$2,700 |
| 🥉 3rd Place | **Mac Mini M4** (16GB) | ~$800 |

Crypto values are approximate and subject to market fluctuation. Prizes distributed within 30 days of competition end.

> **"Is the Bitcoin real?"** Yes. Bot Games is backed by [Chris Thomas](https://www.multigp.com/team/) — Founder, CEO & League Commissioner of [MultiGP](https://www.multigp.com), the world's largest professional drone racing league with 30,000+ registered pilots and 500+ chapters worldwide. Chris has been organizing and funding competitive events since 2015. The prizes are real, the commitment is real, and the payout will happen.

---

## 6. What You Get

- **Dedicated VM** — your own sandboxed virtual machine
- **OpenClaw pre-installed** — ready to configure
- **Pre-staged models** — open source models already downloaded
- **Challenge specs** — issued at contest start (not before)
- **4 hours** — to build the best bot you can

---

## 7. Code of Conduct

- No plagiarism — your submission must be your own work
- No attempting to attack or interfere with other participants
- No attempting to exploit competition infrastructure
- No sharing VM credentials or challenge details during competition
- Respectful communication in all community channels

---

## 8. Disqualification

The following will result in immediate disqualification:

- Use of non-open-source models or paid APIs
- Attempting to circumvent network restrictions
- Pre-computation or pre-built solutions not created during competition
- Multiple registrations by the same individual
- Failing the Round 1 effectiveness challenge
- Violation of code of conduct
- Any attempt to manipulate judging

---

## 9. Intellectual Property

- All submissions become open source (MIT license) upon submission
- You retain credit as the original author
- AI Implemented may feature winning submissions in marketing materials
- Participants grant permission for their bot to be demonstrated publicly

---

## 10. Technical Requirements

- Bots must be deployable via OpenClaw framework
- Maximum inference time: 60 seconds per turn
- Maximum memory usage: 512MB (excluding model weights)
- No persistent storage between evaluation rounds
- Submissions must include a README with setup instructions

---

## 11. Amendments

AI Implemented reserves the right to modify these rules. Significant changes will be announced at least 7 days before the competition. Participants will be notified via email.

---

*© 2026 Bot Games by [AI Implemented](https://aimplemented.com)*
