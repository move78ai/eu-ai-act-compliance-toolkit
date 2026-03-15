
<!-- 04-article-6-exemption-generator.md -->
# Article 6(3) Exemption Generator — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 4 scored prompts + 2 asset-classification fields  
> **EU AI Act References:** Article 6(3), Annex III, Article 26  
> **Purpose:** Test whether an Annex III use case can be documented as exempt from high-risk classification because it poses no significant risk and fits one of the Article 6(3) exemption gates.

**🔗 [Try the interactive version →](https://euaicompass.com/article-6-exemption-framework.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates whether a system that might otherwise sit in an Annex III high-risk context can be mapped to an Article 6(3) exemption. It applies a hard-stop logic first: if the system performs profiling of natural persons or materially influences a final decision, the exemption path is blocked and the system is treated as high-risk.

It is most useful for compliance leads, product owners, CTOs, legal operations teams, and deployers who need a quick internal screening before claiming that an Annex III use case is exempt. The interactive version also generates a downloadable-style **local audit defense record** for internal governance tracking; this Markdown version cannot generate that output, so use the interactive version if you need the formatted record text.

---

## Instructions

Answer the Step 1 baseline verification questions first. If either answer is **Yes**, stop: the exemption is void in the tool logic.

If both Step 1 answers are **No**, move to Step 2 and select exactly **one** exemption gate. Then complete the Step 3 asset-classification fields for your internal record.

---

## Step 1: Baseline Verification (Hard Stops)

**Q1A. Does this system perform profiling of natural persons?**

- [ ] Yes, it performs profiling.
- [ ] No, it does not profile.

> *Guidance: The tool treats profiling as an automatic disqualifier. If the answer is Yes, the exemption path is blocked immediately.*

**Q1B. Does this system's output materially influence a final decision?**

- [ ] Yes, it influences decisions.
- [ ] No, it does not influence decisions.

> *Guidance: The tool gives this example: influencing a hiring decision, credit approval, or access to essential services. If the answer is Yes, the exemption path is blocked immediately.*

---

## Step 2: Select the Exemption Gate

**Q2. Which condition proves the system poses no "significant risk" under Article 6(3)?**

- [ ] **Narrow Procedural Task** — The AI does grunt work. It performs a strictly defined action. Example: sorting incoming invoices by date.
- [ ] **Human Activity Enhancement** — The AI polishes human work. It improves a previously completed human activity. Example: grammar checking a drafted review.
- [ ] **Pattern Detection** — The AI acts as a highlighter, not a decision-maker. A human must review the detected patterns without undue influence.
- [ ] **Preparatory Task** — The AI sets the table. It prepares data for a human assessment. Example: standardizing resume formatting.

> *Guidance: You may select an exemption gate only if both Step 1 answers are No. The interactive tool will not generate a record unless one gate is selected.*

---

## Step 3: Asset Classification

**Q3. Business Function**

- [ ] HR / Recruitment Tech
- [ ] FinTech / Credit Scoring
- [ ] EdTech / Assessment
- [ ] Operations / Security

> *Guidance: The tool says not to enter proprietary vendor names. Use a business-function classification instead of naming a vendor or confidential product.*

**Q4. Internal Alias (Optional)**

- [ ] Enter free text (example: `Project Alpha`, `System 001`)

> *Guidance: This field is optional. If completed, the alias is inserted into the generated audit record in the format `Business Function (Alias: [your text])`.*

---

## Scoring Guide

This tool uses a **strict branching logic**, not points.

### Rule 1 — Hard-stop disqualifier

If either of the following is true:

- **Q1A = Yes, it performs profiling**
- **Q1B = Yes, it influences decisions**

then the result is:

**Hard Stop. The Exemption is Void.**

The tool displays this exact outcome logic:

- The exemption path is blocked.
- Step 2 becomes disabled.
- Any previously selected exemption gate is cleared.
- No audit defense record can be generated.

**Result interpretation used by the tool:**  
*By performing profiling or materially influencing a decision, the system is permanently classified as High-Risk. You must comply with full Article 26 obligations immediately.*

### Rule 2 — Exemption path opens

If **Q1A = No** and **Q1B = No**, then:

- The hard-stop warning is removed.
- Step 2 becomes available.
- The user may select exactly one exemption gate.

### Rule 3 — Record generation condition

If Step 1 is cleared **and** one Step 2 exemption gate is selected, the tool generates a local text output.

If no Step 2 exemption gate is selected, the tool shows this blocking prompt:

**Action Required: Please select an Exemption Gate in Step 2 to generate the record.**

### Rule 4 — Generated result text

When the tool generates the local audit record, it uses this structure:

```text
EU AI Act Article 6(3) Exemption Record
(Record Generated Locally)

System Classification: [Business Function] OR [Business Function (Alias: ...)]
Assessment Date: [UTC timestamp]

Step 1: Baseline Verification
Profiling Status: Negative (Cleared)
Material Influence Status: Negative (Cleared)

Step 2: Exemption Claimed
Condition: [Selected exemption gate]

Compliance Attestation:
This system has been assessed against the criteria of the EU AI Act. It does not perform profiling of natural persons. It does not materially influence final decisions regarding health, safety, or fundamental rights. Furthermore, it falls strictly under the selected exemption condition. It poses no significant risk of harm under Annex III criteria.

As such, this system is exempt from High-Risk classification and full Article 26 Deployer obligations.

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
````

### Decision Tree Summary

Use this exact self-scoring sequence:

1. **Did you answer Yes to profiling?**

   * If **Yes** → **Exemption void. Treat as high-risk.**
   * If **No** → go to Question 2.

2. **Did you answer Yes to material influence over a final decision?**

   * If **Yes** → **Exemption void. Treat as high-risk.**
   * If **No** → go to Question 3.

3. **Did you select exactly one exemption gate?**

   * If **No** → **No result can be generated yet.**
   * If **Yes** → **Proceed to create an Article 6(3) exemption record.**

4. **Record the business function and optional alias**

   * These fields do **not** change the result.
   * They only change how the generated record labels the system.

---

## What to Do Next

| If your result is...                                                     | Recommended next tool(s)                                                                                                                        | Why                                                                                                                                   |
| ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Exemption void because profiling or material influence is present        | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md) | The tool itself treats the system as high-risk and says full Article 26 deployer obligations apply immediately.                       |
| Exemption appears available but you need broader classification context  | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                            | Use these to validate that the overall system context really supports the exemption claim and that no other route changes the result. |
| You need evidence that human review is real and not nominal              | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)                      | These tools help document oversight discipline and test whether the human reviewer is actually exercising meaningful control.         |
| The system is in HR, finance, education, or operational decision support | [Accidental Provider Classifier](05-accidental-provider-classifier.md), [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md)                | These tools help confirm that role boundaries, vendor dependencies, and modification practices do not undermine the exemption claim.  |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/article-6-exemption-framework.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
````markdown
<!-- 04-article-6-exemption-generator.md -->
# Article 6(3) Exemption Generator — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 4 scored prompts + 2 asset-classification fields  
> **EU AI Act References:** Article 6(3), Annex III, Article 26  
> **Purpose:** Test whether an Annex III use case can be documented as exempt from high-risk classification because it poses no significant risk and fits one of the Article 6(3) exemption gates.

**🔗 [Try the interactive version →](https://euaicompass.com/article-6-exemption-framework.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool evaluates whether a system that might otherwise sit in an Annex III high-risk context can be mapped to an Article 6(3) exemption. It applies a hard-stop logic first: if the system performs profiling of natural persons or materially influences a final decision, the exemption path is blocked and the system is treated as high-risk.

It is most useful for compliance leads, product owners, CTOs, legal operations teams, and deployers who need a quick internal screening before claiming that an Annex III use case is exempt. The interactive version also generates a downloadable-style **local audit defense record** for internal governance tracking; this Markdown version cannot generate that output, so use the interactive version if you need the formatted record text.

---

## Instructions

Answer the Step 1 baseline verification questions first. If either answer is **Yes**, stop: the exemption is void in the tool logic.

If both Step 1 answers are **No**, move to Step 2 and select exactly **one** exemption gate. Then complete the Step 3 asset-classification fields for your internal record.

---

## Step 1: Baseline Verification (Hard Stops)

**Q1A. Does this system perform profiling of natural persons?**

- [ ] Yes, it performs profiling.
- [ ] No, it does not profile.

> *Guidance: The tool treats profiling as an automatic disqualifier. If the answer is Yes, the exemption path is blocked immediately.*

**Q1B. Does this system's output materially influence a final decision?**

- [ ] Yes, it influences decisions.
- [ ] No, it does not influence decisions.

> *Guidance: The tool gives this example: influencing a hiring decision, credit approval, or access to essential services. If the answer is Yes, the exemption path is blocked immediately.*

---

## Step 2: Select the Exemption Gate

**Q2. Which condition proves the system poses no "significant risk" under Article 6(3)?**

- [ ] **Narrow Procedural Task** — The AI does grunt work. It performs a strictly defined action. Example: sorting incoming invoices by date.
- [ ] **Human Activity Enhancement** — The AI polishes human work. It improves a previously completed human activity. Example: grammar checking a drafted review.
- [ ] **Pattern Detection** — The AI acts as a highlighter, not a decision-maker. A human must review the detected patterns without undue influence.
- [ ] **Preparatory Task** — The AI sets the table. It prepares data for a human assessment. Example: standardizing resume formatting.

> *Guidance: You may select an exemption gate only if both Step 1 answers are No. The interactive tool will not generate a record unless one gate is selected.*

---

## Step 3: Asset Classification

**Q3. Business Function**

- [ ] HR / Recruitment Tech
- [ ] FinTech / Credit Scoring
- [ ] EdTech / Assessment
- [ ] Operations / Security

> *Guidance: The tool says not to enter proprietary vendor names. Use a business-function classification instead of naming a vendor or confidential product.*

**Q4. Internal Alias (Optional)**

- [ ] Enter free text (example: `Project Alpha`, `System 001`)

> *Guidance: This field is optional. If completed, the alias is inserted into the generated audit record in the format `Business Function (Alias: [your text])`.*

---

## Scoring Guide

This tool uses a **strict branching logic**, not points.

### Rule 1 — Hard-stop disqualifier

If either of the following is true:

- **Q1A = Yes, it performs profiling**
- **Q1B = Yes, it influences decisions**

then the result is:

**Hard Stop. The Exemption is Void.**

The tool displays this exact outcome logic:

- The exemption path is blocked.
- Step 2 becomes disabled.
- Any previously selected exemption gate is cleared.
- No audit defense record can be generated.

**Result interpretation used by the tool:**  
*By performing profiling or materially influencing a decision, the system is permanently classified as High-Risk. You must comply with full Article 26 obligations immediately.*

### Rule 2 — Exemption path opens

If **Q1A = No** and **Q1B = No**, then:

- The hard-stop warning is removed.
- Step 2 becomes available.
- The user may select exactly one exemption gate.

### Rule 3 — Record generation condition

If Step 1 is cleared **and** one Step 2 exemption gate is selected, the tool generates a local text output.

If no Step 2 exemption gate is selected, the tool shows this blocking prompt:

**Action Required: Please select an Exemption Gate in Step 2 to generate the record.**

### Rule 4 — Generated result text

When the tool generates the local audit record, it uses this structure:

```text
EU AI Act Article 6(3) Exemption Record
(Record Generated Locally)

System Classification: [Business Function] OR [Business Function (Alias: ...)]
Assessment Date: [UTC timestamp]

Step 1: Baseline Verification
Profiling Status: Negative (Cleared)
Material Influence Status: Negative (Cleared)

Step 2: Exemption Claimed
Condition: [Selected exemption gate]

Compliance Attestation:
This system has been assessed against the criteria of the EU AI Act. It does not perform profiling of natural persons. It does not materially influence final decisions regarding health, safety, or fundamental rights. Furthermore, it falls strictly under the selected exemption condition. It poses no significant risk of harm under Annex III criteria.

As such, this system is exempt from High-Risk classification and full Article 26 Deployer obligations.

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
````

### Decision Tree Summary

Use this exact self-scoring sequence:

1. **Did you answer Yes to profiling?**

   * If **Yes** → **Exemption void. Treat as high-risk.**
   * If **No** → go to Question 2.

2. **Did you answer Yes to material influence over a final decision?**

   * If **Yes** → **Exemption void. Treat as high-risk.**
   * If **No** → go to Question 3.

3. **Did you select exactly one exemption gate?**

   * If **No** → **No result can be generated yet.**
   * If **Yes** → **Proceed to create an Article 6(3) exemption record.**

4. **Record the business function and optional alias**

   * These fields do **not** change the result.
   * They only change how the generated record labels the system.

---

## What to Do Next

| If your result is...                                                     | Recommended next tool(s)                                                                                                                        | Why                                                                                                                                   |
| ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Exemption void because profiling or material influence is present        | [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md) | The tool itself treats the system as high-risk and says full Article 26 deployer obligations apply immediately.                       |
| Exemption appears available but you need broader classification context  | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [EU AI Act Quick Checker](01-quick-checker.md)                            | Use these to validate that the overall system context really supports the exemption claim and that no other route changes the result. |
| You need evidence that human review is real and not nominal              | [Human Oversight Log](06-human-oversight-log.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)                      | These tools help document oversight discipline and test whether the human reviewer is actually exercising meaningful control.         |
| The system is in HR, finance, education, or operational decision support | [Accidental Provider Classifier](05-accidental-provider-classifier.md), [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md)                | These tools help confirm that role boundaries, vendor dependencies, and modification practices do not undermine the exemption claim.  |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/article-6-exemption-framework.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
