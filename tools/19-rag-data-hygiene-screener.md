<!-- 19-rag-data-hygiene-screener.md -->
# RAG Data Hygiene Screener — Self-Assessment

> **Time:** ~3 minutes · **Questions:** 3  
> **EU AI Act References:** Article 10, GDPR Article 5, GDPR Article 25  
> **Purpose:** Screen your internal RAG environment for permission sprawl, unsafe indexing scope, and missing retrieval traceability before deployment.

**🔗 [Try the interactive version →](https://euaicompass.com/rag-data-hygiene-screener.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool tests whether an internal Retrieval-Augmented Generation (RAG) deployment is sitting on top of defensible access controls and data hygiene. It focuses on three operational variables: baseline IAM discipline, whether the model indexes only approved repositories, and whether retrieval actions are logged with enough detail to support investigation and audit.

It is most useful for CISOs, IT directors, enterprise architects, security teams, and AI governance owners preparing to connect an internal LLM or copilot to corporate repositories. The interactive version also generates a downloadable/copyable **Internal RAG Hygiene Diagnostic Report** locally in the browser for internal governance review.

---

## Instructions

Answer all three questions by selecting **one option per question**.

Each answer has a fixed score:

- **Access Control Baseline (IAM)** = 0, 10, or 33
- **Data Segregation** = 0, 10, or 33
- **Audit and Retrieval Logging** = 0, 10, or 34

Add the three scores to produce a total out of **100**. Then apply the exact thresholds in the **Scoring Guide**.

---

## Section 1 — Access Control Baseline (IAM)

**Q1. How are file permissions currently structured across your connected repositories?**  
*Example: SharePoint or Google Workspace.*

- [ ] **Default Open (Critical Risk)** — Files are generally visible to the whole company unless actively locked down. Permission creep is rampant. **(0 points)**
- [ ] **Group Based** — Permissions are managed via broad departmental groups. Files are occasionally saved in the wrong group folder. **(10 points)**
- [ ] **Strict Least Privilege (Defensible)** — Access is rigorously controlled. Employees only possess access to the specific files required for their daily duties. **(33 points)**

> *Guidance: This question tests the real IAM baseline beneath the RAG layer. If the underlying permissions are loose, the model simply accelerates exposure of misfiled or overexposed documents.*

---

## Section 2 — Data Segregation

**Q2. What data is the AI actually allowed to read and index?**

- [ ] **Global Index (Critical Risk)** — The AI reads everything on the network. It relies purely on existing user permissions to filter outputs. **(0 points)**
- [ ] **Excluded Folders** — The AI index attempts to block specific high-risk folders. Example: blocking the HR drive. **(10 points)**
- [ ] **Whitelisted Only (Defensible)** — The AI only indexes pre-approved, sanitized data repositories. All other corporate drives are physically disconnected from the model. **(33 points)**

> *Guidance: The tool treats blacklisting or excluded-folder logic as weaker than a whitelist model. The control standard here is positive scoping, not “index everything except a few risky folders.”*

---

## Section 3 — Audit and Retrieval Logging

**Q3. When a user prompts the AI, how is the data retrieval logged?**

- [ ] **No Traceability (Critical Risk)** — We only see the prompt text. We cannot determine which specific source files the LLM accessed to generate the answer. **(0 points)**
- [ ] **Basic System Logs** — We can theoretically trace retrieval through deep server logs, but there is no accessible dashboard for security audits. **(10 points)**
- [ ] **Full Provenance Logging (Defensible)** — We explicitly log the user, the exact prompt, and the unique document IDs the model retrieved to form the response. **(34 points)**

> *Guidance: This question tests whether retrieval provenance is audit-ready. The strongest answer requires traceability from user prompt to source-document set, not just generic infrastructure logs.*

---

## Scoring Guide

### Step 1 — Completion rule

You must answer all three questions.

If any question is unanswered, the interactive tool stops and shows:

**Action Required: Please answer all three data hygiene questions.**

---

### Step 2 — Calculate the score

Add the selected values:

```text
Final Score = Q1 + Q2 + Q3
````

Possible values:

* Q1 = 0 / 10 / 33
* Q2 = 0 / 10 / 33
* Q3 = 0 / 10 / 34

Maximum score = **100**

---

### Step 3 — Interpret the result band

#### A. Score = 100

**Result:** `DEPLOYMENT VERIFIED: PRISTINE DATA HYGIENE`

**Report text used by the tool:**

```text
Your organization demonstrates a highly defensible approach to internal AI deployment.

Infrastructure Strengths:
[PASS] Access control enforces strict least privilege.
[PASS] RAG indexing is restricted solely to whitelisted, sanitized repositories.
[PASS] Retrieval provenance is fully traceable and logged.

Next Steps:
Proceed with deployment. Ensure these access logs are preserved locally to satisfy internal audit requirements and prove compliance to regulatory authorities.
```

---

#### B. Score between 40 and 99

**Result:** `DEPLOYMENT VULNERABLE: HIGH RISK OF INTERNAL BREACH`

The tool generates a warning list for each answer below the fully defensible threshold:

* If **Q1 < 33** → `[WARN] Broad group permissions create lateral access vulnerabilities.`
* If **Q2 < 33** → `[WARN] Folder exclusion lists are prone to human error and misfiling.`
* If **Q3 < 34** → `[WARN] Basic system logs hinder effective incident investigation.`

**Report text used by the tool:**

```text
Your environment contains structural vulnerabilities that an internal AI agent will rapidly exploit.

Identified Vulnerabilities:
[WARN] ... (all triggered warnings listed here)

Resolution Strategy:
Do not scale this deployment. You must enforce a whitelisting approach for data indexing and establish clear provenance tracking before exposing the tool to a wider employee base.
```

---

#### C. Score below 40

**Result:** `DEPLOYMENT INVALID: CRITICAL DATA LEAK IMMINENT`

The tool generates a failure list only for answers scored **0**:

* If **Q1 = 0** → `[FAIL] Default open permissions guarantee unauthorized file exposure.`
* If **Q2 = 0** → `[FAIL] Global indexing turns the AI into a mass data exfiltration tool.`
* If **Q3 = 0** → `[FAIL] Zero traceability prevents post-breach forensics.`

**Report text used by the tool:**

```text
Your organization is operating a critical compliance vulnerability. Connecting an LLM to this environment violates core data protection principles.

Critical Compliance Failures:
[FAIL] ... (all triggered failures listed here)

Resolution Strategy:
Halt deployment immediately. The project must be paused until the Identity and Access Management baseline is completely restructured. Do not deploy internal AI tools in a default-open network.
```

---

### Decision Logic Summary

| Total Score | Result Band                                         | Meaning                                                                                                             |
| ----------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **100**     | Deployment Verified: Pristine Data Hygiene          | All three controls meet the tool’s fully defensible threshold.                                                      |
| **40–99**   | Deployment Vulnerable: High Risk of Internal Breach | The environment still contains permission, scoping, or provenance weaknesses that an internal AI agent can exploit. |
| **0–39**    | Deployment Invalid: Critical Data Leak Imminent     | The tool treats the deployment as fundamentally unsafe for internal AI rollout.                                     |

### Exact Threshold Notes

The thresholds in the source code are:

* `score === 100` → pristine data hygiene
* `score >= 40` → high risk of internal breach
* `score < 40` → critical data leak imminent

That means:

* A score of **40** is still **vulnerable**, not compliant.
* The only fully successful outcome is **100/100**.

---

### Generated Output Structure

When all three answers are completed, the interactive tool generates this exact local record structure:

```text
Internal RAG Hygiene Diagnostic Report
Assessment Date: [UTC timestamp]

[Result-specific report body]

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
```

The interactive tool also displays this implementation note below the output:

*This report analyzes critical infrastructure risk. Paste this directly to the project steering committee to establish governance requirements before deployment.*

---

## What to Do Next

| If your result is...                                             | Recommended next tool(s)                                                                                                          | Why                                                                                                                  |
| ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Vulnerable or invalid RAG deployment                             | [Shadow AI Discovery Protocol](16-shadow-ai-discovery-protocol.md), [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md)      | Weak internal RAG hygiene often coexists with unregistered AI tooling and unclear third-party data-routing exposure. |
| Input scope or retrieval logging is the main weakness            | [Input Data Validator](09-input-data-validator.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md)            | These tools help tighten data-quality controls and the operational logging/monitoring discipline around AI use.      |
| Human oversight and intervention are still underdesigned         | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)        | Even a clean RAG layer does not solve weak review discipline or nominal oversight.                                   |
| You need broader deployer governance after fixing the data layer | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md), [ISO/NIST Gap Analyzer](15-iso-nist-gap-analyzer.md) | A safe RAG foundation still needs to sit inside a wider EU AI Act operating model and evidence architecture.         |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/rag-data-hygiene-screener.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

