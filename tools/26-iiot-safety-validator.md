<!-- 26-iiot-safety-validator.md -->
# IIoT Safety Component Validator — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 3 scored questions + 1 engineering attestation + 1 optional system identifier  
> **EU AI Act References:** Annex III Area 2, Article 14, Article 15, Article 26  
> **Purpose:** Evaluate whether an IIoT / operational technology AI system has the robustness, safety-boundary, and adversarial-defense controls needed for a defensible critical-infrastructure deployment.

**🔗 [Try the interactive version →](https://euaicompass.com/iiot-safety-validator.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates whether an IIoT, SCADA, or critical-infrastructure AI system is architected as a defensible safety-related deployment or whether it creates unacceptable operational and regulatory risk. The source page states that AI systems used as safety components in the management of digital infrastructure, road traffic, or utility grids are strictly treated as high-risk and must satisfy unusually strong Article 15 robustness and cybersecurity expectations.

It is most useful for IIoT CTOs, OT Security Heads, utility operators, infrastructure engineering leads, vendor compliance teams, and legal/compliance reviewers assessing predictive maintenance, grid-balancing, or OT analytics systems before procurement or deployment. The interactive version also generates a downloadable/copyable **IIoT Safety Component Validation Report** locally in the browser for enterprise procurement and governance review.

---

## Instructions

Complete the optional system identifier, answer all three scored questions, and check the engineering attestation.

This tool is **score-based**. Each answer has a fixed value:

- **Functional Classification** = 0, 15, or 34
- **Physical Robustness Testing** = 0, 15, or 33
- **Adversarial Cybersecurity Defense** = 0, 15, or 33

Add the three scores to produce a total out of **100**. Then apply the exact thresholds in the **Scoring Guide**.

---

## Section 1 — System Context

**Q1. System Identifier**

- [ ] Enter free text  
  Example: `Predictive Grid Balancing Engine v4`

> *Guidance: If left blank, the generated report uses `[UNNAMED SYSTEM]`.*

---

## Section 2 — Functional Classification

**Q2. What is the direct operational capability of this algorithm within the physical network?**

- [ ] **Automated Physical Control (Critical Risk)** — The system actively commands valves, switches, or routing hardware without requiring human confirmation. **(0 points)**
- [ ] **Predictive Alert Generation** — The system predicts hardware failure and triggers real-time alerts for immediate human intervention. **(15 points)**
- [ ] **Retrospective Analytics (Defensible)** — The system strictly evaluates historical logs for reporting purposes and possesses zero real-time influence over physical infrastructure. **(34 points)**

> *Guidance: This question tests how close the system sits to live physical control. The strongest answer is historical analytics only; the weakest is direct command authority over infrastructure.*

---

## Section 3 — Physical Robustness Testing

**Q3. Under Article 15, how is the model validated against real-world sensor degradation?**

- [ ] **Sterile Lab Training (Critical Risk)** — The model is trained entirely on perfect, synthetic data without accounting for hardware wear, signal noise, or environmental interference. **(0 points)**
- [ ] **Periodic Calibration** — Engineers run batch accuracy tests quarterly using updated readings from the physical plant. **(15 points)**
- [ ] **Continuous Edge Validation (Defensible)** — The pipeline executes hardware-in-the-loop simulations, actively testing the AI against sensor failure and extreme physical anomalies. **(33 points)**

> *Guidance: The source page treats real-world physical failure simulation as the defensible standard. Static lab-only testing is treated as structurally unsafe for OT deployment.*

---

## Section 4 — Adversarial Cybersecurity Defense

**Q4. How does the architecture protect the algorithm from malicious data poisoning?**

- [ ] **Standard IT Perimeters (Critical Risk)** — We rely on standard corporate firewalls. The AI model itself possesses no specific defenses against adversarial input manipulation. **(0 points)**
- [ ] **Segmented Network Zones** — The OT network is segmented from the IT network, utilizing basic intrusion detection systems for data feeds. **(15 points)**
- [ ] **Adversarial SCADA Defenses (Defensible)** — The model architecture includes specialized defenses against data poisoning and model evasion designed explicitly for operational technology protocols. **(33 points)**

> *Guidance: The tool distinguishes ordinary IT security from specialized model-level defenses for hostile industrial-data manipulation. Segmentation alone is not treated as fully sufficient.*

---

## Section 5 — Engineering Attestation

**Q5. Engineering Attestation**

- [ ] I attest that the resilience and cybersecurity parameters of this system have been formally evaluated against Article 15 critical infrastructure mandates.

> *Guidance: The interactive tool blocks output unless this attestation is checked. The page frames this as formal engineering sign-off for Annex III critical infrastructure deployment.*

---

## Scoring Guide

### Step 1 — Completion rules

You must answer all three scored questions:

- Functional Classification
- Physical Robustness Testing
- Adversarial Cybersecurity Defense

If any of the three is unanswered, the interactive tool stops and shows:

**Action Required: Please evaluate all three infrastructure parameters.**

You must also check the engineering attestation.  
If not checked, the interactive tool stops and shows:

**Action Required: You must verify the engineering attestation before proceeding.**

---

### Step 2 — Calculate the score

Add the selected values:

```text
Final Score = Functional Classification + Physical Robustness Testing + Adversarial Cybersecurity Defense
````

Possible values:

* Q2 = 0 / 15 / 34
* Q3 = 0 / 15 / 33
* Q4 = 0 / 15 / 33

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `OT ARCHITECTURE VERIFIED: DEFENSIBLE DEPLOYMENT`

**Report text used by the tool:**

```text
Architecture Status: Highly Defensible

This IIoT system enforces robust operational boundaries and achieves the strict accuracy and cybersecurity standards mandated by Article 15.

Verified Safeguards:
[PASS] The system's operational capability minimizes automated physical risk.
[PASS] Continuous hardware-in-the-loop validation secures model robustness.
[PASS] Specialized adversarial SCADA defenses neutralize data poisoning threats.

Next Steps:
Proceed with client integration. Present this validation record directly to utility procurement teams to verify High-Risk compliance maturity.
```

---

#### B. Score between 40 and 99

**Result:** `OT ARCHITECTURE VULNERABLE: HIGH RISK OF INFRASTRUCTURE FAILURE`

The tool generates a warning list for each answer below the fully defensible threshold:

* If **Q2 < 34** → `[WARN] Generating predictive alerts without automated shutdown requires stringent Article 14 human oversight protocols.`
* If **Q3 < 33** → `[WARN] Periodic lab calibration fails to account for real-time edge sensor degradation.`
* If **Q4 < 33** → `[WARN] Basic network segmentation is insufficient against targeted adversarial AI attacks on industrial protocols.`

**Report text used by the tool:**

```text
Architecture Status: Conditional Warning

This critical infrastructure deployment possesses structural weaknesses that expose the utility operator to unacceptable physical and regulatory risk.

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Do not deploy to active utility grids. You must implement continuous physical failure simulations and upgrade your adversarial machine learning defenses before passing client procurement audits.
```

---

#### C. Score below 40

**Result:** `OT ARCHITECTURE INVALID: CRITICAL SAFETY COMPONENT VIOLATION`

The tool generates a failure list only for answers scored **0**:

* If **Q2 = 0** → `[FAIL] Direct automated control of physical infrastructure without human validation triggers extreme liability.`
* If **Q3 = 0** → `[FAIL] Sterile lab training guarantees catastrophic failure under physical stress conditions.`
* If **Q4 = 0** → `[FAIL] Reliance on standard IT perimeters leaves the AI model fully exposed to hostile data manipulation.`

**Report text used by the tool:**

```text
Architecture Status: Failed / Article 15 Violation

This deployment functions as an unprotected, automated safety component. You lack the mandatory cybersecurity, accuracy, and operational controls to deploy this into critical infrastructure.

Critical Compliance Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
Halt system deployment immediately. Do not connect to active operational technology environments. You must fundamentally re-architect the AI model to incorporate edge validation and specialized adversarial defenses.
```

---

### Decision Logic Summary

| Total Score | Result Band                                                     | Meaning                                                                                      |
| ----------- | --------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **100**     | OT Architecture Verified: Defensible Deployment                 | All three dimensions meet the tool’s fully defensible threshold.                             |
| **40–99**   | OT Architecture Vulnerable: High Risk of Infrastructure Failure | The system still has structural safety, robustness, or adversarial-defense weaknesses.       |
| **0–39**    | OT Architecture Invalid: Critical Safety Component Violation    | The tool treats the deployment as non-defensible for live OT or critical-infrastructure use. |

### Exact Threshold Notes

The thresholds in the source code are:

* `score === 100` → defensible deployment
* `score >= 40` → high risk of infrastructure failure
* `score < 40` → critical safety component violation

That means:

* A score of **40** is still **vulnerable**, not compliant.
* The only fully successful outcome is **100/100**.

---

### Generated Output Structure

When all required fields are completed, the interactive tool generates this exact local record structure:

```text
IIoT Safety Component Validation Report
Assessment Date: [UTC timestamp]

System Identifier: [System Identifier or [UNNAMED SYSTEM]]

Executive Attestation:
Operational Technology Leadership formally attests that the resilience and cybersecurity parameters of this system have been evaluated against Article 15 critical infrastructure mandates.

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this implementation note below the output:

*This report analyzes critical infrastructure liability. Export this directly to your enterprise utility clients to accelerate vendor compliance review.*

---

## What to Do Next

| If your result is...                                                             | Recommended next tool(s)                                                                                                                        | Why                                                                                                                                  |
| -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| OT architecture vulnerable or invalid                                            | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Once the safety-component architecture is weak, you need the deployer-side control and operational-readiness view immediately.       |
| The main weakness is adversarial resilience or external vendor dependency        | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [RAG Data Hygiene Screener](19-rag-data-hygiene-screener.md)                          | These tools help test vendor exposure, data routing, and internal repository/control weaknesses that often sit behind OT model risk. |
| Human intervention and override mechanics are weak                               | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)                      | Predictive alerting and safety escalation are not defensible if human review is nominal or structurally ineffective.                 |
| You need broader classification context for the critical-infrastructure use case | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                            | Use these to place the OT system back into the wider EU AI Act role and risk-classification framework.                               |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/iiot-safety-validator.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
