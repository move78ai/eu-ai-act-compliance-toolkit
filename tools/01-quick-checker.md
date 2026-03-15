<!-- 01-quick-checker.md -->
# EU AI Act Quick Checker — Self-Assessment

> **Time:** ~5 minutes · **Questions:** 12  
> **EU AI Act References:** Articles 2, 3, 4, 5, 6(1), 6(2), 6(3), 9–15, 27, 43, 49, 50(1), 50(3), 50(4), 53, 55, 57–63, 99; Annex I; Annex III; Chapter V  
> **Purpose:** Fast triage of likely role, risk classification, core obligations, and deadline path under the EU AI Act.

**🔗 [Try the interactive version →](https://euaicompass.com/checker.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool gives you a fast first-pass assessment of your likely role, risk classification, and core obligations under the EU AI Act in 12 questions. It is designed as a triage tool before moving into the more detailed applicability scorer.

It is most useful for founders, product owners, CTOs, CISOs, compliance leads, procurement teams, and in-house legal teams who need an initial answer on whether they are dealing with prohibited practices, high-risk AI, GPAI obligations, transparency obligations, or a likely minimal-risk case.

---

## Instructions

Answer each question by selecting **one option**, except where the tool explicitly says **Select all that apply**.

Use the **Scoring Guide** exactly in the order shown. This tool does **not** use points. It uses a rule-based decision flow. The **first matching rule** determines the headline classification.

For **Q4**, **“None of the above”** is exclusive and should not be selected together with any other option.

---

## Section A — Scope

**Q1. Where is your organization established?**

- [ ] Within the EU/EEA
- [ ] Outside the EU/EEA

> *Guidance: Determines whether the EU AI Act applies directly. A non-EU organization may still be in scope if its AI system is placed on the EU market or its output is used in the EU.*

---

## Section B — Your Role (Article 3)

**Q2. What is your relationship to the AI system?**

- [ ] We develop/commission and market the AI system under our name
- [ ] We use/deploy an AI system under our authority (bought or licensed it)
- [ ] We import AI systems into the EU from outside
- [ ] We make AI systems available on the EU market
- [ ] We develop/distribute a general-purpose AI model (LLM/foundation model)
- [ ] Not sure

> *Guidance: The Act assigns different obligations to different roles. The interactive tool maps these to Provider, Deployer, Importer, Distributor, GPAI Provider, or an undetermined role pending other answers.*

---

## Section C — EU Nexus (Article 2)

**Q3. Does your AI system connect to the EU market?**

- [ ] Placed on the EU market or put into service in the EU
- [ ] Outside the EU, but the AI output is used within the EU
- [ ] No connection to the EU market
- [ ] Not sure

> *Guidance: The Act has extraterritorial reach. A non-EU organization can still be in scope if the AI output is used in the EU.*

---

## Section D — Prohibited Practices (Article 5)

**Q4. Does your AI system do any of the following?**  
**Select all that apply.**

- [ ] Social scoring by/for public authorities
- [ ] Subliminal or manipulative techniques to distort behavior
- [ ] Exploits vulnerabilities (age, disability, socio-economic)
- [ ] Untargeted scraping of facial images from internet/CCTV
- [ ] Emotion recognition in workplaces or schools (non-medical)
- [ ] Biometric categorization inferring sensitive attributes
- [ ] Criminal risk prediction solely from profiling
- [ ] Real-time remote biometric ID in public spaces (non-exempt)
- [ ] None of the above

> *Guidance: The tool treats these as prohibited-practice indicators and states they are banned since 2 February 2025. “None of the above” is exclusive.*

---

## Section E — Product Safety (Article 6(1), Annex I)

**Q5. Is your AI system a safety component of a product under EU harmonized legislation?**

- [ ] Yes — embedded in a regulated product
- [ ] No — standalone software/service
- [ ] Not sure

> *Guidance: The tool lists Annex I examples as medical devices, machinery, toys, vehicles, lifts, pressure equipment, radio equipment, marine equipment, and rail. If yes, the tool routes the system to the Annex I high-risk path.*

---

## Section F — High-Risk Use Cases (Article 6(2), Annex III)

**Q6. Does your system fall into any Annex III area?**

- [ ] Biometric identification, verification, or categorization
- [ ] Critical infrastructure (energy, water, transport, digital)
- [ ] Education — admissions, grading, assessment, monitoring
- [ ] Employment — recruitment, screening, performance, allocation
- [ ] Essential services — credit scoring, benefits, insurance, emergency
- [ ] Law enforcement — risk assessment, profiling, evidence
- [ ] Migration & border control
- [ ] Justice & democracy — legal research, sentencing
- [ ] None of the above

> *Guidance: This question maps the system against the 8 high-risk use-case categories used by the interactive tool.*

---

## Section G — Exceptions (Article 6(3))

**Q7. Does your system meet any high-risk exception?**

- [ ] Performs a narrow procedural task only
- [ ] Improves the result of a completed human activity only
- [ ] Detects decision patterns without replacing human judgment
- [ ] Performs a preparatory task for a human assessment only
- [ ] None apply — or it profiles individuals (always high-risk)
- [ ] Not sure

> *Guidance: The tool applies these only where the system is within Annex III. If none apply, or if you are unsure, the tool takes the conservative high-risk path.*

---

## Section H — GPAI (Chapter V)

**Q8. Is your system based on a General-Purpose AI model?**

- [ ] Yes — model trained with >10²⁵ FLOPs (systemic risk)
- [ ] Yes — standard GPAI model
- [ ] No — purpose-built or rule-based system
- [ ] Not sure

> *Guidance: The tool defines GPAI using examples such as GPT-4, Claude, Gemini, Llama, and Mistral. If systemic-risk GPAI is selected, additional Article 55 obligations are added.*

---

## Section I — Transparency (Article 50)

**Q9. Does your AI interact with people or generate content?**

- [ ] Chatbot, virtual assistant, or conversational AI
- [ ] Generates/manipulates images, audio, or video
- [ ] Performs emotion recognition or biometric categorization
- [ ] Generates text on matters of public interest
- [ ] Backend system, no direct user/public interaction

> *Guidance: This routes to Article 50 transparency obligations where applicable. Backend systems with no direct user or public interaction are treated as potentially outside Article 50 in the tool logic.*

---

## Section J — Organization (Articles 57–63)

**Q10. What is the size of your organization?**

- [ ] Startup — under 5 years, fewer than 250 employees
- [ ] SME — fewer than 250 employees
- [ ] Enterprise — 250+ employees
- [ ] Public authority or government body

> *Guidance: This does not change the core classification, but it affects support messaging and, for public authorities or government bodies, may add a FRIA obligation in the high-risk path.*

---

## Section K — Readiness

**Q11. Where are you on your compliance journey?**

- [ ] Haven’t started — just learning
- [ ] Assessing which systems are in scope
- [ ] Identified systems, planning measures
- [ ] Actively implementing

> *Guidance: The tool says this helps calibrate recommendations. It does not change the headline classification in the current logic.*

---

## Section L — Priority

**Q12. Your biggest compliance concern?**

- [ ] Understanding if our systems are high-risk
- [ ] Technical documentation and record-keeping
- [ ] Risk management and human oversight
- [ ] Cost and resources for compliance
- [ ] Meeting enforcement deadlines

> *Guidance: This changes the concern-specific advisory text shown at the end of the assessment. It does not change the headline classification.*

---

## Scoring Guide

This tool uses a **rule-based decision tree**, not a point score. Apply the logic below **in order**.

### Step 1 — Determine the role label

Use **Q2** to assign the role shown in the final summary:

- **Provider** → “We develop/commission and market the AI system under our name”
- **Deployer** → “We use/deploy an AI system under our authority (bought or licensed it)”
- **Importer** → “We import AI systems into the EU from outside”
- **Distributor** → “We make AI systems available on the EU market”
- **GPAI Model Provider** → “We develop/distribute a general-purpose AI model (LLM/foundation model)”
- **Undetermined** → “Not sure”

---

### Step 2 — Determine the scope note

Apply the scope note separately from the classification:

- If **Q1 = Outside the EU/EEA** and **Q3 = No connection to the EU market** →  
  **Scope note:** *No EU nexus identified. The Act likely does not apply.*

- If **Q3 = Outside the EU, but the AI output is used within the EU** →  
  **Scope note:** *Extraterritorial scope — AI output used in the EU (Article 2(1)(c)).*

- If **Q1 = Within the EU/EEA** →  
  **Scope note:** *EU-established entity — Act applies directly.*

The tool treats the assessment as **in scope** unless both of the following are true:

- **Q1 = Outside the EU/EEA**, and
- **Q3 = No connection to the EU market**

---

### Step 3 — Determine the headline classification

Apply these rules in order. The **first matching rule** wins.

#### Rule 1 — Prohibited
If **Q4** includes **any option other than “None of the above”**, the result is:

**PROHIBITED**

---

#### Rule 2 — Likely out of scope
If the system is **not in scope** based on Step 2, the result is:

**LIKELY OUT OF SCOPE**

---

#### Rule 3 — High-risk (Annex I Product)
If **Q5 = Yes — embedded in a regulated product**, the result is:

**HIGH-RISK (Annex I Product)**

---

#### Rule 4 — High-risk (Annex III)
If **Q6** is any Annex III category other than **None of the above**, and **Q7** is:

- **None apply — or it profiles individuals (always high-risk)**, or
- **Not sure**

the result is:

**HIGH-RISK (Annex III)**

---

#### Rule 5 — Potential exemption
If **Q6** is any Annex III category other than **None of the above**, and **Q7** is one of the exception options:

- Performs a narrow procedural task only
- Improves the result of a completed human activity only
- Detects decision patterns without replacing human judgment
- Performs a preparatory task for a human assessment only

the result is:

**POTENTIALLY EXEMPT — Verify Exceptions**

---

#### Rule 6 — GPAI obligations
If any of the following is true:

- **Q2 = We develop/distribute a general-purpose AI model (LLM/foundation model)**
- **Q8 = Yes — model trained with >10²⁵ FLOPs (systemic risk)**
- **Q8 = Yes — standard GPAI model**

the result is:

**GPAI OBLIGATIONS**

---

#### Rule 7 — Transparency obligations
If **Q9** is any option other than **Backend system, no direct user/public interaction**, the result is:

**TRANSPARENCY OBLIGATIONS**

---

#### Rule 8 — Minimal risk
If none of the above rules apply, the result is:

**MINIMAL RISK**

---

### Step 4 — Add obligations exactly as the tool does

The interactive tool builds obligations cumulatively.

#### A. In-scope baseline obligation
If the system is **in scope**, always add:

- **Art. 4** — Ensure AI literacy for staff interacting with AI — **Now**

---

#### B. Prohibited-practice obligations
If the result is **PROHIBITED**, add:

- **Art. 5** — Immediately cease prohibited AI practices — **IMMEDIATE**
- **Art. 99** — Penalty exposure: up to €35M or 7% global turnover — **IMMEDIATE**

The tool also displays a prohibited-practice warning box listing the selected prohibited indicators from Q4.

---

#### C. High-risk obligations
If the result contains **HIGH-RISK**, add:

- **Art. 9** — Establish risk management system — **By deadline**
- **Art. 10** — Implement data governance practices — **By deadline**
- **Art. 11** — Create technical documentation — **By deadline**
- **Art. 12** — Design for automatic logging/record-keeping — **By deadline**
- **Art. 13** — Ensure transparency to deployers — **By deadline**
- **Art. 14** — Design for human oversight — **By deadline**
- **Art. 15** — Ensure accuracy, robustness, cybersecurity — **By deadline**
- **Art. 43** — Complete conformity assessment — **Before market**
- **Art. 49** — Register in EU high-risk AI database — **Before market**

Add this further obligation if either of the following is true:

- **Q2 = Deployer**, or
- **Q10 = Public authority or government body**

Then add:

- **Art. 27** — Conduct fundamental rights impact assessment (FRIA) — **Before deployment**

---

#### D. GPAI obligations
If the result contains **GPAI**, or **Q8** is **standard GPAI** or **systemic-risk GPAI**, add:

- **Art. 53** — Maintain technical documentation for GPAI model — **Since Aug 2025**
- **Art. 53** — Provide info to downstream providers — **Since Aug 2025**
- **Art. 53** — Comply with copyright (text/data mining opt-out) — **Since Aug 2025**
- **Art. 53** — Publish training data summary — **Since Aug 2025**

If **Q8 = systemic-risk GPAI**, also add:

- **Art. 55** — Model evaluations + adversarial testing — **Since Aug 2025**
- **Art. 55** — Track/report serious incidents — **Since Aug 2025**
- **Art. 55** — Ensure model + infrastructure cybersecurity — **Since Aug 2025**

---

#### E. Transparency obligations
If **Q9 = Chatbot, virtual assistant, or conversational AI**, add:

- **Art. 50(1)** — Inform users they are interacting with AI — **By Aug 2026 (Omnibus proposes grace to Feb 2027 for pre-existing content)**

If **Q9 = Generates/manipulates images, audio, or video**, add:

- **Art. 50(4)** — Label AI-generated/manipulated content — **By Aug 2026 (Omnibus proposes grace to Feb 2027 for pre-existing content)**

If **Q9 = Performs emotion recognition or biometric categorization**, add:

- **Art. 50(3)** — Inform persons of emotion recognition/biometric function — **By Aug 2026 (Omnibus proposes grace to Feb 2027 for pre-existing content)**

If **Q9 = Generates text on matters of public interest**, add:

- **Art. 50(4)** — Label AI-generated text on public interest matters — **By Aug 2026 (Omnibus proposes grace to Feb 2027 for pre-existing content)**

---

### Step 5 — Determine the key deadline

Apply the same deadline logic used by the interactive tool:

- If the result is **PROHIBITED** →  
  **Key Deadline:** **NOW**  
  **Tool note:** *Prohibited practices banned since 2 February 2025.*

- Else if the result contains **GPAI** →  
  **Key Deadline:** **Already in effect**  
  **Tool note:** *GPAI obligations apply since 2 August 2025.*

- Else if **Q5 = Yes — embedded in a regulated product** →  
  **Key Deadline:** **2 August 2027**  
  **Tool note:** *Annex I product systems — final transition.*

- Else if the result contains **HIGH-RISK** →  
  **Key Deadline:** **2 August 2026**  
  **Tool note:** *Annex III enforcement starts. Digital Omnibus proposes fixed extension to Dec 2, 2027 (not yet adopted).*

- Else →  
  **Key Deadline:** **2 August 2026**  
  **Tool note:** *General application date.*

---

### Step 6 — Apply SME/startup support note

If **Q10 = SME** or **Q10 = Startup**, add the support note used by the interactive tool:

- **SME** → reduced conformity assessment fees, dedicated guidance, and tailored support
- **Startup** → priority sandbox access, reduced conformity assessment fees, dedicated guidance, and tailored support

The tool attributes this support note to **Articles 57–63**.

---

### Step 7 — Concern-specific advisory shown by the interactive tool

The final screen also adds an advisory box based on **Q12**:

- **Understanding if our systems are high-risk** →  
  *Start with a portfolio classification using our E0 scorecard — free download at store.move78int.com.*

- **Technical documentation and record-keeping** →  
  *Our E1 toolkit ($299) includes structured templates for Articles 11-12 documentation.*

- **Risk management and human oversight** →  
  *Articles 9 and 14 require documented risk management and human oversight. Our E2 toolkit provides NIST AI RMF crosswalks.*

- **Cost and resources for compliance** →  
  *Estimated initial compliance: €200K-€500K for high-risk. Our toolkits reduce cost through structured frameworks starting at $299.*

- **Meeting enforcement deadlines** →  
  *Key dates: Aug 2, 2026 (Annex III enforcement), Aug 2, 2027 (Annex I products). Digital Omnibus proposes fixed shift to Dec 2, 2027 (not yet law).*

---

## What to Do Next

| If your result is... | Next tool | Why |
|---|---|---|
| You need deeper classification after this quick triage | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md) | The interactive tool itself directs users to the detailed scorer as the next step for one system or a portfolio. |
| You landed in a potential exemption path under Article 6(3) | [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md) | Use it to test whether your Annex III case is genuinely exempt or still high-risk. |
| You are a deployer, public authority, or operational owner of a high-risk system | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Move from triage into deployer-specific duties, oversight controls, and FRIA-related actions. |
| Your result includes Article 50 transparency duties | [Article 50 Transparency Validator](12-article-50-transparency-validator.md) | Validate the exact disclosure and labelling requirements triggered by your system design or user interaction model. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/checker.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*