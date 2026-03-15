<!-- 11-material-influence-evaluator.md -->
# Material Influence Evaluator — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 3 scored questions + 1 legal attestation  
> **EU AI Act References:** Article 6(3), Annex III  
> **Purpose:** Test whether an Annex III deployment is genuinely exempt from high-risk classification or whether the system materially influences the final decision.

**🔗 [Try the interactive version →](https://euaicompass.com/material-influence-evaluator.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates whether an Annex III deployment can credibly rely on the Article 6(3) exemption by testing three operational criteria: procedural narrowness, whether the AI replaces human assessment, and whether the AI materially influences the final outcome. The source page states that the core legal test is **material influence** and warns that a vendor’s upstream exemption claim is not a sufficient legal defense for the deployer.

It is most useful for legal counsel, compliance leads, CTOs, product owners, and deployers who need to document an internal exemption justification before relying on an Annex III opt-out. The interactive version also generates a downloadable/copyable **Article 6(3) Self-Assessment Record** for local retention.

---

## Instructions

Complete the **System Context** field, answer all three material-influence questions, and check the legal counsel attestation.

This tool is **score-based**. Each answer has a fixed value. Add the three scores:

- **Procedural Narrowness:** 0, 15, or 34
- **Baseline Assessment Replacement:** 0, 15, or 33
- **Material Influence Execution:** 0, 15, or 33

Maximum score = **100**

Then apply the exact thresholds in the **Scoring Guide**.

---

## System Context

**Q1. System Identifier**

- [ ] Enter free text

> *Guidance: Example from the interactive tool: `Candidate Document Parser v1`. If left blank, the generated record uses `[UNNAMED SYSTEM]`.*

---

## Section 1 — Procedural Narrowness

**Q2. Is the AI system intended to perform a narrow procedural task?**

- [ ] **Broad Analytical Scope (Critical Risk)** — The system evaluates holistic profiles, predicts future performance, or synthesizes complex variables to generate new insights. **(0 points)**
- [ ] **Conditional Formatting** — The system organizes data based on dynamic rules but does not generate new analytical conclusions. **(15 points)**
- [ ] **Strictly Procedural (Defensible)** — The system merely extracts data, translates text, or executes basic sorting functions without evaluating the underlying merit of the data. **(34 points)**

> *Guidance: This question tests whether the system is narrowly procedural or whether it has drifted into broader evaluative analysis. The tool treats broad analytical scope as a direct exemption failure risk.*

---

## Section 2 — Baseline Assessment Replacement

**Q3. Does the system detect patterns or deviations without replacing the human assessment?**

- [ ] **Replaces Human Assessment (Critical Risk)** — The algorithm executes the primary evaluation. Humans only review the output if an appeal is formally initiated. **(0 points)**
- [ ] **Parallel Assessment** — The AI and the human conduct simultaneous evaluations, but the AI score is prominently displayed to the human operator. **(15 points)**
- [ ] **Preparatory Flagging Only (Defensible)** — The system strictly highlights potential anomalies in large datasets to direct human attention. The human executes the entire substantive review. **(33 points)**

> *Guidance: This question tests whether the AI is merely preparatory or whether it has become the substantive assessor. Parallel scoring is treated as a warning state because it can still steer the reviewer.*

---

## Section 3 — Material Influence Execution

**Q4. Does the system materially influence the final outcome of the decision?**

- [ ] **Direct Material Influence (Critical Risk)** — The algorithm generates a score or ranking that heavily dictates the final decision. Overriding the system requires justification. **(0 points)**
- [ ] **Secondary Influence** — The system provides supplementary data points that the human operator factors into their broader decision matrix. **(15 points)**
- [ ] **Zero Decision Influence (Defensible)** — The system performs backend tasks. It merely improves the result of a previously completed human activity without altering the substantive outcome. **(33 points)**

> *Guidance: This is the decisive legal test in the tool. If the algorithm meaningfully steers the outcome, the exemption becomes vulnerable or fails outright.*

---

## Section 4 — Legal Counsel Attestation

**Q5. Legal Counsel Attestation**

- [ ] I attest that the operational reality of this system has been evaluated by Legal Counsel and accurately reflects the exemption parameters defined in Article 6(3).

> *Guidance: The interactive tool blocks output generation unless this attestation is checked. The page positions this as the formal internal documentation step needed to support an exemption claim.*

---

## Scoring Guide

### Step 1 — Completion rules

You must answer all three scored questions:

- **Procedural Narrowness**
- **Baseline Assessment Replacement**
- **Material Influence Execution**

If any of the three is unanswered, the interactive tool stops and shows:

**Action Required: Please evaluate all three material influence parameters.**

You must also check the legal counsel attestation.  
If not checked, the interactive tool stops and shows:

**Action Required: You must verify the Legal Counsel attestation before proceeding.**

---

### Step 2 — Calculate the score

Add the three selected values:

```text
Final Score = Procedural Narrowness + Baseline Assessment Replacement + Material Influence Execution
````

Possible values:

* Q2 = 0 / 15 / 34
* Q3 = 0 / 15 / 33
* Q4 = 0 / 15 / 33

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `EXEMPTION VALIDATED: DEFENSIBLE JUSTIFICATION`

**Report text used by the tool:**

```text
Legal Evaluation Status: Exemption Justified

This system meets the strict criteria for an Article 6(3) exemption from High-Risk obligations.

Verified Parameters:
[PASS] The system is constrained to a narrow procedural task.
[PASS] The system performs preparatory flagging without replacing substantive human assessment.
[PASS] The system executes zero material influence on the final outcome of the decision.

Next Steps:
The exemption is legally defensible. Retain this self-assessment record locally to present to Market Surveillance Authorities upon request.
```

---

#### B. Score between 40 and 99

**Result:** `EXEMPTION VULNERABLE: BORDERLINE MATERIAL INFLUENCE`

The tool generates a warning list for each answer that is below the fully defensible threshold:

* If **Q2 < 34** → `[WARN] Dynamic rule formatting risks expanding beyond 'narrow procedural tasks'.`
* If **Q3 < 33** → `[WARN] Parallel AI scoring creates psychological automation bias, threatening human assessment authority.`
* If **Q4 < 33** → `[WARN] Providing secondary influence data challenges the 'zero material influence' threshold.`

**Report text used by the tool:**

```text
Legal Evaluation Status: Conditional Warning

This system's operational design sits on the border of material influence. Claiming an exemption carries significant regulatory risk.

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Do not rely on the vendor's upstream exemption claim. You must restrict the operational boundaries of this system to prevent the algorithmic output from steering human decisions.
```

---

#### C. Score below 40

**Result:** `EXEMPTION INVALID: FULL HIGH-RISK OBLIGATIONS APPLY`

The tool generates a failure list only for answers scored **0**:

* If **Q2 = 0** → `[FAIL] Broad analytical scope completely nullifies the 'procedural task' exemption.`
* If **Q3 = 0** → `[FAIL] Replacing human assessment automatically triggers High-Risk classification.`
* If **Q4 = 0** → `[FAIL] Executing direct material influence constitutes a failure of the Article 6(3) test.`

**Report text used by the tool:**

```text
Legal Evaluation Status: Failed / Exemption Void

This deployment executes clear material influence over human outcomes. Any attempt to claim an Article 6(3) exemption is legally invalid.

Critical Exemption Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
Immediate action required. You must formally classify this system as High-Risk under Annex III. You are legally obligated to comply with the entirety of Articles 8 through 15 and Article 26 Deployer duties.
```

---

### Decision Logic Summary

| Total Score | Result Band                                         | Meaning                                                                                                 |
| ----------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **100**     | Exemption Validated: Defensible Justification       | All three conditions meet the tool’s fully defensible threshold.                                        |
| **40–99**   | Exemption Vulnerable: Borderline Material Influence | The system may still influence outcomes or weaken human authority, making the exemption risky to claim. |
| **0–39**    | Exemption Invalid: Full High-Risk Obligations Apply | The tool treats the deployment as failing the Article 6(3) test.                                        |

### Exact Threshold Notes

The thresholds in the source code are:

* `score === 100` → exemption validated
* `score >= 40` → exemption vulnerable
* `score < 40` → exemption invalid

That means:

* A score of **40** is still **vulnerable**, not valid.
* The only fully successful outcome is **100/100**.

---

### Generated Output Structure

When all required fields are completed, the interactive tool generates this exact local record structure:

```text
Article 6(3) Self-Assessment Record
Assessment Date: [UTC timestamp]

System Identifier: [System Identifier or [UNNAMED SYSTEM]]

Executive Attestation:
Corporate Legal Counsel formally attests that the operational reality of this system has been evaluated and accurately reflects the exemption parameters defined in Article 6(3).

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The page also includes this retention instruction below the output:

*This record establishes your internal legal defense. Retain this document locally to justify your Annex III exemption during Market Surveillance Authority audits.*

---

## What to Do Next

| If your result is...                                                      | Recommended next tool(s)                                                                                                                    | Why                                                                                                                                                     |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Exemption invalid or borderline                                           | [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md) | First confirm whether any exemption path remains available at all. If not, move immediately into deployer operational controls for a high-risk posture. |
| Human review appears weak or overly influenced by the system              | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)                  | These tools help prove whether the human is actually making the substantive judgment or merely ratifying the machine.                                   |
| Vendor claims the system is exempt but your operational use is different  | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md)            | The source page explicitly warns that deployers cannot blindly rely on upstream vendor exemption claims.                                                |
| You need broader applicability confirmation beyond the exemption question | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                        | Use these to place the system back into the wider EU AI Act context and confirm whether other obligations are triggered.                                |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/material-influence-evaluator.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
