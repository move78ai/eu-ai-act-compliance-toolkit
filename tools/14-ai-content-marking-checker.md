<!-- 14-ai-content-marking-checker.md -->
# AI Content Marking Compliance Checker — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 6  
> **EU AI Act References:** Article 50(1), Article 50(3), Article 50(4), Code of Practice Draft 2  
> **Purpose:** Check whether your AI content pipeline meets the two-layer marking approach and related operational controls expected for Article 50 transparency compliance.

**🔗 [Try the interactive version →](https://euaicompass.com/ai-content-marking-checker.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool checks whether your content pipeline is within Article 50 scope and, if so, whether it has implemented the marking and transparency layers described on the page as part of the Code of Practice Draft 2 approach. It evaluates scope first, then tests metadata, watermarking, user-facing labelling, detection capability, and internal process maturity.

It is most useful for CMOs, digital product leaders, compliance teams, legal counsel, trust and safety teams, and content operations owners managing chatbots, synthetic media, AI-generated public-interest text, or emotion recognition / biometric categorization systems.

---

## Instructions

Answer all six questions. Start with the content type question to determine whether Article 50 is likely in scope for your use case.

If you select **None of the Above** for Question 1, the tool stops there and returns an out-of-scope style result. Otherwise, answer Questions 2–6 and calculate your readiness score using the exact scoring logic below.

---

## Section A — Scope Check

**Q1. Which AI-generated content types does your organization produce or deploy?**

- [ ] **Chatbot / Conversational AI** — Users interact with an AI system (customer service bots, virtual assistants, AI copilots). Article 50(1) applies.
- [ ] **Synthetic Media (Images, Audio, Video)** — AI generates or manipulates visual/audio content (marketing images, voice synthesis, video editing). Article 50(4) applies.
- [ ] **AI-Generated Text on Public Interest** — AI produces text published on matters of public interest (news, analysis, reports). Article 50(4) applies.
- [ ] **Emotion Recognition / Biometric Categorization** — AI infers emotional states or categorizes biometric attributes. Article 50(3) applies.
- [ ] **None of the Above** — Backend-only AI with no public-facing content generation or user interaction.

> *Guidance: This is the gating question. If you select “None of the Above,” the tool does not score the remaining controls and instead returns an “Article 50 may not apply” result.*

---

## Section B — Layer 1: Provenance Metadata

**Q2. Does your content pipeline embed machine-readable provenance metadata (e.g., C2PA content credentials) in generated files?**

- [ ] **No Metadata (Gap)** — Generated content contains no provenance information. Origin cannot be traced programmatically. **(0 points)**
- [ ] **Basic Metadata** — Some metadata exists (EXIF, basic tags) but not in a standardized provenance format like C2PA. **(8 points)**
- [ ] **C2PA or Equivalent (Compliant)** — Content credentials are embedded using C2PA or equivalent standard. Provenance is machine-readable and tamper-evident. **(16 points)**

> *Guidance: The source page treats this as the first technical marking layer. Basic EXIF-style tags are not treated as fully compliant because they are not standardized provenance credentials.*

---

## Section C — Layer 2: Watermarking

**Q3. Does your pipeline embed imperceptible watermarks in AI-generated content that can be detected by automated tools?**

- [ ] **No Watermarking (Gap)** — Content is generated without any embedded watermark signal. **(0 points)**
- [ ] **Visible Watermark Only** — A visible label or overlay exists but no imperceptible machine-detectable watermark is embedded in the content data. **(8 points)**
- [ ] **Imperceptible Watermark (Compliant)** — Content embeds imperceptible watermarks that survive common transformations (compression, cropping) and can be detected by automated verification tools. **(16 points)**

> *Guidance: The source page is explicit that visible labelling alone is not enough for this control. The tool expects an imperceptible watermark layer that survives common transformations.*

---

## Section D — User-Facing Labelling

**Q4. Do you provide clear, visible labels to end users indicating content is AI-generated or that they are interacting with an AI system?**

- [ ] **No Labelling (Gap)** — Users are not informed that content is AI-generated or that they are interacting with AI. **(0 points)**
- [ ] **Buried Disclosure** — Disclosure exists in terms of service or footer text but is not prominent at the point of interaction or consumption. **(8 points)**
- [ ] **Prominent Labelling (Compliant)** — Clear, visible labelling at the point of interaction/consumption. Users are informed before or during engagement with AI-generated content. **(16 points)**

> *Guidance: The source logic treats point-of-interaction disclosure as the standard. Buried terms, footer text, or secondary pages are not treated as compliant.*

---

## Section E — Detection Capability

**Q5. Can you detect whether content in your pipeline was AI-generated (either your own or third-party content)?**

- [ ] **No Detection (Gap)** — We have no tools or processes to detect AI-generated content entering or leaving our pipeline. **(0 points)**
- [ ] **Manual Review** — Human reviewers inspect content but no automated detection tools are deployed. **(8 points)**
- [ ] **Automated Detection (Compliant)** — Automated tools verify watermarks and metadata. Detection is integrated into the content publishing workflow. **(16 points)**

> *Guidance: The tool does not treat manual review as sufficient for a fully mature posture. It expects automated verification integrated into publishing operations.*

---

## Section F — Organizational Process

**Q6. Do you have a documented internal process for AI content marking compliance, including roles, responsibilities, and audit procedures?**

- [ ] **No Process (Gap)** — No documented process exists. AI content marking is ad-hoc or non-existent. **(0 points)**
- [ ] **Informal Guidelines** — Some internal guidelines exist but they are not formally documented, assigned to owners, or audited. **(10 points)**
- [ ] **Documented Process (Compliant)** — Formal policy with assigned roles, documented procedures, and periodic audit/review schedule. **(20 points)**

> *Guidance: This question is not technical. It checks whether marking compliance is owned, documented, and reviewable rather than improvised.*

---

## Scoring Guide

This tool uses a **scope gate plus weighted readiness scoring**.

### Step 1 — Scope Gate

If **Q1 = None of the Above**, do **not** score Questions 2–6.

The tool returns:

**ARTICLE 50 MAY NOT APPLY**

With this exact result logic:

```text
Result: Your AI system does not appear to fall within Article 50 scope (no public-facing content generation, chatbot interaction, emotion recognition, or synthetic media).

Note: If your system's outputs are subsequently used in public-facing contexts by downstream users, Article 50 may still apply. Review periodically.
````

### Step 2 — Completion Rule

If Q1 is any in-scope content type, you must answer **all six questions**.

If any answer is missing, the tool stops and shows:

**Please answer all six questions.**

### Step 3 — Calculate the Score

For in-scope content types, score Questions 2–6 only.

* **Q2 Layer 1: Secured Metadata** = 0, 8, or 16
* **Q3 Layer 2: Watermarking** = 0, 8, or 16
* **Q4 User-Facing Labelling** = 0, 8, or 16
* **Q5 Detection Capability** = 0, 8, or 16
* **Q6 Organizational Process** = 0, 10, or 20

**Formula:**

```text
Total Score = Q2 + Q3 + Q4 + Q5 + Q6
Maximum Score = 84
Readiness % = round((Total Score / 84) × 100)
```

### Step 4 — PASS / GAP Logic

The interactive tool evaluates each scored control against these maximums:

* Layer 1: Secured Metadata → max 16
* Layer 2: Watermarking → max 16
* User-Facing Labelling → max 16
* Detection Capability → max 16
* Organizational Process → max 20

For each control:

* If the score is **less than the max**, it is listed as a **[GAP]**
* If the score **equals the max**, it is listed as a **[PASS]**

The exact labels used by the tool are:

* `Layer 1: Secured Metadata`
* `Layer 2: Watermarking`
* `User-Facing Labelling`
* `Detection Capability`
* `Organizational Process`

### Step 5 — Result Thresholds

#### A. Readiness = 100%

**Result:** `SCORE 100%: ARTICLE 50 READY`

**Report text used by the tool:**

```text
Your content pipeline demonstrates compliance with the two-layer marking approach.

Content Type: [selected content type]

Verified:
[PASS] Layer 1: Secured Metadata
[PASS] Layer 2: Watermarking
[PASS] User-Facing Labelling
[PASS] Detection Capability
[PASS] Organizational Process

Next: Maintain compliance through the final Code adoption (expected June 2026). Monitor for the proposed uniform EU icon requirement.
```

#### B. Readiness between 50% and 99%

**Result:** `SCORE [percentage]%: GAPS IN CONTENT MARKING`

**Report text used by the tool:**

```text
Your pipeline has partial coverage but critical gaps remain before the August 2026 deadline.

Content Type: [selected content type]

Gaps:
[GAP] ... (all controls scoring below their maximum)

Passes:
[PASS] ... (all controls at maximum)

Priority: Address each [GAP] item. The Code of Practice requires BOTH metadata AND watermarking layers, not either/or.
```

#### C. Readiness below 50%

**Result:** `SCORE [percentage]%: CRITICAL TRANSPARENCY GAPS`

**Report text used by the tool:**

```text
Your content pipeline lacks the mandatory marking infrastructure required by August 2026.

Content Type: [selected content type]

Critical Gaps:
[GAP] ... (all controls scoring below their maximum)

Immediate Action: Article 50 obligations are NOT delayed by the Digital Omnibus. Your deadline is August 2, 2026. Evaluate C2PA metadata integration, watermarking libraries, and user-facing labelling UI immediately.
```

### Content Type Labels Used in the Result

The interactive tool maps Q1 to these exact labels:

* **Chatbot / Conversational AI** → `Chatbot/Conversational AI (Art 50(1))`
* **Synthetic Media (Images, Audio, Video)** → `Synthetic Media (Art 50(4))`
* **AI-Generated Text on Public Interest** → `AI Text on Public Interest (Art 50(4))`
* **Emotion Recognition / Biometric Categorization** → `Emotion Recognition (Art 50(3))`

### Generated Output Structure

When the result is generated, the tool outputs this exact structure:

```text
Article 50 Content Marking Assessment
Date: [UTC timestamp]
Readiness: [percentage]% ([score]/84)

[result body]

Based on: Code of Practice Draft 2 (5 March 2026)
Generated via EU AI Compass
Execution: Local Browser (Zero Cloud Sync)
```

---

## What to Do Next

| If your result is...                                                       | Recommended next tool(s)                                                                                                                                  | Why                                                                                                                                                                        |
| -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Article 50 may not apply                                                   | [EU AI Act Quick Checker](01-quick-checker.md), [Detailed Applicability Scorer](02-detailed-applicability-scorer.md)                                      | Validate whether your system is truly out of Article 50 scope or whether downstream public-facing use still creates transparency duties.                                   |
| Gaps in metadata, watermarking, or disclosure                              | [Article 50 Transparency Validator](12-article-50-transparency-validator.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | The transparency validator gives a broader Article 50 architecture review, and the deployer assessment helps connect marking gaps to operational ownership and governance. |
| Detection capability or governance process is weak                         | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [ISO/NIST Gap Analyzer](15-iso-nist-gap-analyzer.md)                                            | Use these to test whether vendor dependencies and governance immaturity are the real reasons your marking controls are failing.                                            |
| User-facing content is still being published while controls are incomplete | [Human Oversight Log](06-human-oversight-log.md), [Article 26 Operations Scorer](07-article-26-operations-scorer.md)                                      | These help add operator accountability, logging, and operational discipline while you remediate transparency gaps.                                                         |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/ai-content-marking-checker.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*

```
```
