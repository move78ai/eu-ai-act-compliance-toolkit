<!-- 18-agentic-ai-bounds-definer.md -->
# Agentic AI Bounds Definer — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 3 scored questions + 1 architectural attestation + 2 context fields  
> **EU AI Act References:** Article 14, Article 26, Recital 70  
> **Purpose:** Test whether an autonomous AI workflow has defensible human control boundaries, least-privilege API scope, and an immediate intervention mechanism before production deployment.

**🔗 [Try the interactive version →](https://euaicompass.com/agentic-ai-bounds-definer.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates whether an agentic AI workflow has the minimum technical intervention controls needed to avoid a runaway-action design. It focuses on three architectural variables: whether external write-actions require human approval, whether API scope is constrained by least privilege, and whether operators can instantly sever the agent’s access without waiting for IT or engineering.

It is most useful for CTOs, CISOs, enterprise architects, AI engineering leads, legal/compliance teams, and operational owners deploying autonomous or semi-autonomous agents against business systems. The interactive version also generates a downloadable/copyable **Agentic AI Autonomy Bounds Report** for internal architecture review.

---

## Instructions

Complete the two context fields, answer all three architectural questions, and check the architectural attestation.

This tool is **score-based**. Each answer has a fixed value:

- **Action Authorization** = 0, 10, or 33
- **API Blast Radius** = 0, 10, or 33
- **Intervention Capability (Kill Switch)** = 0, 10, or 34

Add the three scores to produce a total out of **100**. Then apply the exact thresholds in the **Scoring Guide**.

---

## Section 1 — Agent Context

**Q1. Agent Name or Identifier**

- [ ] Enter free text  
  Example: `Automated HR Scheduler Bot`

> *Guidance: If left blank, the generated report uses `[UNNAMED AGENT]`.*

**Q2. Target APIs or Systems**

- [ ] Enter free text  
  Example: `Workday, Outlook Calendar, Jira`

> *Guidance: If left blank, the generated report uses `[UNDEFINED APIs]`.*

---

## Section 2 — Action Authorization

**Q3. How does the agent execute external state changes?**  
*Example: deleting a record or sending an email to a client.*

- [ ] **Fully Autonomous (Critical Risk)** — The agent executes write-actions independently without any human confirmation. **(0 points)**
- [ ] **Human-in-the-Loop for Critical Only** — The agent handles routine write-actions automatically, but flags major changes for human review. **(10 points)**
- [ ] **Strict Human Approval (Defensible)** — The agent drafts the payload, but every external write-action requires an explicit human click to execute. **(33 points)**

> *Guidance: The tool treats routine autonomous write-actions as a control failure risk. Full defensibility requires explicit human approval before every external write-action.*

---

## Section 3 — API Blast Radius

**Q4. What level of technical scope does the service account controlling the agent possess?**

- [ ] **Admin / Full Access (Critical Risk)** — The agent connects using broad administrator credentials capable of system-wide changes. **(0 points)**
- [ ] **Scoped but Broad** — The agent has standard user access. A hallucination could alter many records before being detected. **(10 points)**
- [ ] **Strict Least Privilege (Defensible)** — The agent is strictly sandboxed. It utilizes read-only access by default and requires temporary, specific tokens to write. **(33 points)**

> *Guidance: The tool is checking whether the agent is sandboxed and token-scoped. Broad standard-user or admin-level access materially expands the damage a hallucination or misfire can cause.*

---

## Section 4 — Intervention Capability (The Kill Switch)

**Q5. How does a human operator stop the agent if it begins executing unintended actions?**

- [ ] **No Immediate Halt (Critical Risk)** — Stopping the agent requires developer intervention or pulling the server offline entirely. **(0 points)**
- [ ] **IT Ticket Process** — Operators must request an IT admin to revoke the agent’s API tokens. This creates a dangerous time delay. **(10 points)**
- [ ] **Instant Operator Kill Switch (Defensible)** — Operators possess a direct UI control to instantly sever the agent’s API access without IT assistance. **(34 points)**

> *Guidance: The source page frames this as the “emergency brake” test under Article 14. A delayed or ticket-based stop process is not treated as a defensible intervention capability.*

---

## Section 5 — Architectural Attestation

**Q6. Architectural Attestation**

- [ ] I attest that the autonomy bounds and intervention protocols for this agentic workflow have been formally reviewed by IT architecture.

> *Guidance: The interactive tool blocks output unless this attestation is checked. It treats the attestation as formal confirmation that the architecture has been reviewed and documented.*

---

## Scoring Guide

### Step 1 — Completion rules

You must answer all three scored questions:

- Action Authorization
- API Blast Radius
- Intervention Capability (Kill Switch)

If any of the three is unanswered, the interactive tool stops and shows:

**Action Required: Please evaluate all three architectural parameters.**

You must also check the architectural attestation.  
If not checked, the interactive tool stops and shows:

**Action Required: You must verify the architectural attestation before proceeding.**

---

### Step 2 — Calculate the score

Add the selected values:

```text
Final Score = Action Authorization + API Blast Radius + Intervention Capability
````

Possible values:

* Q3 = 0 / 10 / 33
* Q4 = 0 / 10 / 33
* Q5 = 0 / 10 / 34

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `AGENTIC BOUNDS VERIFIED: DEFENSIBLE AUTONOMY`

**Report text used by the tool:**

```text
Architecture Status: Highly Defensible

This agent design enforces robust Article 14 intervention protocols.

Verified Strengths:
[PASS] All external write-actions are gated by human approval.
[PASS] API access operates under strict least-privilege sandboxing.
[PASS] Operators possess a direct, instant kill switch to halt execution.

Next Steps:
Proceed with deployment. Retain this architectural blueprint locally to demonstrate human-in-the-loop control to regulatory authorities.
```

---

#### B. Score between 40 and 99

**Result:** `AGENTIC BOUNDS VULNERABLE: HIGH RISK OF RUNAWAY ACTIONS`

The tool generates a warning list for each answer below the fully defensible threshold:

* If **Q3 < 33** → `[WARN] Routine write-actions lack human-in-the-loop confirmation.`
* If **Q4 < 33** → `[WARN] API access is overly broad, increasing the damage potential of hallucinations.`
* If **Q5 < 34** → `[WARN] Kill switch relies on IT ticketing, creating a dangerous time delay.`

**Report text used by the tool:**

```text
Architecture Status: Conditional Warning

This agent possesses sufficient autonomy to execute unintended actions before operators can intervene. 

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Scale back the agent's autonomy. You must tighten the API scope and provide operators with an instant, direct UI halt mechanism before moving to production.
```

---

#### C. Score below 40

**Result:** `AGENTIC BOUNDS INVALID: CRITICAL LOSS OF CONTROL`

The tool generates a failure list only for answers scored **0**:

* If **Q3 = 0** → `[FAIL] Agent executes write-actions fully autonomously.`
* If **Q4 = 0** → `[FAIL] Service account possesses dangerous administrator-level access.`
* If **Q5 = 0** → `[FAIL] No immediate halt mechanism exists for the human operator.`

**Report text used by the tool:**

```text
Architecture Status: Failed / Article 14 Violation

This deployment functions as a runaway train. You lack the mandatory technical capabilities to effectively oversee or stop the AI system.

Critical Compliance Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
Halt development immediately. Do not connect this agent to live external APIs. You must re-architect the service account permissions and build a physical stop button before proceeding.
```

---

### Decision Logic Summary

| Total Score | Result Band                                             | Meaning                                                                                                               |
| ----------- | ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| **100**     | Agentic Bounds Verified: Defensible Autonomy            | All three control dimensions meet the tool’s fully defensible threshold.                                              |
| **40–99**   | Agentic Bounds Vulnerable: High Risk of Runaway Actions | The agent still has enough autonomy or privilege to execute unintended actions before operators can intervene safely. |
| **0–39**    | Agentic Bounds Invalid: Critical Loss of Control        | The tool treats the architecture as lacking the minimum intervention controls required for safe deployment.           |

### Exact Threshold Notes

The thresholds in the source code are:

* `score === 100` → defensible autonomy
* `score >= 40` → vulnerable / high risk of runaway actions
* `score < 40` → critical loss of control

That means:

* A score of **40** is still **vulnerable**, not compliant.
* The only fully successful outcome is **100/100**.

---

### Generated Output Structure

When all required fields are completed, the interactive tool generates this exact local record structure:

```text
Agentic AI Autonomy Bounds Report
Assessment Date: [UTC timestamp]

Agent Identifier: [Agent Name or Identifier or [UNNAMED AGENT]]
Target APIs: [Target APIs or Systems or [UNDEFINED APIs]]

Architectural Attestation:
The IT architect formally attests that the autonomy bounds and intervention protocols for this workflow have been reviewed and documented in accordance with Article 14 requirements.

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this implementation note below the output:

*This report documents your Article 14 intervention capabilities. Log this in your secure internal repository prior to finalizing the API connection.*

---

## What to Do Next

| If your result is...                                                                  | Recommended next tool(s)                                                                                                                        | Why                                                                                                                                     |
| ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Vulnerable or invalid autonomy bounds                                                 | [Automation Complacency Assessor](10-automation-complacency-assessor.md), [Human Oversight Log](06-human-oversight-log.md)                      | The next problem is usually whether humans can actually intervene in time and whether those interventions are documented.               |
| API scope or write-action design is the main weakness                                 | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | These tools help connect architectural weaknesses to concrete deployer-side operational controls and accountability.                    |
| You rely on third-party agents, wrappers, or hosted orchestration tools               | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md)                | Weak autonomy boundaries often sit inside unclear vendor control, outsourced inference, or role-shift exposure.                         |
| You need to test whether human review is still being materially steered by the system | [Material Influence Evaluator](11-material-influence-evaluator.md), [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md)     | These tools help determine whether the human remains substantively in control or whether the agent has crossed into material influence. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/agentic-ai-bounds-definer.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
