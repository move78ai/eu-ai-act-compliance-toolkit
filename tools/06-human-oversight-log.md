<!-- 06-human-oversight-log.md -->
# Human Oversight Log — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 5  
> **EU AI Act References:** Article 14, Article 26(2), GDPR Article 22  
> **Purpose:** Create a local, auditable record showing that a human operator exercised genuine discretion over an AI-assisted decision.

**🔗 [Try the interactive version →](https://euaicompass.com/human-oversight-log.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool does not classify risk. It documents whether a human operator has actually reviewed an AI recommendation, recorded an independent justification, and attested that they have the authority and training to intervene. It is designed to reduce “rubber-stamping” and create an auditable human-in-the-loop record for Article 14 and Article 26(2) purposes.

It is most useful for HR operators, FinTech operators, compliance teams, and line managers supervising AI-assisted approval, rejection, or escalation decisions. The interactive version also generates a downloadable/copyable **Human Intervention Record** for your internal files.

---

## Instructions

Complete every field below. Then apply the validation rules in the Scoring Guide.

This tool is **not point-based**. It uses a simple validation gate:

- You must select an operator action.
- You must provide a justification of at least 10 characters.
- You must attest to competence and authority.

If any required field is missing, the log cannot be generated.

---

## Section A — Decision Context

**Q1. System / Ticket ID**

- [ ] Enter free text  
  Example: `APP-2026-994`, `Candidate 402`

> *Guidance: The tool uses this field to label the log entry. If left blank, the generated record inserts `[UNNAMED ENTITY]`.*

**Q2. AI System Recommendation**

- [ ] Proceed / Approve
- [ ] Reject / Filter Out
- [ ] Flag for Manual Review

> *Guidance: This records the baseline recommendation produced by the AI system before human review.*

---

## Section B — Operator Action Taken

**Q3. What action did the human operator take?**

- [ ] Concur (Agree with AI)
- [ ] Override (Disagree with AI)
- [ ] Escalate to Tier 2

> *Guidance: The tool defines these exactly as follows:*
>
> *Concur (Agree with AI): I have reviewed the inputs and agree with the system's baseline recommendation.*  
> *Override (Disagree with AI): I am actively rejecting the system's output based on external context or identified bias.*  
> *Escalate to Tier 2: The AI output is ambiguous or confidence is low. This requires senior review.*

---

## Section C — Discretion Justification

**Q4. Provide 1–2 sentences proving your independent reasoning.**

- [ ] Enter free text

> *Guidance: The tool explicitly says: “Do not just write ‘looks good’.” The justification must be at least 10 characters long. Example from the tool: “Reviewed applicant portfolio manually. AI flagged gap in employment, but candidate noted sabbatical for education in cover letter. Overriding system rejection to proceed to interview.”*

---

## Section D — Competence and Authority

**Q5. Competence and Authority Attestation**

- [ ] I attest that I possess the designated authority and specific training to override this system's recommendation under corporate policy.

> *Guidance: The tool states that Article 26(2) requires human overseers to possess specific competence and authority. Without this attestation, no record can be generated.*

---

## Scoring Guide

This tool uses a **validation workflow**, not a score.

### Validation Rule 1 — Required action and justification

You must:

- select one option for **Q3 Operator Action Taken**, and
- provide a justification in **Q4** of at least **10 characters**

If either condition is not met, the tool stops and shows this exact message:

**Action Required: Please select an action and provide a detailed justification (minimum 10 characters).**

---

### Validation Rule 2 — Authority attestation required

You must check the competence-and-authority attestation in **Q5**.

If not checked, the tool stops and shows this exact message:

**Action Required: You must attest to your competence and authority before logging this decision.**

---

### Validation Rule 3 — Default value handling

If **Q1 System / Ticket ID** is blank, the tool substitutes:

`[UNNAMED ENTITY]`

The **AI System Recommendation** field always has a selected value in the interactive tool, with these possible outputs:

- `Proceed / Approve`
- `Reject / Filter Out`
- `Flag for Manual Review`

---

### Record Generation Logic

If all required fields pass validation, the tool generates a local output with the following structure:

```text
Human Intervention Record (Article 14)
(Record Generated Locally)

Entity / Ticket ID: [System / Ticket ID or [UNNAMED ENTITY]]
Timestamp: [UTC timestamp]

System Output
The AI system recommended: [AI Recommendation]

Human Discretion Applied
Operator Action Taken: [CONCUR / OVERRIDE / ESCALATE]

Independent Justification
[Operator justification text]

Competence and Authority Attestation
The operator has attested they possess the designated authority and specific training to override this system's recommendation under corporate policy.

Legal Attestation
I certify that I have exercised genuine human discretion in reviewing this automated output. This review complies with corporate policy regarding Article 14 of the EU AI Act and Article 22 of the GDPR.

Generated via EU AI Compass
Execution Environment: Local Browser (Zero Cloud Sync)
````

---

### Decision Tree Summary

1. **Did you select an operator action?**

   * If **No** → no record can be generated.
   * If **Yes** → continue.

2. **Is your justification at least 10 characters?**

   * If **No** → no record can be generated.
   * If **Yes** → continue.

3. **Did you attest to competence and authority?**

   * If **No** → no record can be generated.
   * If **Yes** → generate the Human Intervention Record.

There are **no weighted scores, thresholds, or result bands**.

---

## What to Do Next

| If your issue is...                                                                    | Recommended next tool(s)                                                                                                                        | Why                                                                                                                         |
| -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| You need to test whether humans are only rubber-stamping AI outputs                    | [Automation Complacency Assessor](10-automation-complacency-assessor.md), [Agentic AI Bounds Definer](18-agentic-ai-bounds-definer.md)          | These tools help determine whether human review is meaningful and whether the system’s operating boundaries are controlled. |
| You are documenting oversight for a deployer of high-risk AI                           | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Use these to connect the log record to the broader operational duties that sit around Article 14 and Article 26.            |
| You need to prove a human can reject or escalate rather than blindly follow the system | [Material Influence Evaluator](11-material-influence-evaluator.md), [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md)     | These tools help assess whether the AI is materially driving the outcome and whether claimed human control is genuine.      |
| You rely on third-party AI recommendations in HR or FinTech                            | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Accidental Provider Classifier](05-accidental-provider-classifier.md)                | These tools help verify vendor role boundaries, modification risks, and accountability for system outputs.                  |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/human-oversight-log.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
