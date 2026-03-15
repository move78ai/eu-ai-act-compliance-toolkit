<!-- 16-shadow-ai-discovery-protocol.md -->
# Shadow AI Discovery Protocol — Self-Assessment

> **Time:** ~3 minutes · **Questions:** 4  
> **EU AI Act References:** Article 4, Article 26, GDPR Article 35  
> **Purpose:** Create a local registry record for unsanctioned departmental AI usage so discovered tools can be routed into formal review.

**🔗 [Try the interactive version →](https://euaicompass.com/shadow-ai-discovery-protocol.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool is a zero-cloud discovery workflow for mapping unsanctioned or unofficial AI usage inside business units. It is designed for CISOs and department heads to capture a minimum viable AI asset declaration without sending tool, use-case, or data exposure details to a third party.

It is most useful for CISOs, department heads, IT operations, legal/compliance, and risk teams that need a fast intake mechanism before formal vendor review, AI classification, or data protection assessment. The interactive version also generates a downloadable/copyable **AI Asset Registry Declaration** for direct pasting into an internal IT ticket or secure Slack/Teams channel.

---

## Instructions

Complete all four required fields:

1. Business Unit / Department
2. AI Tool Name
3. Primary Purpose
4. Data Exposure Risk Assessment

Then use the generated block as an intake artifact for your internal service desk, AI asset register, or secure collaboration channel.

This tool is **not point-based**. It is a **record generator** with a strict completion rule.

---

## Section A — Business Unit / Department

**Q1. Business Unit / Department**

- [ ] Human Resources / Talent Acquisition
- [ ] Marketing / Content Creation
- [ ] Sales / RevOps
- [ ] Engineering / Product Development
- [ ] Finance / Legal / Operations

> *Guidance: This field identifies the internal owner of the unsanctioned or unofficial AI usage. The source page positions this as a departmental declaration workflow for heads of function.*

---

## Section B — AI Tool Identification

**Q2. AI Tool Name**

- [ ] Enter free text  
  Example: `ChatGPT Plus`, `Jasper`, `GitHub Copilot`, `HR Screener AI`

> *Guidance: Record the actual tool or service name. The tool treats this as a required field.*

**Q3. Primary Purpose**

- [ ] Enter free text  
  Example: `Drafting emails`, `filtering candidate resumes`, `coding assistance`

> *Guidance: Record the real business use case, not a generic category. This becomes the “PRIMARY USE CASE” section in the generated record.*

---

## Section C — Data Exposure Risk Assessment

**Q4. What category of data is uploaded, pasted, or processed by this AI tool?**

- [ ] **Public Data Only (Low Risk)** — Information already publicly available (e.g., public blog posts, generic research).
- [ ] **Corporate IP (Medium Risk)** — Proprietary code, internal strategy docs, unreleased marketing materials.
- [ ] **PII / Sensitive Data (CRITICAL RISK)** — Customer data, employee resumes, health records, credit scores, or financial data.

> *Guidance: This is the only structured risk label in the tool. It does not calculate a score, but it directly determines the “DATA EXPOSURE RISK LEVEL” line in the output and should drive downstream triage priority.*

---

## Scoring Guide

This tool uses **no score, no weights, and no threshold bands**. It is a **completion-gated generator**.

### Step 1 — Completion rule

You must complete all four required fields:

- Business Unit / Department
- AI Tool Name
- Primary Purpose
- Data Exposure Risk Assessment

If any required field is missing, the interactive tool stops and shows this exact message:

**Action Required: Please complete all fields to generate the asset record.**

---

### Step 2 — Record generation logic

If all four required fields are completed, the tool generates a local record using:

- the selected **Business Unit / Department**
- the entered **AI Tool Name**
- the entered **Primary Purpose**
- the selected **Data Exposure Risk** label
- a UTC timestamp in the format: `YYYY-MM-DD HH:MM:SS UTC`

There is **no branching result category** beyond whether the record can be generated.

---

### Output Structure

When generation succeeds, the interactive tool creates this exact output block:

```text
================================================
AI ASSET REGISTRY DECLARATION (SHADOW AI DISCOVERY)
================================================
DATE REPORTED    : [UTC timestamp]
BUSINESS UNIT    : [Selected business unit]
AI TOOL NAME     : [Entered tool name]

PRIMARY USE CASE : 
[Entered purpose]

DATA EXPOSURE RISK LEVEL:
=> [Selected data exposure risk]

CISO / COMPLIANCE ROUTING NOTE:
This tool requires vetting for EU AI Act Deployer 
obligations (Article 26) and GDPR cross-border 
vendor data transfer compliance.

GENERATED VIA    : EU AI Compass Discovery Protocol
EXECUTION ENV    : 100% Local Browser Output
================================================
````

---

### Operational Use Pattern from the Tool Page

The page instructs teams to use the output in this sequence:

1. Department head fills out the tool locally in the browser.
2. Department head generates the plain-text AI Asset Block.
3. Department head copies and pastes it into the internal IT service desk or secure Slack/Teams channel.

The page explicitly says this tool should **not** be replaced with a PDF or insecure Google Form.

---

## What to Do Next

| If your discovered asset looks like...                                                     | Recommended next tool(s)                                                                                                                        | Why                                                                                                                  |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| A third-party AI vendor handling internal or sensitive data                                | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md)                                                                                        | The next control step is vendor risk and data transfer review.                                                       |
| A system that may trigger EU AI Act role or classification questions                       | [EU AI Act Quick Checker](01-quick-checker.md), [Detailed Applicability Scorer](02-detailed-applicability-scorer.md)                            | Once the shadow asset is identified, classify whether it is in scope, high-risk, or subject to transparency duties.  |
| A business unit using AI with employee, customer, or operational decision impact           | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md) | The page’s routing note explicitly points to Article 26 deployer obligations.                                        |
| A discovered tool processing proprietary code, resumes, financial, or other sensitive data | [Input Data Validator](09-input-data-validator.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md)                      | These tools help test input-data control quality and whether internal modification or repackaging changes your role. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/shadow-ai-discovery-protocol.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

