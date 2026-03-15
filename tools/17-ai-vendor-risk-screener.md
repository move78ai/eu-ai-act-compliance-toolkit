<!-- 17-ai-vendor-risk-screener.md -->
# AI Vendor Risk Screener — Self-Assessment

> **Time:** ~3 minutes · **Questions:** 3 + 1 optional vendor name field  
> **EU AI Act References:** Article 25, Article 26, GDPR Chapter V, DPA / TIA requirements  
> **Purpose:** Screen whether an AI SaaS vendor creates unacceptable data-sovereignty and cross-border processing risk before procurement.

**🔗 [Try the interactive version →](https://euaicompass.com/ai-vendor-risk-screener.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates whether an AI vendor’s terms and operating model create unacceptable procurement risk through model-training ingestion, foreign inference routing, or prompt-retention practices. The tool is designed as a fast DPA / commercial-terms screen before procurement approval, with a specific focus on GDPR Chapter V exposure and the practical governance burden that remains with the deployer.

It is most useful for procurement leads, CISOs, legal/privacy teams, CTOs, and AI governance owners reviewing third-party AI SaaS vendors before contract signature. The interactive version also generates a downloadable/copyable **Vendor AI Risk Attestation** for your internal procurement ticket.

---

## Instructions

Answer all three vendor-evaluation questions and optionally enter the vendor or application name.

This tool is **not point-based**. It uses a **traffic-light trigger model**:

- **Critical Fail** if any one critical-risk answer is selected
- **Conditional Approval** if no critical-fail answer is selected, but one or more medium-risk answers are selected
- **Approved** only if all three answers are the strongest/lowest-risk option

Apply the rules in the **Scoring Guide** exactly as written.

---

## Section 1 — The Ingestion Trap (Model Training)

**Q1. According to the vendor terms of service, do they use customer inputs to train or improve their own foundational AI models?**  
*Example: prompts and uploaded files.*

- [ ] **No or Zero Retention API** — The vendor explicitly guarantees in writing that customer data is never used for training.
- [ ] **Opt-Out Required** — They train on data by default. We must manually toggle a setting to opt out.
- [ ] **Yes or Unclear** — They retain the right to improve their services using our data. There is no enterprise opt-out available.

> *Guidance: This is the tool’s model-training ingestion test. “Yes or Unclear” is treated as an immediate procurement stop condition.*

---

## Section 2 — The Geographic Pipeline (Inference Data)

**Q2. Where does the actual compute and inference processing of the AI workload take place?**

- [ ] **Strictly EU or Local** — Compute is handled strictly within the EU with no US sub-processors. Alternatively, it is fully local on corporate hardware.
- [ ] **US Cloud or External** — Inference data is routed to the US or UK. This relies on Standard Contractual Clauses or DPF. It exposes prompts to the US CLOUD Act.
- [ ] **Unknown or API Wrapper** — The vendor passes inference data to third-party APIs. There is a high risk of sub-processor dilution and untraceable routing.

> *Guidance: The source tool treats unknown routing and opaque API-wrapper chains as the highest geographic-risk outcome because you cannot verify processor location or downstream transfers.*

---

## Section 3 — The Retention Window

**Q3. How long does the vendor store the prompts and generated outputs on their servers?**

- [ ] **Zero Retention** — Data is dropped immediately after the output is generated. Example: Enterprise APIs.
- [ ] **Trust and Safety Window** — Data is stored temporarily to monitor for abuse, then automatically purged. Example: 30-day retention.
- [ ] **Indefinite or Profile Linked** — Data is saved to user history indefinitely until manually deleted.

> *Guidance: The tool treats indefinite or profile-linked retention as a critical-risk posture because it creates a persistent prompt-history attack surface.*

---

## Section 4 — Vendor Identifier

**Q4. Target Vendor or Application Name (Optional)**

- [ ] Enter free text  
  Example: `Jasper AI`, `MS Copilot`, `Custom API Wrapper`

> *Guidance: This field is optional. If left blank, the generated attestation uses `[UNNAMED VENDOR]`.*

---

## Scoring Guide

This tool uses a **three-tier branching model**, not points or percentages.

### Step 1 — Completion rule

You must answer all three vendor-evaluation questions:

- The Ingestion Trap
- The Geographic Pipeline
- The Retention Window

If any answer is missing, the interactive tool stops and shows:

**Action Required: Please answer all three vendor evaluation questions.**

---

### Step 2 — Apply the result logic in order

The source code uses the following logic maps:

**Ingestion mapping**
- `No` → `Zero Retention API (No Training)`
- `Opt-Out` → `Opt-Out Required`
- `Yes` → `Yes / Unclear (Training Permitted)`

**Geography mapping**
- `EU` → `Strictly EU or Local Hardware`
- `US_Cloud` → `US Cloud or External (Schrems II Exposure)`
- `API_Wrapper` → `Unknown API Wrapper (Sub-processor Dilution)`

**Retention mapping**
- `Zero` → `Zero Retention`
- `30Days` → `Trust and Safety Window (Temporary)`
- `Indefinite` → `Indefinite User Profile History`

---

### Result A — Procurement Hold: Critical Data Risk

If **any one** of the following is true:

- **Q1 = Yes or Unclear**
- **Q2 = Unknown or API Wrapper**
- **Q3 = Indefinite or Profile Linked**

then the result is:

**PROCUREMENT HOLD: CRITICAL DATA RISK**

**Report text used by the tool:**

```text
Risk Posture: Critical Fail (GDPR Chapter V Risk)

We strongly advise against proceeding with this procurement. This vendor presents an unmanageable risk to corporate data sovereignty.

Critical Flags Detected:
* Vendor may train foundational models on proprietary data.
* Inference data geographic routing is unknown or exposed to foreign jurisdictions. High risk of sub-processor dilution.
* Indefinite retention creates a persistent attack surface for prompt history.

Required Action: 
Reject the current SaaS tier. Escalate to Enterprise API tier negotiations to secure a zero-retention Data Processing Agreement.
````

---

### Result B — Conditional Approval: Action Required

If **Result A does not apply**, but **any one** of the following is true:

* **Q1 = Opt-Out Required**
* **Q2 = US Cloud or External**
* **Q3 = Trust and Safety Window**

then the result is:

**CONDITIONAL APPROVAL: ACTION REQUIRED**

**Report text used by the tool:**

```text
Risk Posture: Conditional (Schrems II Exposure)

Procurement may proceed ONLY IF the following technical and legal controls are verified and enforced.

Mandatory Controls:
[ ] Admin MUST toggle the Opt-Out of Training setting immediately upon tenant creation.
[ ] Legal must conduct a Transfer Impact Assessment (TIA) for inference data routing and US CLOUD Act exposure.
[ ] Confirm the 30-day data purge policy is binding in the DPA.

Ensure users are trained not to submit highly sensitive PII, as the data exits the localized EU perimeter.
```

---

### Result C — Procurement Cleared: Sovereignty Maintained

If **all three** of the following are true:

* **Q1 = No or Zero Retention API**
* **Q2 = Strictly EU or Local**
* **Q3 = Zero Retention**

then the result is:

**PROCUREMENT CLEARED: SOVEREIGNTY MAINTAINED**

**Report text used by the tool:**

```text
Risk Posture: Approved (Sovereignty Maintained)

This vendor meets high-grade data sovereignty requirements for corporate deployment.

Verified Alignment:
* Zero data ingestion for model training.
* Compute and inference processing remains securely within the EU perimeter.
* Zero retention API architecture confirmed.

Required Action: 
Cleared for deployment. Proceed with standard IT onboarding and AI Act Article 26 Deployer logging.
```

---

### Decision Tree Summary

Use this exact self-scoring sequence:

1. **Did you answer all three questions?**

   * If **No** → no attestation can be generated.
   * If **Yes** → continue.

2. **Did you select any critical-risk answer?**

   * `Yes or Unclear`
   * `Unknown or API Wrapper`
   * `Indefinite or Profile Linked`
   * If **Yes** → **Procurement Hold: Critical Data Risk**
   * If **No** → continue.

3. **Did you select any conditional-risk answer?**

   * `Opt-Out Required`
   * `US Cloud or External`
   * `Trust and Safety Window`
   * If **Yes** → **Conditional Approval: Action Required**
   * If **No** → continue.

4. **Otherwise**

   * **Procurement Cleared: Sovereignty Maintained**

There are **no numeric scores, weights, or threshold percentages**.

---

## Generated Output Structure

When all required answers are completed, the interactive tool generates this exact local record structure:

```text
AI Vendor Data Sovereignty Attestation
(Record Generated Locally)

Vendor Application Name: [Vendor name or [UNNAMED VENDOR]]
Assessment Date: [UTC timestamp]

Assessment Inputs
Data Ingestion for Training: [Mapped ingestion label]
Geographic Routing of Inference Data: [Mapped geography label]
Prompt Retention Policy: [Mapped retention label]

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

---

## What to Do Next

| If your result is...                                                           | Recommended next tool(s)                                                                                                                        | Why                                                                                                                                             |
| ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Procurement hold / critical data risk                                          | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md), [Shadow AI Discovery Protocol](16-shadow-ai-discovery-protocol.md) | You need to understand deployer-side liability and make sure similar tools are not already being used informally inside the business.           |
| Conditional approval                                                           | [Input Data Validator](09-input-data-validator.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md)                          | The tool explicitly requires tighter controls around sensitive inputs, oversight, and operational logging when data leaves the local perimeter. |
| Vendor looks clean but framework maturity is uncertain                         | [ISO/NIST Gap Analyzer](15-iso-nist-gap-analyzer.md), [Human Oversight Log](06-human-oversight-log.md)                                          | A low-risk vendor does not solve internal control gaps around Article 10, Article 14, and operator accountability.                              |
| Vendor is being modified, rebranded, or embedded into a new high-risk workflow | [Accidental Provider Classifier](05-accidental-provider-classifier.md), [Material Influence Evaluator](11-material-influence-evaluator.md)      | Vendor procurement can still create role-shift and material-influence problems if your internal use changes the legal posture.                  |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/ai-vendor-risk-screener.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

