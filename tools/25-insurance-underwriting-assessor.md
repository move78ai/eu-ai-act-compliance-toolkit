<!-- 25-insurance-underwriting-assessor.md -->
# Insurance Underwriting Assessor — Self-Assessment

> **Time:** ~3 minutes · **Questions:** 3 scored questions + 1 executive attestation + 1 optional system identifier  
> **EU AI Act References:** Annex III Area 5(c), Articles 10, 13, 14  
> **Purpose:** Assess whether a life or health insurance underwriting model is architected defensibly or exposes the organization to proxy-bias and high-risk AI liability.

**🔗 [Try the interactive version →](https://euaicompass.com/insurance-underwriting-assessor.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates life and health insurance pricing algorithms used for underwriting and risk assessment. The interactive tool frames these systems as high-risk under Annex III Area 5(c) and focuses on three operational pressure points: proxy bias in training data, whether pricing logic can be explained to consumers, and whether human underwriters retain direct intervention authority.

It is most useful for Chief Actuaries, Chief Compliance Officers, insurance risk committees, CTOs, and legal/compliance teams reviewing actuarial AI systems. The interactive version also generates a downloadable/copyable **Actuarial Defensibility Memo** locally in the browser for internal governance review.

---

## Instructions

Complete the optional model identifier, answer all three scored questions, and check the executive attestation.

This tool is **score-based**. Each answer has a fixed value:

- **Data Provenance and Proxy Auditing** = 0, 10, or 34
- **Algorithmic Explainability** = 0, 20, or 33
- **Underwriter Intervention Protocol** = 0, 15, or 33

Add the three scores to produce a total out of **100**. Then apply the exact thresholds in the **Scoring Guide**.

---

## Section 1 — Model Context

**Q1. Actuarial Model Identifier**

- [ ] Enter free text  
  Example: `Direct Life Underwriting Engine v4`

> *Guidance: If left blank, the generated report uses `[UNNAMED SYSTEM]`.*

---

## Section 2 — Data Provenance and Proxy Auditing

**Q2. Under Article 10, how does your organization vet the training data for discriminatory proxy variables?**

- [ ] **Unvetted Third-Party Aggregation (Critical Risk)** — The model ingests broad wellness app and lifestyle data without rigorous statistical analysis regarding demographic correlation. **(0 points)**
- [ ] **Restricted Data Inputs** — The model exclusively utilizes verified medical records, but we do not proactively audit those records for historical bias. **(10 points)**
- [ ] **Validated Clinical Framework (Defensible)** — All ingested data is strictly vetted. We conduct continuous statistical proxy audits to ensure lifestyle metrics do not penalize protected classes. **(34 points)**

> *Guidance: This question tests whether the underwriting model is protected against proxy discrimination. The source page explicitly warns that lifestyle, location, and behavioral data can act as hidden proxies for protected groups.*

---

## Section 3 — Algorithmic Explainability

**Q3. Can your underwriting team effectively explain a premium increase to the end consumer?**

- [ ] **Opaque Actuarial Output (Critical Risk)** — The model generates a strict numerical risk score. Underwriters cannot isolate the specific variables driving a premium hike. **(0 points)**
- [ ] **Technical Feature Importance** — The system provides complex mathematical weights to the actuary, but this logic is highly difficult to translate into plain language for the consumer. **(20 points)**
- [ ] **Deterministic Transparency (Defensible)** — The model utilizes deterministic logic. It generates explicit, plain-language justifications for every pricing adjustment. **(33 points)**

> *Guidance: The tool is not asking whether data scientists understand the model internally. It asks whether the organization can explain an individual premium outcome in plain language to the customer.*

---

## Section 4 — Underwriter Intervention Protocol

**Q4. Under Article 14, what is the required operational workflow before a policy is officially rejected?**

- [ ] **Automated Rejection (Critical Risk)** — The system automatically declines applications falling below the established risk threshold without human review. **(0 points)**
- [ ] **High-Friction Escalation** — Consumers can appeal automated rejections, but overturning the decision requires extensive senior committee review. **(15 points)**
- [ ] **Direct Underwriter Authority (Defensible)** — Human underwriters intercept every borderline decision. They possess immediate authority to adjust premiums and override the machine's assessment. **(33 points)**

> *Guidance: This question tests whether human intervention is real and low-friction. Appeal-only review is treated as materially weaker than direct underwriter authority before rejection is finalized.*

---

## Section 5 — Executive Attestation

**Q5. Executive Attestation**

- [ ] I attest that this actuarial model has been formally evaluated for demographic proxy bias in accordance with corporate risk policies.

> *Guidance: The interactive tool blocks output unless this attestation is checked. The source page positions this as governance accountability by the Chief Actuary / risk leadership.*

---

## Scoring Guide

### Step 1 — Completion rules

You must answer all three scored questions:

- Data Provenance and Proxy Auditing
- Algorithmic Explainability
- Underwriter Intervention Protocol

If any of the three is unanswered, the interactive tool stops and shows:

**Action Required: Please evaluate all three actuarial parameters.**

You must also check the executive attestation.  
If not checked, the interactive tool stops and shows:

**Action Required: You must verify the executive attestation before proceeding.**

---

### Step 2 — Calculate the score

Add the selected values:

```text
Final Score = Data Provenance and Proxy Auditing + Algorithmic Explainability + Underwriter Intervention Protocol
````

Possible values:

* Q2 = 0 / 10 / 34
* Q3 = 0 / 20 / 33
* Q4 = 0 / 15 / 33

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `ACTUARIAL WORKFLOW VERIFIED: DEFENSIBLE ARCHITECTURE`

**Report text used by the tool:**

```text
Evaluation Status: Highly Defensible

This life and health pricing model enforces robust Article 10 and Article 14 controls.

Verified Strengths:
[PASS] Ingested data is strictly vetted and audited for proxy discrimination.
[PASS] The pricing logic is deterministic and fully explainable to consumers.
[PASS] Human underwriters possess direct, low-friction override capabilities.

Next Steps:
Proceed with deployment. Retain this validation record locally to demonstrate proactive governance during market surveillance audits.
```

---

#### B. Score between 40 and 99

**Result:** `ACTUARIAL WORKFLOW VULNERABLE: HIGH RISK OF DISPARATE IMPACT`

The tool generates a warning list for each answer below the fully defensible threshold:

* If **Q2 < 34** → `[WARN] Failure to conduct statistical proxy audits exposes the firm to systemic discrimination charges.`
* If **Q3 < 33** → `[WARN] Relying solely on mathematical feature importance prevents legal teams from explaining premium hikes.`
* If **Q4 < 33** → `[WARN] High-friction escalation protocols severely undermine the Article 14 human oversight requirement.`

**Report text used by the tool:**

```text
Evaluation Status: Conditional Warning

This underwriting system possesses sufficient structural blind spots to unintentionally penalize protected demographics.

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Do not expand this deployment. You must institute proactive statistical disparity audits and lower the operational friction for underwriters overriding the AI logic.
```

---

#### C. Score below 40

**Result:** `ACTUARIAL WORKFLOW INVALID: CRITICAL COMPLIANCE FAILURE`

The tool generates a failure list only for answers scored **0**:

* If **Q2 = 0** → `[FAIL] Ingesting unvetted wellness data virtually guarantees the inclusion of illegal proxy variables.`
* If **Q3 = 0** → `[FAIL] Opaque Black Box logic prevents legal defensibility under Article 13.`
* If **Q4 = 0** → `[FAIL] Automated application rejection violates strict human-in-the-loop mandates.`

**Report text used by the tool:**

```text
Evaluation Status: Failed / Annex III Violation

This deployment functions as an uncontrolled, automated decision-maker regarding consumer health and financial access. You lack the mandatory technical capabilities to govern this process.

Critical Compliance Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
Halt usage of this tool immediately. Do not process live policy applications. You must re-architect the data baseline and establish a mandatory human review mechanism before resuming operations.
```

---

### Decision Logic Summary

| Total Score | Result Band                                                  | Meaning                                                                                                  |
| ----------- | ------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------- |
| **100**     | Actuarial Workflow Verified: Defensible Architecture         | All three controls meet the tool’s fully defensible threshold.                                           |
| **40–99**   | Actuarial Workflow Vulnerable: High Risk of Disparate Impact | The underwriting workflow still contains structural proxy-bias, explainability, or oversight weaknesses. |
| **0–39**    | Actuarial Workflow Invalid: Critical Compliance Failure      | The tool treats the deployment as non-defensible for live insurance underwriting use.                    |

### Exact Threshold Notes

The thresholds in the source code are:

* `score === 100` → defensible architecture
* `score >= 40` → vulnerable / high risk of disparate impact
* `score < 40` → critical compliance failure

That means:

* A score of **40** is still **vulnerable**, not compliant.
* The only fully successful outcome is **100/100**.

---

### Generated Output Structure

When all required fields are completed, the interactive tool generates this exact local record structure:

```text
Actuarial AI Compliance Validation Report
Assessment Date: [UTC timestamp]

System Identifier: [Actuarial Model Identifier or [UNNAMED SYSTEM]]

Executive Attestation:
The Chief Actuary formally attests that this pricing algorithm has been evaluated for demographic proxy bias and disparate impact in accordance with corporate risk policies.

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this implementation note below the output:

*This report analyzes critical High-Risk liability vectors. Export this directly to your Risk Committee to establish governance parameters prior to policy issuance.*

---

## What to Do Next

| If your result is...                                               | Recommended next tool(s)                                                                                                              | Why                                                                                                                                  |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Workflow vulnerable or invalid                                     | [Input Data Validator](09-input-data-validator.md), [Bias Testing Safe Harbor Protocol](20-bias-safe-harbor-protocol.md)              | These tools help tighten statistical validation, proxy-bias controls, and sensitive-data testing safeguards around actuarial models. |
| Human intervention and override authority are weak                 | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)            | These tools help prove whether underwriters actually exercise meaningful discretion instead of rubber-stamping model outcomes.       |
| Vendor model logic or data-routing is unclear                      | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Insurance AI exposure often sits inside third-party model opacity, data-retention risk, and missing deployer controls.               |
| You need broader classification context for the insurance use case | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                  | Use these to place the underwriting model back into the wider EU AI Act role and risk-classification framework.                      |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/insurance-underwriting-assessor.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

