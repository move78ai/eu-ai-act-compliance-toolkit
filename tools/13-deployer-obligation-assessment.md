<!-- 13-deployer-obligation-assessment.md -->
# Deployer Obligation Self-Assessment — Self-Assessment

> **Time:** ~10 minutes · **Questions:** 5  
> **EU AI Act References:** Articles 26(1), 26(2), 26(5), 26(6), 26(7)–26(11), 27, 72  
> **Purpose:** Map the deployer-specific obligations that remain with you even if your AI provider is compliant.

**🔗 [Try the interactive version →](https://euaicompass.com/deployer-obligation-assessment.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool measures deployer readiness against five independent legal duties that the page treats as non-transferable: using the system per provider instructions, assigning competent human oversight, monitoring and reporting serious incidents, retaining logs, and handling transparency plus FRIA-related duties. The source page is explicit: vendor compliance does **not** make the deployer compliant.

It is most useful for deployers, compliance leads, CTOs, CISOs, operations owners, and legal teams using high-risk AI systems. The interactive version also generates a downloadable/copyable **Deployer Obligation Assessment Record** locally in the browser for roadmap and audit use.

---

## Instructions

Answer all five questions by selecting **one option per question**.

Each answer has a fixed score:

- **0 points** = critical failure
- **10 points** = partial compliance
- **20 points** = compliant posture

Add the five scores to produce a total out of **100**. Then apply the exact thresholds in the **Scoring Guide**.

---

## Section 1 — Use Per Provider Instructions (Article 26(1))

**Q1. Do you operate your high-risk AI system in accordance with the provider's instructions for use?**

- [ ] **No Documentation (Critical)** — We have not received or reviewed provider instructions. Operators use the system based on informal training. **(0 points)**
- [ ] **Partial Compliance** — We have provider documentation but have not verified our actual usage aligns with the stated intended purpose. **(10 points)**
- [ ] **Verified Compliance** — We maintain auditable records confirming our use matches the provider's intended purpose and instructions. **(20 points)**

> *Guidance: This question is not asking whether the vendor has documentation somewhere. It asks whether your actual operational use is verified against those instructions.*

---

## Section 2 — Human Oversight (Article 26(2))

**Q2. Have you assigned human oversight to individuals who have the competence, training, and authority to fulfill that function?**

- [ ] **No Oversight (Critical)** — AI outputs are accepted automatically. No designated human overseer exists for high-risk decisions. **(0 points)**
- [ ] **Informal Oversight** — A person reviews outputs, but they lack formal training on the AI system's limitations and override authority is unclear. **(10 points)**
- [ ] **Structured Oversight (Compliant)** — Designated overseers are trained, have documented authority to override, and their interventions are logged. **(20 points)**

> *Guidance: The source tool is testing for named, trained, authorized oversight with logged intervention, not just casual human review.*

---

## Section 3 — Monitoring and Incident Reporting (Articles 26(5), 72)

**Q3. Do you monitor the AI system's operation and report serious incidents to the provider and relevant authorities?**

- [ ] **No Monitoring (Critical)** — We do not actively monitor the AI system post-deployment. No incident reporting process exists for AI-specific events. **(0 points)**
- [ ] **Generic IT Monitoring** — We use standard IT monitoring but have no AI-specific incident classification, escalation, or authority notification process. **(10 points)**
- [ ] **Active AI Monitoring (Compliant)** — We monitor for anomalies, have AI-specific incident codes, and maintain a documented process for notifying the provider and national authorities of serious incidents. **(20 points)**

> *Guidance: Generic IT monitoring is not treated as sufficient. The tool requires AI-specific monitoring and incident escalation logic.*

---

## Section 4 — Log Retention (Article 26(6))

**Q4. Do you retain AI-generated logs for at least six months under your direct control?**

- [ ] **No Retention (Critical)** — Logs are overwritten by vendor defaults (typically 30 days). We have no independent log retention. **(0 points)**
- [ ] **Vendor-Managed** — We rely on the vendor to retain logs but have not verified the retention period or our ability to access them for audits. **(10 points)**
- [ ] **Independent Retention (Compliant)** — We export and retain logs under our direct control for at least six months, accessible for regulatory audit. **(20 points)**

> *Guidance: The tool treats direct control over retention and audit access as the key requirement. Vendor-only retention is not enough.*

---

## Section 5 — Transparency and FRIA (Articles 26(7-11), 27)

**Q5. Have you completed a fundamental rights impact assessment (if required) and do you notify affected individuals and workers?**

- [ ] **No FRIA or Notification (Critical)** — We have not assessed fundamental rights impact. Workers and affected individuals are not informed about AI use in decisions affecting them. **(0 points)**
- [ ] **Partial Compliance** — We updated our GDPR privacy notice but have not completed a specific AI fundamental rights impact assessment or notified workers' representatives. **(10 points)**
- [ ] **Full Compliance** — FRIA completed (where required), workers' representatives notified, and individuals informed when AI decisions affect them. **(20 points)**

> *Guidance: The page distinguishes AI-specific FRIA and worker/individual notification from generic privacy notice updates.*

---

## Scoring Guide

### Step 1 — Completion rule

You must answer all five questions.

If any question is unanswered, the interactive tool stops and shows:

**Please answer all five questions.**

---

### Step 2 — Calculate the score

Add the selected values:

- **Q1 Use Per Provider Instructions** = 0, 10, or 20
- **Q2 Human Oversight** = 0, 10, or 20
- **Q3 Monitoring and Incident Reporting** = 0, 10, or 20
- **Q4 Log Retention** = 0, 10, or 20
- **Q5 Transparency and FRIA** = 0, 10, or 20

**Formula:**

```text
Final Score = Q1 + Q2 + Q3 + Q4 + Q5
````

Maximum score = **100**

---

### Step 3 — Determine FAIL and PASS items

The interactive tool builds two lists from the individual question scores:

* A question becomes **[FAIL]** if its score is **less than 20**
* A question becomes **[PASS]** if its score is **exactly 20**

The exact labels used by the tool are:

* **Art 26(1) Use Per Instructions**
* **Art 26(2) Human Oversight**
* **Art 26(5)/72 Monitoring & Incidents**
* **Art 26(6) Log Retention**
* **Art 26(7-11)/27 Transparency & FRIA**

---

### Step 4 — Interpret the result band

#### A. Score = 100

**Result:** `SCORE 100/100: DEPLOYER OBLIGATIONS MET`

**Report text used by the tool:**

```text
Your organization demonstrates compliant deployer operations.

Verified:
[PASS] Art 26(1) Use Per Instructions
[PASS] Art 26(2) Human Oversight
[PASS] Art 26(5)/72 Monitoring & Incidents
[PASS] Art 26(6) Log Retention
[PASS] Art 26(7-11)/27 Transparency & FRIA

Next: Ensure evidence is centralized and audit-ready. Maintain continuous monitoring.
```

---

#### B. Score between 50 and 99

**Result:** `SCORE [score]/100: DEPLOYER GAPS DETECTED`

**Report text used by the tool:**

```text
Your organization has partial deployer compliance but critical gaps remain.

Gaps Detected:
[FAIL] ... (all questions with score < 20)

Passes:
[PASS] ... (all questions with score = 20)

Priority: Address each [FAIL] item. These represent independent legal obligations that your AI provider cannot fulfill on your behalf.
```

---

#### C. Score below 50

**Result:** `SCORE [score]/100: CRITICAL DEPLOYER LIABILITY`

**Report text used by the tool:**

```text
Your organization lacks the mandatory deployer governance structures required by law.

Critical Gaps:
[FAIL] ... (all questions with score < 20)

Immediate Action Required: Your vendor's compliance does NOT cover these obligations. You face direct regulatory liability as a deployer. Establish independent oversight, logging, monitoring, and notification processes before enforcement begins.
```

---

### Decision Logic Summary

| Total Score | Result Band                 | Meaning                                                                                 |
| ----------- | --------------------------- | --------------------------------------------------------------------------------------- |
| **100**     | Deployer Obligations Met    | All five deployer duties are at the compliant level.                                    |
| **50–99**   | Deployer Gaps Detected      | Some deployer obligations are met, but one or more independent duties remain deficient. |
| **0–49**    | Critical Deployer Liability | Foundational deployer controls are missing, creating direct regulatory exposure.        |

### Exact Threshold Notes

The thresholds in the source code are:

* `total === 100` → **Deployer Obligations Met**
* `total >= 50` → **Deployer Gaps Detected**
* `total < 50` → **Critical Deployer Liability**

That means:

* A score of **50** still counts as **gaps detected**, not failure.
* The only fully successful result is **100/100**.

---

### Generated Output Structure

When all five answers are completed, the interactive tool generates this exact local record structure:

```text
EU AI Act Deployer Obligation Assessment
Date: [UTC timestamp]
Score: [score] / 100

[Result-specific report body]

Generated via EU AI Compass
Execution: Local Browser (Zero Cloud Sync)
```

---

## What to Do Next

| If your result is...                                                     | Recommended next tool(s)                                                                                                                     | Why                                                                                                                             |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Human oversight and intervention are weak                                | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)                   | These tools convert a weak oversight score into concrete evidence and test whether humans are actually exercising real control. |
| Monitoring, incident handling, and log retention are weak                | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Input Data Validator](09-input-data-validator.md)                       | These tools go deeper into operational execution under Article 26 and help close monitoring, logging, and input-control gaps.   |
| Transparency, FRIA, or affected-person notification are weak             | [Local FRIA Generator](08-local-fria-generator.md), [Article 50 Transparency Validator](12-article-50-transparency-validator.md)             | Use these to structure FRIA records and tighten user/worker-facing transparency controls.                                       |
| You need to confirm broader classification, role, or applicability first | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md) | Deployer obligations only make sense once the role and applicability posture are correctly classified.                          |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/deployer-obligation-assessment.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

