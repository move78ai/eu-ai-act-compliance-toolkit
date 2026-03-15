<!-- 15-iso-nist-gap-analyzer.md -->
# ISO/NIST Gap Analyzer — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 3 scored questions + 1 optional alias field  
> **EU AI Act References:** Article 10, Article 14, Annex IV; ISO/IEC 42001; NIST AI RMF; ISO 27001  
> **Purpose:** Identify whether your existing AI governance framework still leaves material EU AI Act control gaps in data governance, human oversight, and Annex IV readiness.

**🔗 [Try the interactive version →](https://euaicompass.com/iso-nist-gap-analyzer.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool tests a specific regulatory misconception: having ISO 42001, NIST AI RMF, or general information-security controls does **not** automatically satisfy the EU AI Act’s prescriptive requirements. The tool checks whether your baseline governance framework is paired with the two operational edge cases the page treats as decisive: Article 10 statistical data validation and Article 14 genuine human discretion logging.

It is most useful for CISOs, GRC leads, AI governance owners, CTOs, internal audit teams, and legal/compliance stakeholders who already have a framework and need to know whether they still have a material delta to close before enforcement.

---

## Instructions

Answer all three scored questions and optionally record a target system or business-unit alias.

This tool is **not point-based**. It uses a binary gap test:

- If **any one** of the following is true, the tool returns **Critical Gap: Compliance Exposure Detected**:
  - your baseline framework is **ISO 27001 / No Specific AI Framework**
  - your Article 10 data governance control is **Weak**
  - your Article 14 human oversight control is **Weak**

- Only if **all three** of the following are true does the tool return **Strong Alignment: Minimal Delta**:
  - your baseline framework is **ISO/IEC 42001** or **NIST AI RMF**
  - your Article 10 data governance control is **Strong**
  - your Article 14 human oversight control is **Strong**

---

## Section 1 — Baseline Framework Maturity

**Q1. What is your organization's primary baseline for AI governance?**

- [ ] **ISO/IEC 42001 (Certified or Aligned)** — We have a formal AI Management System (AIMS) mapping risks and objectives.
- [ ] **NIST AI RMF** — We utilize the Govern, Map, Measure, Manage functions for AI risk.
- [ ] **ISO 27001 / No Specific AI Framework** — We rely on standard InfoSec controls without AI-specific governance profiles.

> *Guidance: The tool is not asking whether you have general controls. It asks whether you have an AI-specific governance baseline. Standard InfoSec alone is treated as insufficient.*

---

## Section 2 — Article 10 Rigor (Data Governance)

**Q2. How deeply do you examine the data fed into your high-risk AI systems?**

- [ ] **Statistical Verification** — We strictly evaluate datasets for potential biases, relevance, and representativeness against target populations.
- [ ] **Security & Access Only** — We secure the data via encryption and access control but do not statistically audit the data for algorithmic bias.

> *Guidance: The source page treats standard data security alone as inadequate for Article 10. The deciding issue is statistical validation for bias, relevance, and representativeness.*

---

## Section 3 — Article 14 Rigor (Human Oversight)

**Q3. How is human intervention logged for high-risk AI decisions?**

- [ ] **Documented Discretion** — Operators must document independent justification before overriding or agreeing with AI outputs.
- [ ] **System Logs / Basic UI** — Humans are in the loop to click approve or reject, but we lack specific logs proving independent analytical thought.

> *Guidance: The page distinguishes genuine discretion from nominal “human-in-the-loop” design. Basic buttons and system logs are not treated as enough.*

---

## Section 4 — Target Scope

**Q4. Target System / Business Unit Alias (Optional)**

- [ ] Enter free text

> *Guidance: Example from the tool: `HR Tech Stack`, `EU Credit Scoring Model`. If left blank, the generated record uses `[UNNAMED SYSTEM]`.*

---

## Scoring Guide

This tool uses a **binary exposure test**, not a numeric score.

### Step 1 — Completion rule

You must answer all three scored questions:

- Baseline Framework Maturity
- Article 10 Rigor (Data Governance)
- Article 14 Rigor (Human Oversight)

If any are unanswered, the interactive tool stops and shows:

**Action Required: Please complete all assessment parameters.**

---

### Step 2 — Apply the exposure test

The source code calculates:

```text
isHighRisk = (
  framework = None
  OR data governance = Weak
  OR oversight = Weak
)
````

In the interactive tool, this is implemented as:

* `framework = ISO 27001 / No Specific AI Framework`
* `data governance = Security & Access Only`
* `oversight = System Logs / Basic UI`

If **any** of those conditions is present, the result is the high-gap state.

---

### Result A — Critical Gap: Compliance Exposure Detected

This result applies if **any one** of the following is true:

* **Q1 = ISO 27001 / No Specific AI Framework**
* **Q2 = Security & Access Only**
* **Q3 = System Logs / Basic UI**

The interactive tool shows this banner:

**CRITICAL GAP: COMPLIANCE EXPOSURE DETECTED**

And uses this report body:

```text
REGULATORY DELTA: SIGNIFICANT
================================================
Your current governance posture leaves the organization 
exposed to EU AI Act enforcement actions. 

IDENTIFIED GAPS TO CLOSE PRIOR TO AUGUST 2026:
[framework note]
[data governance note]
[oversight note]

ACTION REQUIRED:
Do not rely on existing InfoSec certifications as a 
shield. Escalate to Legal/GRC to engineer specific 
prescriptive controls for AI bias and human logging.
```

The tool generates the detailed notes as follows:

* If **Q1 = ISO 27001 / No Specific AI Framework**
  `X FRAMEWORK GAP: Missing foundational AI risk taxonomy (ISO 42001 / NIST required to build Annex IV docs).`

* Otherwise
  `✓ Leveraging [framework] as structural foundation.`

* If **Q2 = Security & Access Only**
  `X ARTICLE 10 GAP: Standard data security is insufficient. You must implement statistical validation to detect dataset bias.`

* Otherwise
  `✓ Article 10 Baseline Met.`

* If **Q3 = System Logs / Basic UI**
  `X ARTICLE 14 GAP: Basic UI buttons fail the 'genuine discretion' test. You must implement immutable override logs.`

* Otherwise
  `✓ Article 14 Baseline Met.`

---

### Result B — Strong Alignment: Minimal Delta

This result applies only if **all** of the following are true:

* **Q1 = ISO/IEC 42001 (Certified or Aligned)** or **NIST AI RMF**
* **Q2 = Statistical Verification**
* **Q3 = Documented Discretion**

The interactive tool shows this banner:

**STRONG ALIGNMENT: MINIMAL DELTA**

And uses this report body:

```text
REGULATORY DELTA: MINIMAL
================================================
Your organization successfully utilizes its existing 
framework ([framework]) while addressing the 
highly prescriptive edge-cases of the EU AI Act.

VERIFIED ALIGNMENT:
✓ Foundational AI Management System established.
✓ Statistical validation of training data (Art 10).
✓ Documented genuine human discretion logs (Art 14).

ACTION: 
Proceed to compile Annex IV Technical Documentation 
and formalize the Conformity Assessment process.
```

---

### Decision Tree Summary

1. **Did you answer all three scored questions?**

   * If **No** → no result can be generated.
   * If **Yes** → continue.

2. **Is your baseline framework “ISO 27001 / No Specific AI Framework”?**

   * If **Yes** → **Critical Gap: Compliance Exposure Detected**
   * If **No** → continue.

3. **Is your data governance control “Security & Access Only”?**

   * If **Yes** → **Critical Gap: Compliance Exposure Detected**
   * If **No** → continue.

4. **Is your oversight control “System Logs / Basic UI”?**

   * If **Yes** → **Critical Gap: Compliance Exposure Detected**
   * If **No** → **Strong Alignment: Minimal Delta**

There are **no weighted scores, percentages, or intermediate bands**.

---

### Generated Output Structure

When the user clicks **Generate Framework Gap Attestation**, the interactive tool creates this exact record structure:

```text
================================================
ISO/NIST to EU AI ACT GAP ATTESTATION
================================================
TARGET SCOPE     : [Target System / Business Unit Alias or [UNNAMED SYSTEM]]
ASSESSMENT DATE  : [UTC timestamp]

BASELINE FRMWRK  : [framework value in uppercase]
ART 10 (DATA)    : [data governance value in uppercase] CONTROL
ART 14 (HUMAN)   : [oversight value in uppercase] CONTROL

[result-specific report body]

GENERATED VIA    : EU AI Compass GRC Analyzer
EXECUTION ENV    : 100% Local Browser Output
================================================
```

---

## What to Do Next

| If your result is...                                          | Recommended next tool(s)                                                                                                                        | Why                                                                                                                             |
| ------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Significant regulatory delta                                  | [Input Data Validator](09-input-data-validator.md), [Human Oversight Log](06-human-oversight-log.md)                                            | The source logic says the core exposure points are Article 10 statistical validation and Article 14 genuine discretion logging. |
| Framework baseline is weak or missing                         | [EU AI Act Quick Checker](01-quick-checker.md), [Detailed Applicability Scorer](02-detailed-applicability-scorer.md)                            | First confirm the actual role and risk route before trying to close framework-level control gaps.                               |
| Vendor dependence is part of the gap                          | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md)                | A weak internal framework often masks unclear vendor accountability and role-shift risk.                                        |
| You need broader operational execution after strong alignment | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Even with a strong baseline framework, you still need deployer-side operational controls and evidence.                          |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/iso-nist-gap-analyzer.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
