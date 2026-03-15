<!-- 05-accidental-provider-classifier.md -->
# Accidental Provider Classifier — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 3 + 1 optional alias field  
> **EU AI Act References:** Articles 25, 26, 26(8), 8–15  
> **Purpose:** Check whether branding, substantial modification, or purpose-shifting of a third-party AI system likely reclassifies your organization from Deployer to Provider.

**🔗 [Try the interactive version →](https://euaicompass.com/accidental-provider-classifier.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool screens for the classic “accidental provider” problem: a company starts as a deployer of a third-party AI system, then crosses into provider status by white-labelling it, substantially modifying it, or changing its intended purpose into a high-risk use case. The tool is designed as a fast legal-posture check for CISOs, legal counsel, product owners, engineering leads, and procurement/compliance teams evaluating modifications to vendor or open-source AI systems.

The interactive version also generates a downloadable-style **local browser assessment record** that can be copied into internal compliance files. This Markdown version cannot generate that record automatically, but the exact record structure is reproduced below.

---

## Instructions

Answer all three condition questions. You must answer **Yes** or **No** for each one.

Then apply the Scoring Guide exactly as written. This tool is **not point-based**. It uses a simple trigger rule:

- If **any one** of the three trigger questions is answered **Yes**, the system is classified as **Provider**.
- If **all three** trigger questions are answered **No**, the system remains **Deployer**.

The optional internal alias field does **not** affect the result. It only changes the text label in the generated assessment record.

---

## Section A — Trigger Conditions

### Q1. The Trademark Trigger

**Are you placing your company's name or trademark on a high-risk AI system that is already on the market?**  
*(e.g., buying a white-label HR screening AI and branding it entirely as your own proprietary tool).*

- [ ] Yes
- [ ] No

> *Guidance: This question tests whether you are effectively re-presenting an existing high-risk AI system as your own product. In the tool logic, a Yes is enough to trigger Provider classification.*

---

### Q2. The Substantial Modification Trigger (Fine-Tuning)

**Have your engineers made a "substantial modification" to a third-party high-risk AI system?**

- [ ] Yes
- [ ] No

> *Guidance: The tool explicitly says this includes fine-tuning an open-source model on your proprietary corporate data, or adjusting the algorithmic weighting criteria of an existing screening tool. In the tool logic, a Yes is enough to trigger Provider classification.*

---

### Q3. The Intended Purpose Trigger

**Are you using a general AI system for a high-risk Annex III purpose it was not explicitly built for?**  
*(e.g., taking an open-source chatbot API and hard-coding it into a tool that automatically rejects loan applications or job candidates).*

- [ ] Yes
- [ ] No

> *Guidance: This question tests whether you have changed the system’s intended purpose into a high-risk use case. In the tool logic, a Yes is enough to trigger Provider classification.*

---

## Section B — System Internal Alias

### Q4. System Internal Alias (Optional)

- [ ] Enter free text (example: `Project Omega`, `HR Core Logic v2`)

> *Guidance: This field is optional. If completed, it is inserted into the generated assessment record. If left blank, the interactive tool uses `[UNNAMED SYSTEM]`.*

---

## Scoring Guide

This tool uses a **single OR-rule classification test**.

### Rule 1 — Completion requirement

You must answer all three trigger questions:

- Q1 Trademark Trigger
- Q2 Substantial Modification Trigger
- Q3 Intended Purpose Trigger

If any of the three is unanswered, the tool stops and shows this message:

**Action Required: Please answer all three condition questions to run the classification.**

---

### Rule 2 — Provider trigger logic

The tool calculates:

```text
isProvider = (Q1 = Yes) OR (Q2 = Yes) OR (Q3 = Yes)
````

#### If **isProvider = Yes**

Your result is:

**CRITICAL RISK: PROVIDER STATUS TRIGGERED**

The interactive tool generates this legal posture:

```text
LEGAL POSTURE: PROVIDER (ARTICLE 25/26 TRIGGERED)
================================================
Based on the provided inputs, the modifications made to 
this system trigger 'Provider' classification under 
the EU AI Act. 

By applying your trademark, substantially modifying 
the architecture, or shifting the intended purpose 
to a High-Risk category, you have inherited the legal 
liability of the original manufacturer.

MANDATORY NEXT STEPS (ARTICLES 8-15):
[ ] Halt deployment immediately.
[ ] Establish Quality Management System (QMS).
[ ] Generate Annex IV Technical Documentation.
[ ] Execute Conformity Assessment.
[ ] Affix CE Marking.
[ ] Register in EU Database.
```

#### If **isProvider = No**

Your result is:

**STATUS VERIFIED: DEPLOYER ONLY**

The interactive tool generates this legal posture:

```text
LEGAL POSTURE: DEPLOYER
================================================
Based on the provided inputs, the internal usage of 
this system remains within the safe harbor of a 
'Deployer'. You have not triggered Provider obligations 
under Article 25/26.

OPERATIONAL REQUIREMENT (ARTICLE 26):
You are clear of CE marking liability, but you must 
still execute Deployer duties:
[ ] Follow vendor instructions for use.
[ ] Assign competent human oversight.
[ ] Maintain local system logs.
[ ] Monitor for anomalous performance.
```

---

### Decision Tree Summary

Use this exact self-scoring sequence:

1. **Did you answer Yes to the Trademark Trigger?**

   * If **Yes** → **Provider**
   * If **No** → continue

2. **Did you answer Yes to the Substantial Modification Trigger?**

   * If **Yes** → **Provider**
   * If **No** → continue

3. **Did you answer Yes to the Intended Purpose Trigger?**

   * If **Yes** → **Provider**
   * If **No** → **Deployer**

This means:

* **Any single Yes** = **Provider**
* **All three No** = **Deployer**

There are **no weights, thresholds, or partial scores**.

---

### Generated Record Structure

When all three questions are answered, the interactive tool creates a local assessment record in this exact structure:

```text
================================================
AI ACT RECLASSIFICATION ASSESSMENT RECORD
================================================
SYSTEM ALIAS     : [System Alias or [UNNAMED SYSTEM]]
ASSESSMENT DATE  : [UTC timestamp]

CONDITION 1 (Trademark)    : [YES/NO]
CONDITION 2 (Modification) : [YES/NO]
CONDITION 3 (Purpose Shift): [YES/NO]

[LEGAL POSTURE BLOCK FROM ABOVE]

GENERATED VIA    : EU AI Compass Classifier
EXECUTION ENV    : 100% Local Browser Output
================================================
```

---

## What to Do Next

| If your result is...                                        | Recommended next tool(s)                                                                                                                        | Why                                                                                                                                      |
| ----------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Provider status triggered                                   | [Article 26 Operations Scorer](07-article-26-operations-scorer.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Move from role-classification into the operational obligations and control actions that follow from a high-risk/provider posture.        |
| Trigger came from a possible Annex III use-case change      | [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md), [Detailed Applicability Scorer](02-detailed-applicability-scorer.md)   | Test whether the use case is genuinely high-risk without an exemption, and validate the broader classification context.                  |
| You remain Deployer but rely heavily on vendor AI           | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [Human Oversight Log](06-human-oversight-log.md)                                      | Even if Provider status is not triggered, you still need vendor control, oversight, logging, and monitoring discipline.                  |
| You are unsure whether modification was truly “substantial” | [Material Influence Evaluator](11-material-influence-evaluator.md), [Automation Complacency Assessor](10-automation-complacency-assessor.md)    | These tools help test whether real human control remains intact and whether system influence has drifted beyond a safe deployer posture. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/accidental-provider-classifier.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 26 Tools →](../README.md)*

