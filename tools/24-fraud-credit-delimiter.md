<!-- 24-fraud-credit-delimiter.md -->
# Fraud vs Credit Scoring Delimiter — Self-Assessment

> **Time:** ~3 minutes · **Questions:** 3 scored questions + 1 architectural attestation + 1 optional system identifier  
> **EU AI Act References:** Annex III Area 5(b), Article 6(2), Article 6(3), Article 26  
> **Purpose:** Determine whether a financial AI pipeline remains within the fraud-detection exemption or has been contaminated into a high-risk credit-scoring architecture.

**🔗 [Try the interactive version →](https://euaicompass.com/fraud-credit-delimiter.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates a specific FinTech boundary problem: fraud-detection AI can sit outside the Annex III high-risk credit-scoring route, but that exemption becomes fragile if the model objective, data architecture, or downstream use drifts into creditworthiness logic. The source page frames this as a **pipeline contamination** problem and uses the “contaminated well” analogy to explain why blended fraud and credit pipelines can drag the whole system into the high-risk regime.

It is most useful for Chief Risk Officers, data architecture leads, compliance teams, CTOs, and legal counsel reviewing fraud, authentication, underwriting-adjacent, or transaction-risk systems. The interactive version also generates a downloadable/copyable **Architectural Segregation Assessment** record locally in the browser for internal governance and legal review.

---

## Instructions

Complete the optional system identifier, answer all three scored questions, and check the architectural attestation.

This tool is **score-based**. Each answer has a fixed value:

- **Algorithmic Objective Function** = 0, 10, or 34
- **Data Pipeline Architecture** = 0, 15, or 33
- **Output Application** = 0, 15, or 33

Add the three scores to produce a total out of **100**. Then apply the exact thresholds in the **Scoring Guide**.

---

## Section 1 — Pipeline Context

**Q1. System or Model Identifier**

- [ ] Enter free text  
  Example: `Transaction Authentication Engine v3`

> *Guidance: If left blank, the generated report uses `[UNNAMED SYSTEM]`.*

---

## Section 2 — Algorithmic Objective Function

**Q2. What is the primary mathematical objective of this specific model?**

- [ ] **Pure Identity Verification (Exempt)** — The model exclusively detects synthetic identities, account takeovers, or anomalous transaction velocity. **(34 points)**
- [ ] **Mixed Risk Scoring** — The model flags fraudulent behavior but simultaneously outputs a general "trust score" used by other departments. **(10 points)**
- [ ] **Propensity to Repay (High-Risk)** — The model analyzes financial history to predict the likelihood of default or late payment. **(0 points)**

> *Guidance: This is the first legal boundary test. The tool distinguishes pure fraud/authentication logic from mixed risk scoring and direct creditworthiness prediction. A model that predicts ability or willingness to repay is treated as the clearest high-risk path.*

---

## Section 3 — Data Pipeline Architecture

**Q3. How are the data inputs for this model physically or logically separated from credit underwriting data?**

- [ ] **Unified Data Lake (Critical Risk)** — Fraud algorithms and credit algorithms pull indiscriminately from the exact same unstructured data lake. **(0 points)**
- [ ] **Logically Tagged** — Data exists in the same repository but utilizes strict metadata tagging to restrict access to the fraud model. **(15 points)**
- [ ] **Strictly Segregated (Defensible)** — The fraud detection model operates in an isolated environment with dedicated, specific data ingestion feeds. **(33 points)**

> *Guidance: The tool treats black-box “same lake, different tags” separation as weaker than physical or architectural segregation. The strongest answer requires a distinct fraud environment with dedicated ingestion boundaries.*

---

## Section 4 — Output Application

**Q4. What happens immediately after the algorithm generates its output?**

- [ ] **Automated Credit Adjustment (Critical Risk)** — The output automatically modifies a customer's borrowing limit or adjusts their interest rate. **(0 points)**
- [ ] **Manual Underwriter Review** — The output is passed to a human credit officer as an advisory signal before they make a final lending decision. **(15 points)**
- [ ] **Binary Authentication (Defensible)** — The output strictly acts as a gatekeeper. It either allows the transaction to proceed or blocks it for suspected fraud. **(33 points)**

> *Guidance: This question tests what the model actually does in production. The strongest answer is a binary fraud-control gate. Once the output starts steering lending, pricing, or underwriting, the exemption becomes fragile or fails outright.*

---

## Section 5 — Architectural Attestation

**Q5. Architectural Attestation**

- [ ] I attest that the boundary definitions and pipeline logic for this system have been formally verified to ensure regulatory segregation.

> *Guidance: The interactive tool blocks output unless this attestation is checked. The page positions this as a governance accountability control for Data Architecture leadership.*

---

## Scoring Guide

### Step 1 — Completion rules

You must answer all three scored questions:

- Algorithmic Objective Function
- Data Pipeline Architecture
- Output Application

If any of the three is unanswered, the interactive tool stops and shows:

**Action Required: Please evaluate all three pipeline parameters.**

You must also check the architectural attestation.  
If not checked, the interactive tool stops and shows:

**Action Required: You must verify the architectural attestation before proceeding.**

---

### Step 2 — Calculate the score

Add the selected values:

```text
Final Score = Algorithmic Objective Function + Data Pipeline Architecture + Output Application
````

Possible values:

* Q2 = 34 / 10 / 0
* Q3 = 33 / 15 / 0
* Q4 = 33 / 15 / 0

Maximum score = **100**.---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `PIPELINE VERIFIED: DEFENSIBLE SEGREGATION`

**Report text used by the tool:**

```text
Architecture Status: Exempt / Defensible

This data architecture successfully isolates fraud detection from credit scoring processes.

Verified Strengths:
[PASS] The algorithmic objective is restricted purely to identity and anomaly verification.
[PASS] The environment enforces strict logical and physical data segregation.
[PASS] Output application is restricted to binary security authentication.

Next Steps:
This system maintains its exemption from Annex III classification. Retain this segregation memo locally to quickly defeat regulatory challenges regarding High-Risk overlap.
```

---

#### B. Score between 40 and 99

**Result:** `PIPELINE VULNERABLE: HIGH RISK OF CONTAMINATION`

The tool generates a warning list for each answer below the fully defensible threshold:

* If **Algorithmic Objective Function < 33** → `[WARN] Mixed risk scoring creates ambiguity regarding the model's legal classification.`
* If **Data Pipeline Architecture < 33** → `[WARN] Logical tagging within unified lakes is prone to access control degradation.`
* If **Output Application < 33** → `[WARN] Advisory signals sent to human underwriters may implicitly influence credit decisions.`

**Report text used by the tool:**

```text
Architecture Status: Conditional Warning

This pipeline contains structural overlaps that threaten to reclassify your exempt fraud systems into the High-Risk regulatory tier.

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Halt further integration. You must enforce harder physical boundaries between your fraud detection datasets and your underwriting datasets to protect your Annex III exemption.
```

---

#### C. Score below 40

**Result:** `PIPELINE INVALID: FULL HIGH-RISK EXPOSURE`

The tool generates a failure list only for answers scored **0**:

* If **Algorithmic Objective Function = 0** → `[FAIL] The model directly assesses propensity to repay, nullifying the fraud exemption.`
* If **Data Pipeline Architecture = 0** → `[FAIL] Unified data lakes permanently poison the regulatory boundary.`
* If **Output Application = 0** → `[FAIL] Automated credit adjustments trigger maximum Article 26 obligations.`

**Report text used by the tool:**

```text
Architecture Status: Failed / High-Risk Contamination

This architecture fails to segregate operations. Your fraud detection systems have been contaminated by credit scoring pipelines. 

Critical Compliance Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
Immediate action required. You must formally reclassify this entire unified pipeline as a High-Risk Annex III system. You are now legally obligated to comply with the entirety of Articles 8 through 15 before market deployment.
```---

### Decision Logic Summary

| Total Score | Result Band                                     | Meaning                                                                                                                              |
| ----------- | ----------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **100**     | Pipeline Verified: Defensible Segregation       | All three dimensions meet the tool’s fully defensible threshold.                                                                     |
| **40–99**   | Pipeline Vulnerable: High Risk of Contamination | The fraud pipeline still has structural overlaps that may collapse the exemption and pull it into a high-risk credit-scoring regime. |
| **0–39**    | Pipeline Invalid: Full High-Risk Exposure       | The tool treats the architecture as contaminated by credit-scoring logic or deployment.                                              |

### Exact Threshold Notes

The thresholds in the source code are:

* `score === 100` → defensible segregation
* `score >= 40` → high risk of contamination
* `score < 40` → full high-risk exposure

That means:

* A score of **40** is still **vulnerable**, not compliant.
* The only fully successful outcome is **100/100**.---

### Generated Output Structure

When all required fields are completed, the interactive tool generates this exact local record structure:

```text
Architectural Segregation Assessment
Assessment Date: [UTC timestamp]

System Identifier: [System or Model Identifier or [UNNAMED SYSTEM]]

Executive Attestation:
Data Architecture leadership formally attests that the boundary definitions and pipeline logic for this system have been evaluated to ensure regulatory segregation under Annex III.

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this implementation note below the output:

*This report analyzes architectural liability. Export this directly to your legal counsel to justify Annex III exemptions before a regulatory audit.*---

## What to Do Next

| If your result is...                                                     | Recommended next tool(s)                                                                                                                        | Why                                                                                                                |
| ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Pipeline vulnerable or invalid                                           | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Once the fraud exemption becomes fragile or collapses, you need the operational deployer-control view immediately. |
| The issue is mixed objectives or material steering of underwriting       | [Material Influence Evaluator](11-material-influence-evaluator.md), [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md)     | These tools help test whether the AI is merely preparatory or is materially driving regulated decisions.           |
| Vendor architecture or data-routing is part of the contamination problem | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [RAG Data Hygiene Screener](19-rag-data-hygiene-screener.md)                          | Weak segregation often sits inside third-party routing, shared repositories, or poor internal data hygiene.        |
| You need broader classification context for the financial use case       | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                            | Use these to place the financial pipeline back into the wider EU AI Act role and risk framework.                   |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/fraud-credit-delimiter.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

