<!-- 07-article-26-operations-scorer.md -->
# Article 26 Operations Scorer — Self-Assessment

> **Time:** ~3 minutes · **Questions:** 4  
> **EU AI Act References:** Article 26(2), Article 26(4), Article 26(5), Article 26(6), Article 26(7), Article 26(11)  
> **Purpose:** Grade your operational readiness against the heaviest execution burdens in Article 26 for AI deployers.

**🔗 [Try the interactive version →](https://euaicompass.com/article-26-operations-scorer.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool measures whether your organization has implemented the operational controls the interactive tool treats as the hardest parts of Article 26 execution: human oversight logging, incident reporting, input-data validation, worker/individual transparency, and six-month log retention. It is built as a fast local diagnostic for deployers who need to identify immediate execution gaps before an audit or internal remediation program.

It is most useful for CISOs, compliance leads, AI governance owners, operational risk teams, and deployers of high-risk AI systems. The interactive version also generates a copyable **Article 26 Operational Diagnostic Report** in the browser for internal use.

---

## Instructions

Answer all four diagnostic questions by selecting **one option per question**.

Each answer has a fixed point value:

- **0 points** = critical-risk posture
- **10 points** = partially structured / incomplete posture
- **25 points** = compliant posture

Add the four scores to produce a total out of **100**. Then apply the result thresholds in the **Scoring Guide** exactly as written.

---

## Section A — Oversight and Event Monitoring (Article 26(2), Article 26(5))

**Q1. How does your organization handle Article 26(2) Human Oversight and Article 26(5) Incident Reporting?**

- [ ] **Ad-Hoc (Critical Risk)** — We rely on standard IT ticketing. There are no specific AI incident codes or dedicated human oversight logs. **(0 points)**
- [ ] **Partially Structured** — We have AI policies, but operator overrides are just tracked as standard UI clicks without independent justification. **(10 points)**
- [ ] **Fully Logged (Compliant)** — We maintain immutable oversight ledgers and immediate authority notification channels for AI incidents. **(25 points)**

> *Guidance: This question tests whether oversight and incident handling are operationalized as AI-specific controls rather than buried inside generic IT workflows.*

---

## Section B — Data Input Validation (Article 26(4))

**Q2. How does your organization satisfy Article 26(4) regarding the relevance of input data?**

- [ ] **Open Input (Critical Risk)** — Operators can feed any data into the AI system. We do not assess the data for relevance to the intended purpose. **(0 points)**
- [ ] **Basic Access Controls** — We restrict who can use the system, but we do not statistically audit the data they choose to upload. **(10 points)**
- [ ] **Strict Validation (Compliant)** — Input data is formally assessed to ensure it is sufficiently representative for the intended system output. **(25 points)**

> *Guidance: This question is not about generic access control alone. It asks whether you assess whether the data being fed into the system is actually relevant and representative for the AI use case.*

---

## Section C — Transparency and Labor Rights (Article 26(7), Article 26(11))

**Q3. How do you execute Article 26(7) Worker Notification and Article 26(11) Individual Transparency?**

- [ ] **Silent Deployment (Critical Risk)** — We deploy AI tools internally without formally notifying the workers' representatives or affected external parties. **(0 points)**
- [ ] **General Privacy Policy** — We updated our general GDPR privacy policy. We lack specific AI exposure notifications for impacted employees. **(10 points)**
- [ ] **Active Notification (Compliant)** — We maintain explicit worker notification logs and clearly inform individuals when they interact with an AI system. **(25 points)**

> *Guidance: This question tests whether AI-specific exposure and interaction notices exist in practice, not whether a general privacy notice exists somewhere in policy documents.*

---

## Section D — Log Retention and Traceability (Article 26(6))

**Q4. How does your organization satisfy the Article 26(6) mandate to retain automatically generated AI logs for at least six months?**

- [ ] **Vendor Default (Critical Risk)** — Logs are frequently overwritten. We rely on 30-day SaaS vendor defaults. They are not retained under our direct control. **(0 points)**
- [ ] **Unsecured Local Storage** — Logs are kept but are easily editable. We lack specific retention lifecycle enforcement policies. **(10 points)**
- [ ] **6-Month Immutable Retention (Compliant)** — We enforce strict, unalterable local log retention for a minimum of six months across all High-Risk systems. **(25 points)**

> *Guidance: The tool is looking for controlled retention under your direct governance, not short vendor defaults or editable local files.*

---

## Scoring Guide

### Step 1 — Completion rule

You must answer all four questions.

If any question is unanswered, the interactive tool stops and shows:

**Action Required: Please answer all four diagnostic questions.**

---

### Step 2 — Calculate the score

Add the selected values:

- **Q1 Oversight and Event Monitoring** = 0, 10, or 25
- **Q2 Data Input Validation** = 0, 10, or 25
- **Q3 Transparency and Labor Rights** = 0, 10, or 25
- **Q4 Log Retention and Traceability** = 0, 10, or 25

**Formula:**

```text
Final Score = Q1 + Q2 + Q3 + Q4
````

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `SCORE 100/100: OPERATIONAL EXCELLENCE`

**Report text used by the tool:**

```text
Your organization demonstrates a mature execution of Article 26.

Verified Strengths:
[PASS] Article 26(2) & 26(5): Active logging and incident reporting.
[PASS] Article 26(4): Statistical input validation enforced.
[PASS] Article 26(7) & 26(11): Transparency and worker rights respected.
[PASS] Article 26(6): Mandatory 6-month log retention secured.

Next Steps:
Ensure these logs are centralized and cryptographically secured locally to prove immutability to an auditor.
```

---

#### B. Score between 50 and 99

**Result:** `SCORE [score]/100: SIGNIFICANT EXECUTION GAPS`

The tool builds a list of failures for every answer scoring **less than 25**:

* If **Q1 < 25** → `[FAIL] Article 26(2) Human Oversight Logging`
* If **Q2 < 25** → `[FAIL] Article 26(4) Input Data Validation`
* If **Q3 < 25** → `[FAIL] Article 26(7) Worker Notification`
* If **Q4 < 25** → `[FAIL] Article 26(6) 6-Month Log Retention`

**Report text used by the tool:**

```text
Your organization relies on generic IT processes that fail the specific legal tests of the EU AI Act.

Critical Execution Gaps Detected:
[FAIL] ... (all failed items listed here)

Resolution Strategy:
You cannot manage these distinct paragraphs via spreadsheets or generic SaaS. You require a dedicated, localized compliance protocol. 

RECOMMENDATION: Immediately operationalize these missing workflows. Establish an immutable, local tracking system to enforce mandatory logging without exposing data to the cloud.
```

---

#### C. Score below 50

**Result:** `SCORE [score]/100: CRITICAL LIABILITY EXPOSURE`

The tool builds the same failure list for every answer scoring **less than 25**:

* If **Q1 < 25** → `[FAIL] Article 26(2) Human Oversight Logging`
* If **Q2 < 25** → `[FAIL] Article 26(4) Input Data Validation`
* If **Q3 < 25** → `[FAIL] Article 26(7) Worker Notification`
* If **Q4 < 25** → `[FAIL] Article 26(6) 6-Month Log Retention`

**Report text used by the tool:**

```text
Your organization operates AI systems without the mandatory governance structures required by law.

Critical Execution Gaps Detected:
[FAIL] ... (all failed items listed here)

Resolution Strategy:
Your current posture presents maximum regulatory liability. You lack the foundational bricks to survive an audit. 

RECOMMENDATION: Halt new high-risk AI deployments. Instantly establish a centralized, zero-cloud governance protocol to force operational logging at the endpoint level.
```

---

### Decision Logic Summary

| Total Score | Result Band                 | Meaning                                                                        |
| ----------- | --------------------------- | ------------------------------------------------------------------------------ |
| **100**     | Operational Excellence      | All four controls are at the compliant level.                                  |
| **50–99**   | Significant Execution Gaps  | One or more Article 26 operational controls are incomplete.                    |
| **0–49**    | Critical Liability Exposure | The organization lacks foundational operational controls required by the tool. |

---

### Generated Output Structure

When all four answers are completed, the interactive tool generates a local report in this structure:

```text
Article 26 Operational Diagnostic Report
Assessment Date: [UTC timestamp]
Final Score: [score] / 100

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

---

## What to Do Next

| If your result is...                                           | Recommended next tool(s)                                                                                                                                | Why                                                                                                                          |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Critical liability exposure in oversight and incident handling | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)                              | These tools help operationalize genuine human review and test whether current human controls are real or cosmetic.           |
| Input-data relevance and data quality are weak                 | [Input Data Validator](09-input-data-validator.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md)                         | Use these to tighten operational checks around Article 26(4) and connect them to broader deployer duties.                    |
| Transparency and worker-notification controls are weak         | [Article 50 Transparency Validator](12-article-50-transparency-validator.md), [AI Content Marking Compliance Checker](14-ai-content-marking-checker.md) | These tools help validate notice, disclosure, and communication controls where AI affects workers or end users.              |
| You need a broader classification and prioritization view      | [EU AI Act Quick Checker](01-quick-checker.md), [Detailed Applicability Scorer](02-detailed-applicability-scorer.md)                                    | Use these to confirm whether the system is in a high-risk route and where Article 26 remediation should sit in your roadmap. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/article-26-operations-scorer.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
