<!-- 08-local-fria-generator.md -->
# Local FRIA Generator — Self-Assessment

> **Time:** ~3 minutes · **Questions:** 8 fields across 4 sections  
> **EU AI Act References:** Article 27, GDPR Article 35  
> **Purpose:** Structure a local Fundamental Rights Impact Assessment (FRIA) record for Annex III FinTech and Insurance deployment contexts.

**🔗 [Try the interactive version →](https://euaicompass.com/local-fria-generator.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool structures the six mandatory elements required by Article 27 into a local record format for deployers using Annex III systems in selected financial-services contexts. It is a documentation tool rather than a maturity score: it captures the deployer process, usage frequency, affected persons, specific risks of harm, oversight measures, and mitigation/complaint measures in one locally generated record.

It is most useful for compliance leads, legal teams, risk managers, CISO/CTO stakeholders, and deployers in FinTech or Insurance environments who need a working FRIA baseline before internal review or regulator-facing preparation. The interactive version also generates a downloadable/copyable **FRIA record** locally in the browser for your records.

---

## Instructions

Complete each field below. This tool does **not** use points, thresholds, or branching scores.

The interactive version will generate a record even if fields are incomplete. Any empty field is automatically replaced with:

`[PENDING INPUT]`

Use the generated record as a structural baseline only. The tool explicitly states that it does **not** replace a formal DPIA under GDPR Article 35.

---

## Section A — System Identity and Classification

**Q1. AI System Identifier**

- [ ] Enter free text

> *Guidance: Example from the tool: `Retail Credit Model v3`. If left blank, the generated record inserts `[PENDING INPUT]`.*

**Q2. Annex III Category**

- [ ] Point 5(b): Credit Scoring
- [ ] Point 5(c): Life/Health Insurance
- [ ] Point 5(a): Public Benefits

> *Guidance: This is a required classification selector in the interactive tool. It determines the Annex III category printed in the generated record.*

---

## Section B — Process and Temporal Scope

**Q3. Deployer Process Description**

- [ ] Enter free text

> *Guidance: Article 27(1)(a). Example from the tool: `Automated initial screening for retail mortgage applications.` The page notes this field is processed locally only.*

**Q4. Period and Frequency of Use**

- [ ] Enter free text

> *Guidance: Article 27(1)(b). Example from the tool: `Continuous real-time processing, 5,000 queries per month.`*

---

## Section C — Affected Persons and Fundamental Risks

**Q5. Categories of Affected Persons**

- [ ] Enter free text

> *Guidance: Article 27(1)(c). Example from the tool: `EU retail banking customers seeking auto loans.` The page notes this field is processed locally only.*

**Q6. Specific Risks of Harm**

- [ ] Enter free text

> *Guidance: Article 27(1)(d). Example from the tool: `Risk of algorithmic discrimination based on postal code proxy data.`*

---

## Section D — Oversight and Mitigation Strategy

**Q7. Human Oversight Measures**

- [ ] Enter free text

> *Guidance: Article 27(1)(e). Example from the tool: `All AI rejections undergo mandatory manual review by a Tier 2 loan officer.` The page notes this field is processed locally only.*

**Q8. Mitigation and Complaint Measures**

- [ ] Enter free text

> *Guidance: Article 27(1)(f). Example from the tool: `Automated bias testing monthly. Transparent appeals process provided in rejection emails.`*

---

## Scoring Guide

This tool uses **no numeric score and no result bands**. It is a **record generator**.

### Generation Logic

For each field, the interactive tool applies this rule:

- If the field contains text, use the entered text.
- If the field is blank, replace it with:

`[PENDING INPUT]`

The only field that is not free-text is **Annex III Category**, which is always selected from these three options:

- `Point 5(b): Credit Scoring`
- `Point 5(c): Life/Health Insurance`
- `Point 5(a): Public Benefits`

### Record Output Structure

When the user clicks **Generate Article 27 FRIA Record**, the interactive tool creates this exact output structure:

```text
Fundamental Rights Impact Assessment (FRIA)
Mandated under EU AI Act Article 27
(Record Generated Locally)

System Identifier: [AI System Identifier or [PENDING INPUT]]
Classification: Annex III, [Selected Annex III Category]
Assessment Date: [UTC timestamp]

Part A: Deployer Process Description
[Deployer Process Description or [PENDING INPUT]]

Part B: Period and Frequency of Use
[Period and Frequency of Use or [PENDING INPUT]]

Part C: Categories of Affected Persons
[Categories of Affected Persons or [PENDING INPUT]]

Part D: Specific Risks of Harm (Fundamental Rights)
[Specific Risks of Harm or [PENDING INPUT]]

Part E: Human Oversight Measures
[Human Oversight Measures or [PENDING INPUT]]

Part F: Risk Mitigation and Complaint Measures
[Mitigation and Complaint Measures or [PENDING INPUT]]

Attestation:
The deployer confirms this assessment complements any existing DPIA required under GDPR Article 35. This record is maintained locally for submission to the relevant market surveillance authority.

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
````

### Validation Notes

The interactive tool does **not** block output generation for incomplete answers. There is no minimum text length, no branching rule, and no threshold score.

### Additional Page Warning

The tool includes this disclaimer directly below the generator:

> *This structural mapping provides a formatting baseline for Article 27. It does not replace a formal Data Protection Impact Assessment (DPIA) under GDPR Article 35. Consult licensed EU regulatory counsel prior to submitting this FRIA to your market surveillance authority.*

---

## What to Do Next

| If your situation is...                                                           | Recommended next tool(s)                                                                                                         | Why                                                                                                             |
| --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| You still need to determine whether the system is actually in a high-risk route   | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)             | Confirm whether the use case is really in scope for Annex III / Article 27 before relying on the FRIA record.   |
| You need stronger operational controls around oversight and deployer duties       | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Human Oversight Log](06-human-oversight-log.md)             | Article 27 documentation is weak if Article 26 oversight, logging, and operator controls are weak.              |
| You need to test data quality, representativeness, or harms in the input pipeline | [Input Data Validator](09-input-data-validator.md), [Bias Testing Safe Harbor Protocol](20-bias-safe-harbor-protocol.md)         | These tools help make the “specific risks of harm” and mitigation sections more concrete and defensible.        |
| You rely on a third-party AI system or model                                      | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md) | FRIA quality depends on role clarity, vendor evidence, and understanding whether you are still only a deployer. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/local-fria-generator.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

