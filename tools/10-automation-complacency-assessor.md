<!-- 10-automation-complacency-assessor.md -->
# Automation Complacency Assessor — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 3  
> **EU AI Act References:** Article 14(1)–(5), Article 26(2)  
> **Purpose:** Test whether your human-oversight workflow is actually defensible or whether it has degraded into rubber-stamping of AI outputs.

**🔗 [Try the interactive version →](https://euaicompass.com/automation-complacency-assessor.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates the real operational conditions under which human reviewers interact with AI recommendations. It focuses on three practical failure modes: lack of review time, structural friction against overrides, and assigning oversight to staff who lack authority or AI-specific competence.

It is most useful for CISOs, compliance leads, HR operations leaders, credit-risk teams, product owners, and deployers of high-risk AI systems who need to prove that human oversight is genuine rather than theoretical. The interactive version also generates a downloadable/copyable **Human Oversight Viability Report** for internal audit records.

---

## Instructions

Answer all three workflow questions by selecting **one option per question**.

Each answer carries a fixed score. Add the three scores to produce a total out of **100**. Then apply the result thresholds exactly as shown in the **Scoring Guide**.

This tool is designed to test whether your workflow creates real human discretion or merely the appearance of it.

---

## Section A — Time Allocation

**Q1. How much time do your human operators realistically have to review each AI recommendation?**

- [ ] **Metrics Driven (High Risk)** — Operators face strict volume quotas. They physically only have seconds to approve each AI output to meet targets. **(0 points)**
- [ ] **Flexible but Rushed** — There are no strict quotas, but high workload generally forces operators to trust the AI to save time. **(10 points)**
- [ ] **Dedicated Review Time (Defensible)** — Workloads are adjusted to explicitly allow operators adequate time to investigate and double-check AI logic. **(33 points)**

> *Guidance: This question tests whether the workflow leaves enough time for genuine review. If operators must clear volume fast, “human oversight” is functionally cosmetic.*

---

## Section B — Override Friction

**Q2. What happens structurally when a human operator disagrees with the AI system?**

- [ ] **High Friction (High Risk)** — Overriding the AI requires massive justification, manager approval, or negatively impacts the operator's performance metrics. **(0 points)**
- [ ] **Neutral Friction** — Operators can override the AI freely. There is no active encouragement or structured feedback loop. **(10 points)**
- [ ] **Supported Override (Defensible)** — Operators are structurally encouraged to challenge the AI. Finding an AI error is treated as a positive catch. **(33 points)**

> *Guidance: The tool is testing whether override is truly feasible in practice. If challenging the AI creates career friction or process pain, operators will default to passive acceptance.*

---

## Section C — Role and Competence

**Q3. Who specifically is assigned to perform the human oversight duties?**

- [ ] **Junior Staff (High Risk)** — The task is delegated to entry-level staff who lack the domain expertise or corporate authority to reject the machine's logic. **(0 points)**
- [ ] **Standard Operations** — Mid-level staff perform the review. They know the business domain but lack specific training on algorithmic bias or AI limitations. **(10 points)**
- [ ] **Trained Authority (Defensible)** — Reviewers possess deep domain expertise, hold explicit authority to intervene, and receive specific AI literacy training. **(34 points)**

> *Guidance: This question tests whether the reviewer can meaningfully intervene. The tool treats lack of authority or AI-specific literacy as a structural oversight failure.*

---

## Scoring Guide

### Step 1 — Completion rule

You must answer all three workflow questions.

If any question is unanswered, the interactive tool stops and shows:

**Action Required: Please answer all three workflow questions.**

---

### Step 2 — Calculate the score

Add the selected values:

- **Q1 Time Allocation** = 0, 10, or 33
- **Q2 Override Friction** = 0, 10, or 33
- **Q3 Role and Competence** = 0, 10, or 34

**Formula:**

```text
Final Score = Q1 + Q2 + Q3
````

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `WORKFLOW VERIFIED: DEFENSIBLE OVERSIGHT`

**Report text used by the tool:**

```text
Your organization demonstrates a highly defensible approach to Article 14 Human Oversight.

Workflow Strengths:
[PASS] Operators are granted adequate time to evaluate decisions without volume pressure.
[PASS] The culture actively supports overriding AI anomalies.
[PASS] Reviewers possess the required domain competence and corporate authority.

Next Steps:
Ensure all overrides and concurrences are actively documented using an immutable local log to prove this reality to auditors.
```

---

#### B. Score between 40 and 99

**Result:** `WORKFLOW VULNERABLE: HIGH RISK OF COMPLACENCY`

The tool builds a warning list for each weak area:

* If **Q1 < 33** → `[WARN] Insufficient time allocated per review (Volume risk).`
* If **Q2 < 33** → `[WARN] Excessive organizational friction for overriding the AI.`
* If **Q3 < 34** → `[WARN] Reviewers lack specific AI training or authority.`

**Report text used by the tool:**

```text
Your workflow creates a structural environment where operators are highly likely to succumb to automation complacency.

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Your current setup treats the human as a speed bump. You must adjust performance metrics and lower override friction to ensure genuine discretion is possible.
```

---

#### C. Score below 40

**Result:** `WORKFLOW INVALID: ILLEGAL RUBBER STAMP`

The tool builds a failure list only for answers scoring **0**:

* If **Q1 = 0** → `[FAIL] Strict volume quotas force rapid, blind approvals.`
* If **Q2 = 0** → `[FAIL] Operators are penalized or blocked from overriding the AI.`
* If **Q3 = 0** → `[FAIL] Junior staff lack the authority to challenge the system.`

**Report text used by the tool:**

```text
Your organization is operating an illegal rubber stamp. The illusion of human control is legally classified as fully automated decision making.

Critical Compliance Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
You fail the basic requirements of Article 14 and GDPR Article 22. You must immediately halt deployment. You must redesign the workflow to assign senior personnel, remove volume quotas, and mandate documented justifications.
```

---

### Decision Logic Summary

| Total Score | Result Band                                   | Meaning                                                                                                  |
| ----------- | --------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **100**     | Workflow Verified: Defensible Oversight       | All three workflow conditions support meaningful human intervention.                                     |
| **40–99**   | Workflow Vulnerable: High Risk of Complacency | Human reviewers exist, but the structure materially pushes them toward passive acceptance of AI outputs. |
| **0–39**    | Workflow Invalid: Illegal Rubber Stamp        | The workflow is so weak that human oversight is functionally absent.                                     |

---

### Exact Threshold Notes

The score thresholds in the source code are:

* `score === 100` → defensible oversight
* `score >= 40` → high risk of complacency
* `score < 40` → illegal rubber stamp

This means:

* A score of **40** is still classified as **vulnerable**, not invalid.
* The only fully compliant outcome is **100/100**.

---

### Generated Output Structure

When all three answers are completed, the interactive tool generates this local report:

```text
Human Oversight Viability Report
Assessment Date: [UTC timestamp]

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this implementation note below the output:

*This report analyzes human workflow validity. Use this insight to redesign operational mandates before finalizing your compliance protocols.*

---

## What to Do Next

| If your result is...                                   | Recommended next tool(s)                                                                                                         | Why                                                                                                                                 |
| ------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Workflow vulnerable or invalid                         | [Human Oversight Log](06-human-oversight-log.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md)             | These tools turn the diagnosis into operational controls, intervention records, and Article 26 execution checks.                    |
| Reviewers lack authority or real intervention power    | [Material Influence Evaluator](11-material-influence-evaluator.md), [Agentic AI Bounds Definer](18-agentic-ai-bounds-definer.md) | Use these to test whether the AI is materially driving outcomes and whether your human control boundaries are actually enforceable. |
| Override is culturally discouraged or penalized        | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md), [Human Oversight Log](06-human-oversight-log.md)    | You need both governance ownership and evidence that overrides and concurrences are documented rather than performative.            |
| You need broader role and vendor accountability checks | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md) | Weak oversight often coexists with unclear responsibility between deployer, provider, and vendor.                                   |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/automation-complacency-assessor.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
