<!-- 09-input-data-validator.md -->
# Input Data Validator — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 5  
> **EU AI Act References:** Article 26(4), Article 10  
> **Purpose:** Validate whether the input dataset for an AI execution is relevant and representative enough to support a defensible Article 26(4) operator record.

**🔗 [Try the interactive version →](https://euaicompass.com/input-data-validator.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool checks whether the dataset you are about to feed into an AI system is both relevant to the intended purpose and sufficiently representative for the expected output. It is designed as an operator-side control before batch execution or large-file uploads into a high-risk or compliance-sensitive AI workflow.

It is most useful for AI operators, data stewards, compliance teams, risk owners, and line managers supervising operational AI usage. The interactive version also generates a downloadable/copyable **Input Data Validation Record** for your internal ticket or compliance ledger.

---

## Instructions

Complete the system and dataset context fields, then assess:

- whether the data is relevant to the intended purpose of the AI model,
- whether the dataset is representative rather than skewed or unverified, and
- whether the operator is willing to attest to that review.

Record your answers, then use the **Scoring Guide** to determine whether execution is blocked, conditionally allowed with mitigation, or cleared.

---

## Section A — System and Dataset Context

**Q1. Target AI System**

- [ ] Enter free text

> *Guidance: Example from the interactive tool: `HR Candidate Screening Model v2`. If left blank, the generated record uses `[UNNAMED SYSTEM]`.*

**Q2. Input Data Description**

- [ ] Enter free text

> *Guidance: Example from the interactive tool: `Batch of 500 applicant resumes exported from the Q3 marketing campaign.` If left blank, the generated record uses `[NO DESCRIPTION PROVIDED]`.*

---

## Section B — Data Relevance Assessment (Article 26(4))

**Q3. Does this data directly relate to the strict intended purpose of the AI model as defined by the vendor?**

- [ ] **Directly Relevant** — The dataset matches the exact parameters the AI was trained to evaluate.
- [ ] **Tangentially Relevant** — The data contains some useful variables, but also includes extraneous data fields the model may misinterpret.
- [ ] **Irrelevant / Unverified** — The data is being fed into the system experimentally to see what outputs it produces.

> *Guidance: This is the tool’s direct relevance test. “Tangentially Relevant” is not treated as a full failure, but it does trigger a conditional warning rather than full approval.*

---

## Section C — Data Representativeness Assessment (Article 26(4), Article 10)

**Q4. Is the data skewed? Have you verified that it accurately represents the target demographic without excluding vulnerable groups?**

- [ ] **Statistically Representative** — The dataset has been checked to ensure fair distribution across relevant demographic variables.
- [ ] **Potential Skew** — The data leans heavily toward a specific demographic. It requires manual weighting or contextual adjustment.
- [ ] **Unknown / Unverified** — The data distribution has not been formally evaluated prior to this execution.

> *Guidance: The tool is not asking whether the file is merely large or complete. It asks whether the distribution has actually been checked for representativeness and bias risk.*

---

## Section D — Operator Attestation

**Q5. Operator Attestation**

- [ ] I attest that I have evaluated this input data for relevance and representativeness prior to execution.

> *Guidance: The tool treats this as a mandatory accountability check. Without it, no validation record can be generated.*

---

## Scoring Guide

This tool uses a **rule-based traffic-light logic**, not a point score.

### Step 1 — Mandatory completion rules

You must answer both of the following:

- **Q3 Data Relevance Assessment**
- **Q4 Data Representativeness Assessment**

If either is missing, the interactive tool stops and shows:

**Action Required: Please evaluate both the relevance and representativeness parameters.**

You must also check the operator attestation in **Q5**.  
If not checked, the interactive tool stops and shows:

**Action Required: You must check the operator attestation box to verify accountability.**

---

### Step 2 — Apply the decision logic

#### Rule 1 — Execution Blocked: Critical Compliance Risk

If either of the following is true:

- **Q3 = Irrelevant / Unverified**
- **Q4 = Unknown / Unverified**

then the result is:

**EXECUTION BLOCKED: CRITICAL COMPLIANCE RISK**

**Report body used by the interactive tool:**

```text
Verification Status: Failed

We strongly advise against executing this data processing job. The input dataset violates Article 26(4) baseline requirements.

Critical Flags Detected:
The data is either irrelevant to the intended purpose or its demographic distribution is entirely unverified. Proceeding creates immediate liability for discriminatory outcomes.

Required Action: 
Halt execution. Return the dataset to the analytics team for formal statistical auditing and cleaning.
````

---

#### Rule 2 — Conditional Approval: Mitigation Required

If Rule 1 does not apply, but either of the following is true:

* **Q3 = Tangentially Relevant**
* **Q4 = Potential Skew**

then the result is:

**CONDITIONAL APPROVAL: MITIGATION REQUIRED**

**Report body used by the interactive tool:**

```text
Verification Status: Conditional Warning

This dataset presents a heightened risk of generating biased outputs or hallucinated correlations. 

Operational Warning:
The data contains known skews or extraneous variables. 

Required Action: 
Execution may proceed ONLY IF the downstream Human Oversight operators are specifically notified of the dataset skew. They must apply strict scrutiny to the AI outputs generated from this specific batch.
```

---

#### Rule 3 — Dataset Cleared: Article 26(4) Satisfied

If both of the following are true:

* **Q3 = Directly Relevant**
* **Q4 = Statistically Representative**

then the result is:

**DATASET CLEARED: ARTICLE 26(4) SATISFIED**

**Report body used by the interactive tool:**

```text
Verification Status: Approved

This dataset meets the legal burden for relevance and representativeness under deployer obligations.

Verified Alignment:
The operator has confirmed the data maps precisely to the intended purpose of the AI model. The distribution has been verified as statistically representative.

Required Action: 
Cleared for execution. Retain this log locally alongside the batch output results.
```

---

### Decision Tree Summary

Apply the logic in this order:

1. **Did you answer Q3 and Q4, and check the attestation box?**

   * If **No** → no record can be generated.
   * If **Yes** → continue.

2. **Is Q3 = Irrelevant / Unverified OR Q4 = Unknown / Unverified?**

   * If **Yes** → **Execution Blocked: Critical Compliance Risk**
   * If **No** → continue.

3. **Is Q3 = Tangentially Relevant OR Q4 = Potential Skew?**

   * If **Yes** → **Conditional Approval: Mitigation Required**
   * If **No** → continue.

4. **Otherwise**

   * **Dataset Cleared: Article 26(4) Satisfied**

There are **no weighted scores, percentages, or threshold bands**.

---

### Field-to-Record Mapping Used by the Interactive Tool

The interactive tool converts the raw answers into these exact record labels:

**Relevance Check**

* `Direct` → `Directly Relevant`
* `Tangent` → `Tangentially Relevant (Extraneous Variables Present)`
* `Irrelevant` → `Irrelevant / Experimental`

**Representativeness Check**

* `Representative` → `Statistically Representative`
* `Skewed` → `Potential Skew / Demographic Bias Detected`
* `Unknown` → `Unknown / Unverified Distribution`

---

### Generated Output Structure

When validation succeeds, the interactive tool generates this exact record format:

```text
Input Data Validation Record (Article 26.4)
(Record Generated Locally)

System Identifier: [Target AI System or [UNNAMED SYSTEM]]
Assessment Date: [UTC timestamp]

Dataset Description:
[Input Data Description or [NO DESCRIPTION PROVIDED]]

Evaluation Parameters
Relevance Check: [Mapped relevance label]
Representativeness Check: [Mapped representativeness label]

Operator Attestation:
The operator formally attests they have evaluated this input data for relevance and representativeness prior to execution, in accordance with organizational AI governance policies.

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this operational reminder below the record:

*Action Required: Attach this record to the associated data processing job ticket to maintain your 6-month compliance ledger.*

---

## What to Do Next

| If your result is...                                                          | Recommended next tool(s)                                                                                                                          | Why                                                                                                                                                        |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Execution blocked because relevance or distribution is unverified             | [Bias Testing Safe Harbor Protocol](20-bias-safe-harbor-protocol.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | You need a stronger evidence base for dataset quality, bias controls, and operator-side accountability before execution resumes.                           |
| Conditional approval because the data is skewed or only tangentially relevant | [Human Oversight Log](06-human-oversight-log.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md)                              | The interactive tool explicitly requires stricter downstream human review and stronger operational controls when skew or extraneous variables are present. |
| Dataset cleared but you need broader governance assurance                     | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [ISO/NIST Gap Analyzer](15-iso-nist-gap-analyzer.md)                                    | A clean dataset record does not prove the wider system, vendor, or governance model is adequate.                                                           |
| You are still unsure whether the system itself is in a high-risk route        | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                              | Validate the overall AI use case before relying on an operational data-control record in isolation.                                                        |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/input-data-validator.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
