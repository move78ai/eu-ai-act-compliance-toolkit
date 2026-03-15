<!-- 23-promo-termination-validator.md -->
# Promotion & Termination Validator — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 3 scored questions + 1 executive attestation + 1 optional system identifier  
> **EU AI Act References:** Annex III Area 4, Article 13, Article 14  
> **Purpose:** Assess whether an AI-driven performance management, promotion, or termination workflow is legally defensible or structurally exposed to labor litigation and EU AI Act failure.

**🔗 [Try the interactive version →](https://euaicompass.com/promo-termination-validator.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates AI systems used to influence employee promotion, compensation, task allocation, performance management, or termination decisions. The source page is explicit that firing or denying promotion through an unvalidated algorithm creates severe litigation and regulatory risk, and that explainability plus binding human oversight are non-negotiable.

It is most useful for CHROs, HR operations leaders, legal counsel, compliance teams, CTOs, and enterprise risk owners reviewing employment-related AI systems. The interactive version also generates a downloadable/copyable **Algorithmic Labor Action Assessment** locally in the browser for internal legal review.

---

## Instructions

Complete the optional system identifier, answer all three scored questions, and check the executive attestation.

This tool is **score-based**. Each answer has a fixed value:

- **System Scope** = 0, 10, or 20
- **Algorithmic Explainability** = 0, 20, or 40
- **Intervention Protocol** = 0, 15, or 40

Add the three scores to produce a total out of **100**. Then apply the exact thresholds in the **Scoring Guide**.

---

## Section 1 — System Context

**Q1. Performance System Identifier**

- [ ] Enter free text  
  Example: `Q4 Performance Analytics Engine`

> *Guidance: If left blank, the generated report uses `[UNNAMED SYSTEM]`.*

---

## Section 2 — System Scope

**Q2. What specific employment action does this algorithm directly influence?**

- [ ] **Termination or Layoff Flagging (Highest Risk)** — The system identifies bottom performers or flags individuals for potential dismissal. **(0 points)**
- [ ] **Promotion and Compensation** — The system ranks employees to dictate bonuses, raises, or career advancement. **(10 points)**
- [ ] **Task and Shift Allocation** — The system purely assigns daily workloads or schedules without directly penalizing staff. **(20 points)**

> *Guidance: The source page treats systems influencing dismissal or layoff decisions as the highest-risk use case. Task and shift allocation is still sensitive, but scored as the lowest-risk option within this tool.*

---

## Section 3 — Algorithmic Explainability (Article 13)

**Q3. Can HR and Legal articulate exactly why the system generated a specific score for an employee?**

- [ ] **Opaque Black Box (Critical Risk)** — The underlying logic is highly complex. We cannot isolate the specific variables that triggered the negative score. **(0 points)**
- [ ] **Partially Transparent** — The vendor provides general feature importance, but individual scores remain difficult to justify in an employment tribunal. **(20 points)**
- [ ] **Fully Explainable Logic (Defensible)** — The system outputs clear, interpretable rationale for every decision. HR can easily explain the precise metrics to the employee. **(40 points)**

> *Guidance: This question tests whether HR and Legal can defend a specific adverse outcome to the affected employee or tribunal. General model summaries are not treated as enough if individual score logic remains opaque.*

---

## Section 4 — Intervention Protocol (Article 14)

**Q4. What is the mandatory operational workflow before an algorithmic penalty is executed?**

- [ ] **Automated Execution (Critical Risk)** — The system automatically initiates performance improvement plans (PIPs) or issues warnings based on the score. **(0 points)**
- [ ] **Rubber Stamp Review** — A manager clicks approve on the generated list. There is no structural incentive to challenge the machine's output. **(15 points)**
- [ ] **Mandatory Committee Override (Defensible)** — Every flagged action requires an independent review by a human committee possessing the authority to completely reverse the AI recommendation. **(40 points)**

> *Guidance: The source logic requires more than nominal human review. A single approval click is treated as weak oversight; a committee with real reversal authority is treated as the defensible model.*

---

## Section 5 — Executive Attestation

**Q5. Executive Attestation**

- [ ] I attest that the transparency controls and human intervention protocols for this performance management system have been formally reviewed by Legal Counsel.

> *Guidance: The interactive tool blocks output unless this attestation is checked. The source page frames this as explicit governance accountability from HR leadership.*

---

## Scoring Guide

### Step 1 — Completion rules

You must answer all three scored questions:

- System Scope
- Algorithmic Explainability
- Intervention Protocol

If any of the three is unanswered, the interactive tool stops and shows:

**Action Required: Please evaluate all three systemic parameters.**

You must also check the executive attestation.  
If not checked, the interactive tool stops and shows:

**Action Required: You must verify the executive attestation before proceeding.**

---

### Step 2 — Calculate the score

Add the selected values:

```text
Final Score = System Scope + Algorithmic Explainability + Intervention Protocol
````

Possible values:

* Q2 = 0 / 10 / 20
* Q3 = 0 / 20 / 40
* Q4 = 0 / 15 / 40

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score >= 80

**Result:** `HR WORKFLOW VERIFIED: DEFENSIBLE ARCHITECTURE`

**Report text used by the tool:**

```text
Evaluation Status: Highly Defensible

This performance management deployment enforces robust Article 13 and Article 14 controls.

Verified Strengths:
[PASS] The algorithmic logic is fully explainable to affected employees.
[PASS] Mandatory human committee oversight prevents automated adverse actions.
[PASS] The system operates within defined, legally reviewed boundaries.

Next Steps:
Proceed with deployment. Retain this validation record locally to demonstrate proactive HR governance during labor disputes or market surveillance audits.
```

---

#### B. Score between 35 and 79

**Result:** `HR WORKFLOW VULNERABLE: HIGH RISK OF LABOR LITIGATION`

The tool generates a warning list for each answer below the higher-defensibility threshold:

* If **System Scope < 20** → `[WARN] Utilizing AI for termination/promotion drastically escalates litigation exposure.`
* If **Algorithmic Explainability < 40** → `[WARN] Partial transparency prevents HR from adequately explaining negative performance scores to staff.`
* If **Intervention Protocol < 40** → `[WARN] Rubber stamp reviews generate automation complacency, failing the Article 14 standard.`

**Report text used by the tool:**

```text
Evaluation Status: Conditional Warning

This system possesses sufficient blind spots to expose the organization to significant labor law and AI Act liabilities.

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Do not utilize this tool for adverse employment actions. You must institute mandatory human review committees and demand greater logic transparency from the software vendor.
```

---

#### C. Score below 35

**Result:** `HR WORKFLOW INVALID: CRITICAL COMPLIANCE FAILURE`

The tool generates a failure list only for answers scored **0**:

* If **System Scope = 0** → `[FAIL] Algorithm directly flags employees for termination.`
* If **Algorithmic Explainability = 0** → `[FAIL] Opaque Black Box logic prevents legal defensibility.`
* If **Intervention Protocol = 0** → `[FAIL] Automated execution violates human-in-the-loop mandates.`

**Report text used by the tool:**

```text
Evaluation Status: Failed / Article 14 Violation

This deployment functions as an uncontrolled, automated decision-maker regarding employee livelihoods. You lack the mandatory technical and organizational capabilities to govern this process.

Critical Compliance Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
Halt usage of this tool immediately. Do not execute any employment actions based on this system. You must re-architect the intervention protocols to establish absolute human authority before resuming operations.
```

---

### Decision Logic Summary

| Total Score | Result Band                                           | Meaning                                                                                    |
| ----------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **80–100**  | HR Workflow Verified: Defensible Architecture         | The workflow has strong explainability and binding human intervention controls.            |
| **35–79**   | HR Workflow Vulnerable: High Risk of Labor Litigation | The system still has material exposure around scope, explainability, or review discipline. |
| **0–34**    | HR Workflow Invalid: Critical Compliance Failure      | The tool treats the workflow as non-defensible for adverse employment action.              |

### Exact Threshold Notes

The thresholds in the source code are:

* `score >= 80` → defensible architecture
* `score >= 35` → high risk of labor litigation
* `score < 35` → critical compliance failure

That means:

* A score of **35** is still **vulnerable**, not compliant.
* Scores **80 and above** are treated as the strongest result band.
* This tool does **not** require a perfect 100/100 to reach the top band.

---

### Generated Output Structure

When all required fields are completed, the interactive tool generates this exact local record structure:

```text
Algorithmic Labor Action Assessment
Assessment Date: [UTC timestamp]

System Identifier: [Performance System Identifier or [UNNAMED SYSTEM]]

Executive Attestation:
The Chief Human Resources Officer formally attests that the transparency controls and human intervention protocols for this performance management system have been formally reviewed by Legal Counsel.

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this implementation note below the output:

*This report analyzes critical labor liability. Export this directly to your General Counsel to establish governance parameters prior to performance review cycles.*

---

## What to Do Next

| If your result is...                                              | Recommended next tool(s)                                                                                                                        | Why                                                                                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Vulnerable or invalid HR workflow                                 | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)                      | These tools help prove whether human intervention is real and whether managers are structurally able to challenge the AI. |
| Explainability or role/accountability is unclear                  | [Accidental Provider Classifier](05-accidental-provider-classifier.md), [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md)                | Weak HR AI deployments often also have unclear vendor liability, modification risk, or unverified software logic.         |
| Broader deployer operating model is weak                          | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md) | Employment AI still requires a wider deployer control model beyond this single labor-action workflow test.                |
| You need wider classification context for the employment use case | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                            | Use these to place the employment system back into the wider EU AI Act role and risk classification framework.            |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/promo-termination-validator.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
