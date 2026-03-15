<!-- 02-detailed-applicability-scorer.md -->
# Detailed Applicability Scorer — Self-Assessment

> **Time:** ~8–12 minutes · **Questions:** 15 (portfolio mode) or 30 (single-system mode)  
> **EU AI Act References:** Articles 2, 3, 5, 6, 50; Annex I; Annex III  
> **Purpose:** Screen one AI system or a portfolio of AI systems for likely EU nexus, role, risk route, priority, and next action.

**🔗 [Try the interactive version →](https://euaicompass.com/eu-ai-act-applicability-checker.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool is a more operational applicability screen than a basic questionnaire. It helps you triage one AI system or a portfolio of systems, assign likely role, identify prohibited-practice indicators, flag Annex I and Annex III triggers, surface likely transparency or GPAI routes, and turn the result into a priority-ranked next action.

It is built for internal triage by CTOs, CISOs, product owners, compliance leads, procurement teams, and legal/compliance operations teams. The interactive version also exports a **local JSON snapshot** for single-system triage and **JSON/CSV portfolio outputs** for multiple systems; this Markdown version cannot generate those files, so use the interactive version when you need exportable records.

---

## Instructions

Choose **one mode**:

1. **Portfolio screening** if you want to screen multiple AI systems consistently and build a register.
2. **Single-system deeper triage** if you want a fuller assessment for one use case.

Use the answer options exactly as shown. Where the tool uses dropdowns, this Markdown version converts them into selectable options. For free-text fields, record your own text.

Then apply the matching scoring logic in the **Scoring Guide** section:

- Use the **Portfolio Scoring Guide** if you completed Path A.
- Use the **Single-System Scoring Guide** if you completed Path B.

For all Yes/No/Unclear questions, the interactive tool treats **Unclear / not yet confirmed** as a missing fact for scoring purposes.

---

## Section A — Path A: Portfolio Screening

This path mirrors the tool’s **Portfolio register**. Repeat it once per AI system or use case.

**P1. System ID**

- [ ] Enter free text (example: `AI-001`)

> *Guidance: Use an internal identifier so you can track the same use case across reviews.*

**P2. AI system or use case**

- [ ] Enter free text

> *Guidance: Use a concrete use-case name such as “Hiring screening model” rather than a generic tool label.*

**P3. Business function**

- [ ] Product / operations
- [ ] HR / people operations
- [ ] Customer service
- [ ] Sales / marketing
- [ ] Finance / credit / insurance
- [ ] Legal / compliance
- [ ] Safety / security
- [ ] IT / internal enablement
- [ ] Education / training
- [ ] Healthcare / life sciences
- [ ] Public service delivery
- [ ] Other

> *Guidance: This field is descriptive. It does not directly change the scoring formula.*

**P4. Owner**

- [ ] Enter free text

> *Guidance: Record the internal owner for follow-up and evidence collection.*

**P5. Vendor or model**

- [ ] Enter free text

> *Guidance: Record the external vendor, model family, or “in-house” so you can trace dependencies later.*

**P6. Role under the Act**

- [ ] Provider
- [ ] Deployer
- [ ] Importer
- [ ] Distributor
- [ ] Product manufacturer
- [ ] Authorized representative
- [ ] Mixed / unclear role

> *Guidance: The role does not drive the category in portfolio mode, but a missing role increases uncertainty and is shown in the trigger summary.*

**P7. Established in EU?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: One of the three EU nexus checks used by the scoring engine.*

**P8. Placed on EU market or put into service?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This tests whether the system is being made available or used in the EU market context.*

**P9. Output used in EU?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This captures extraterritorial relevance where the system or output affects the EU even if developed elsewhere.*

**P10. Any prohibited indicator?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This is a high-level prohibited-practice flag. If “Yes,” the tool immediately escalates the item to critical priority.*

**P11. Annex III area**

- [ ] No apparent Annex III trigger
- [ ] Unclear / needs review
- [ ] Biometrics
- [ ] Critical infrastructure
- [ ] Education and vocational training
- [ ] Employment and workers management
- [ ] Access to essential services
- [ ] Law enforcement
- [ ] Migration, asylum, border control
- [ ] Administration of justice / democratic processes

> *Guidance: This is a single-select high-risk screen in portfolio mode. It is used to determine whether an Annex III route is likely.*

**P12. Annex I regulated product route?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use “Yes” if the AI is embedded in or linked to a regulated product / safety-component route.*

**P13. GPAI provider?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This is narrower than “uses GPAI.” It asks whether your organization is acting on the provider side of a GPAI route.*

**P14. Transparency obligations likely?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use “Yes” where user-facing AI interaction or AI-generated/manipulated content likely triggers transparency duties.*

**P15. Confidence**

- [ ] High confidence
- [ ] Medium confidence
- [ ] Low confidence

> *Guidance: Confidence directly affects the score, open-item count, priority in some branches, and trigger text.*

**Optional portfolio note field**

Record **Notes or evidence assumptions** in free text if helpful. The interactive tool warns: do not enter personal data or customer-confidential information; use internal IDs and redacted summaries.

---

## Section B — Path B: Single-System Deeper Triage

This path mirrors the tool’s **Single-system deeper triage**.

### Section B1 — Organization and System Context

**S1. Organization name**

- [ ] Enter free text

> *Guidance: Administrative field only. It does not affect the scoring logic.*

**S2. Industry sector**

- [ ] Software / SaaS
- [ ] Financial services
- [ ] Healthcare
- [ ] Education
- [ ] Manufacturing
- [ ] Retail / ecommerce
- [ ] Telecoms / infrastructure
- [ ] Transport / mobility
- [ ] Public sector
- [ ] Energy / utilities
- [ ] Media / creative
- [ ] Other

> *Guidance: Descriptive context field. It does not directly alter the score.*

**S3. AI value chain role**

- [ ] Provider
- [ ] Deployer
- [ ] Importer
- [ ] Distributor
- [ ] Product manufacturer
- [ ] Authorized representative
- [ ] Mixed / unclear role

> *Guidance: A missing role increases the score and trigger list because the tool treats it as an unresolved fact.*

**S4. AI system or use case**

- [ ] Enter free text

> *Guidance: Use a specific system or use-case label.*

**S5. Deployment context**

- [ ] Internal-only workflow
- [ ] Employee-facing workflow
- [ ] Customer-facing workflow
- [ ] Public-facing service
- [ ] Critical / safety-relevant operations
- [ ] Support to public authority decisions
- [ ] Pilot / research / testing
- [ ] Other

> *Guidance: Descriptive context field. It does not directly change the branch logic.*

**S6. Business function**

- [ ] Product / operations
- [ ] HR / people operations
- [ ] Customer service
- [ ] Sales / marketing
- [ ] Finance / credit / insurance
- [ ] Legal / compliance
- [ ] Safety / security
- [ ] IT / internal enablement
- [ ] Education / training
- [ ] Healthcare / life sciences
- [ ] Public service delivery
- [ ] Other

> *Guidance: Descriptive context field. It does not directly change the branch logic.*

---

### Section B2 — EU Nexus

**S7. Established in the EU?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: One of the three EU nexus checks used by the engine.*

**S8. Places AI on EU market / puts into service in EU?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This captures market placement or operational deployment in the EU.*

**S9. AI output used in EU / affects people in EU?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This captures extraterritorial relevance based on downstream use or impact in the EU.*

---

### Section B3 — System Type and Transparency

**S10. GPAI model provider?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this when your organization is acting as the provider of a GPAI model.*

**S11. Uses a GPAI model as core component?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This is broader than S10. Use “Yes” if the system materially depends on a GPAI model even if you are not the provider.*

**S12. Embedded in regulated product / safety component?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This is the Annex I route check.*

**S13. If yes, product domain**

- [ ] Not using Annex I route
- [ ] Medical devices
- [ ] In vitro diagnostics
- [ ] Machinery
- [ ] Toys
- [ ] Radio equipment
- [ ] Motor vehicles
- [ ] Civil aviation
- [ ] Marine / rail
- [ ] Protective equipment
- [ ] Gas / pressure equipment
- [ ] Other regulated product

> *Guidance: In the interactive tool, this field is enabled only when S12 is Yes or Unclear. If Annex I is selected but no domain is chosen, the open-item count increases.*

**S14. Transparency obligations likely?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use “Yes” if the system is likely to require user-facing notices or synthetic-content disclosures.*

---

### Section B4 — Prohibited Practices Screening

**S15. Manipulative or deceptive techniques causing significant harm?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: A “Yes” here is treated as a prohibited-practice indicator and drives an immediate critical result.*

**S16. Exploits vulnerabilities causing significant harm?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: This covers exploitation of vulnerable persons or groups where significant harm may result.*

**S17. Social scoring with detrimental treatment in unrelated context?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: The tool treats a “Yes” as a prohibited-practice indicator.*

**S18. Biometric categorisation to infer sensitive traits?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: The tool treats a “Yes” as a prohibited-practice indicator.*

**S19. Emotion recognition in workplace or education?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: The tool treats a “Yes” as a prohibited-practice indicator unless a lawful exception exists outside this screen.*

**S20. Untargeted scraping of facial images?**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: The tool treats a “Yes” as a prohibited-practice indicator.*

---

### Section B5 — High-Risk Annex III Screening

**S21. Biometrics**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this if the system appears to fall within an Annex III biometric route.*

**S22. Critical infrastructure**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this for infrastructure-related AI use cases with safety or service significance.*

**S23. Education and vocational training**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this for admissions, assessment, monitoring, or similar education-related routes.*

**S24. Employment and workers management**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this for hiring, screening, performance, allocation, or worker-management routes.*

**S25. Access to essential services**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this for credit, insurance, benefits, emergency, or similar essential-service routes.*

**S26. Law enforcement**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this for law-enforcement-related AI use cases.*

**S27. Migration, asylum, border control**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this for migration or border-control routes.*

**S28. Administration of justice / democratic processes**

- [ ] Yes
- [ ] No
- [ ] Unclear / not yet confirmed

> *Guidance: Use this for justice-system or democratic-process routes.*

---

### Section B6 — Confidence and Assumptions

**S29. Confidence level**

- [ ] High confidence
- [ ] Medium confidence
- [ ] Low confidence

> *Guidance: Confidence directly changes score, trigger text, open items, and sometimes priority.*

**S30. Timeline basis**

- [ ] Already live / in production
- [ ] Planned launch within 90 days
- [ ] Planned launch within 6 months
- [ ] Pilot / limited release
- [ ] Exploratory only

> *Guidance: Timeline basis changes the milestone and recommended start-by dates using the tool’s schedule logic.*

**Optional single-system note field**

Record **Notes / evidence / assumptions** in free text if helpful. The interactive tool recommends keeping this operational and redacted and not inputting personal data.

---

## Scoring Guide

This tool uses a **rule-based classification engine** plus a calculated **audit score**, **open-item count**, and **timing estimate**. There are **two separate scoring models**, one for portfolio mode and one for single-system mode.

---

### Portfolio Scoring Guide

#### 1) Definitions used by the portfolio engine

**EU nexus helper (`n`)**

Look at P7, P8, and P9:

- `n.y = true` if **any** of the three answers is **Yes**
- `n.n = true` if **all three** answers are **No**
- `n.u = true` if **any** of the three answers is blank or **Unclear / not yet confirmed**

**Derived route flags**

- `pro = true` if **P10 = Yes**
- `a1 = true` if **P12 = Yes**
- `a3 = true` if **P11** is any selected Annex III area other than:
  - No apparent Annex III trigger
  - Unclear / needs review
- `tr = true` if **P14 = Yes**
- `gp = true` if **P13 = Yes**
- `low = true` if **P15 = Low confidence**
- `med = true` if **P15 = Medium confidence**

**Missing-field count (`miss`)**

Count how many of the following are blank or **Unclear / not yet confirmed**:

- P6 Role
- P7 Established in EU?
- P8 Placed on EU market or put into service?
- P9 Output used in EU?
- P10 Any prohibited indicator?
- P11 Annex III area
- P12 Annex I regulated product route?
- P14 Transparency obligations likely?
- P15 Confidence

#### 2) Category and priority logic — in exact order

Apply these rules in order. The first matching rule sets the main result.

**Rule 1 — Potential prohibited practice**

If `pro = true`:

- **Applicability:** Likely in scope
- **Category:** Potential prohibited practice
- **Priority:** Critical
- **Next action:** Pause rollout and escalate to legal/compliance immediately.

**Key trigger text:**  
`A prohibited-practice indicator was marked yes.`

---

**Rule 2 — No clear EU nexus**

If `n.y = false` and `n.n = true`:

- **Applicability:** Likely out of scope
- **Category:**  
  - `No current EU nexus; monitor GPAI route` if `gp = true`
  - otherwise `No clear EU nexus`
- **Priority:**  
  - Medium if `gp = true`
  - otherwise Low
- **Next action:** Keep a dated record and rescreen if geography or downstream use changes.

**Key trigger text:**  
`No EU establishment, market placement, or EU output use was confirmed.`

---

**Rule 3 — Likely high-risk (Annex I)**

If `a1 = true`:

- **Applicability:** Likely in scope
- **Category:** Likely high-risk (Annex I)
- **Priority:**  
  - Critical if `low = true`
  - otherwise High
- **Next action:** Start Annex I evidence gathering and assign a product/safety owner.

**Key trigger text:**  
`Annex I regulated-product route was marked yes.`

---

**Rule 4 — Likely high-risk (Annex III)**

If `a3 = true`:

- **Applicability:** Likely in scope
- **Category:** Likely high-risk (Annex III)
- **Priority:** High
- **Next action:** Move this system into a deeper control assessment and evidence review.

**Key trigger text:**  
`Annex III area selected: [selected area]`

---

**Rule 5 — GPAI / transparency route**

If `tr = true` or `gp = true`:

- **Applicability:** Likely in scope
- **Category:**  
  - `GPAI / transparency route` if `gp = true`
  - otherwise `Transparency route`
- **Priority:**  
  - High if `low = true`
  - otherwise Medium
- **Next action:** Prepare notices, confirm role allocation, and validate GPAI dependencies.

**Key trigger text:**  
- `A GPAI provider route was indicated.` if `gp = true`
- `Transparency obligations were marked likely.` otherwise

---

**Rule 6 — Lower-risk route pending deeper facts**

If `n.y = true` and none of the earlier rules matched:

- **Applicability:** Likely in scope
- **Category:** Lower-risk route pending deeper facts
- **Priority:**  
  - Medium if `low = true`
  - otherwise Low
- **Next action:** Confirm role boundaries and keep this item on a rescreen list.

**Key trigger text:**  
`At least one EU nexus answer was yes.`

---

**Rule 7 — Needs more facts**

If none of the above rules matched:

- **Applicability:** Unclear
- **Category:** Needs more facts
- **Priority:** Medium
- **Next action:** Complete missing screening fields and rerun.

**Key trigger text:**  
`EU nexus facts remain incomplete.`

#### 3) Additional trigger text appended by the tool

After the main rule above, append these if applicable:

- If **P6 Role** is blank → `Role not selected.`
- If `med = true` → `Confidence is medium.`
- If `low = true` → `Confidence is low.`

#### 4) Open-item formula

Portfolio open items are calculated as:

`openItems = miss + routeAdder + confidenceAdder`

Where:

- `routeAdder = 4` if `pro = true`
- else `routeAdder = 4` if `a1 = true`
- else `routeAdder = 3` if `a3 = true`
- else `routeAdder = 2` if `tr = true` or `gp = true`
- else `routeAdder = 1` if `n.y = true`
- else `routeAdder = 0`

And:

- `confidenceAdder = 2` if `low = true`
- `confidenceAdder = 1` if `med = true`
- `confidenceAdder = 0` otherwise

#### 5) Audit score formula

If all of the following are true:

- `n.y = false`
- `n.n = true`
- `pro = false`
- `a1 = false`
- `a3 = false`
- `tr = false`
- `gp = false`

then:

`score = 10`

Otherwise:

`score = min(100, 8 + nexusPoints + prohibitedPoints + annexIPoints + annexIIIPoints + transparencyPoints + gpaiPoints + confidencePoints + roleGapPoints)`

Where:

- `nexusPoints = 16` if `n.y = true`
- `nexusPoints = 8` if `n.y = false` and `n.u = true`
- `nexusPoints = 0` otherwise

- `prohibitedPoints = 45` if `pro = true`, else `0`
- `annexIPoints = 30` if `a1 = true`, else `0`
- `annexIIIPoints = 22` if `a3 = true`, else `0`
- `transparencyPoints = 8` if `tr = true`, else `0`
- `gpaiPoints = 10` if `gp = true`, else `0`
- `confidencePoints = 5` if `med = true`, `10` if `low = true`, else `0`
- `roleGapPoints = 3` if **P6 Role** is blank, else `0`

#### 6) Milestone, effort, and recommended start-by

Portfolio mode uses the generic timing matrix below.

If **Applicability = Likely out of scope**:

- **Estimated milestone:** On material change
- **Estimated effort:** <1 day
- **Recommended start-by:** Only if EU facts change

Otherwise use **Priority**:

| Priority | Estimated milestone | Estimated effort | Recommended start-by |
|---|---|---|---|
| Critical | Within 7 days | 2–4 weeks | Immediately |
| High | Within 30 days | 1–3 weeks | This week |
| Medium | Within 60 days | 2–5 days | Within 2 weeks |
| Low | Within 90 days | 1–2 days | This month |

---

### Single-System Scoring Guide

#### 1) Definitions used by the single-system engine

**EU nexus helper (`n`)**

Look at S7, S8, and S9:

- `n.y = true` if **any** of the three answers is **Yes**
- `n.n = true` if **all three** answers are **No**
- `n.u = true` if **any** of the three answers is blank or **Unclear / not yet confirmed**

**Prohibited-practice list (`pros`)**

Add one prohibited indicator for each of the following questions answered **Yes**:

- S15 Manipulative or deceptive techniques
- S16 Exploitation of vulnerability
- S17 Social scoring
- S18 Sensitive-trait biometric categorisation
- S19 Emotion recognition in workplace or education
- S20 Untargeted facial-image scraping

**Annex III list (`a3`)**

Add one Annex III category for each of the following answered **Yes**:

- S21 Biometrics
- S22 Critical infrastructure
- S23 Education and vocational training
- S24 Employment and workers management
- S25 Access to essential services
- S26 Law enforcement
- S27 Migration, asylum, border control
- S28 Administration of justice / democratic processes

**Derived route flags**

- `a1 = true` if **S12 = Yes**
- `tr = true` if **S14 = Yes**
- `gp = true` if **S10 = Yes** or **S11 = Yes**
- `low = true` if **S29 = Low confidence**
- `med = true` if **S29 = Medium confidence**

**Missing-field count (`miss`)**

Count how many of the following are blank or **Unclear / not yet confirmed**:

- S3 Role
- S7 Established in the EU?
- S8 Places AI on EU market / puts into service in EU?
- S9 AI output used in EU / affects people in EU?
- S10 GPAI model provider?
- S11 Uses a GPAI model as core component?
- S12 Embedded in regulated product / safety component?
- S14 Transparency obligations likely?
- S29 Confidence level
- S30 Timeline basis
- S15–S20 all prohibited-practice questions
- S21–S28 all Annex III questions

#### 2) Category and priority logic — in exact order

Apply these rules in order. The first matching rule sets the main result.

**Rule 1 — Potential prohibited practice**

If `pros` contains one or more selected prohibited indicators:

- **Applicability:** Likely in scope
- **Category:** Potential prohibited practice
- **Priority:** Critical
- **Recommendation:** Freeze deployment or expansion, preserve evidence, and obtain legal review.

**Key trigger text:**  
`Potential prohibited-practice indicators: [list].`

---

**Rule 2 — No clear EU nexus**

If `n.y = false` and `n.n = true`:

- **Applicability:** Likely out of scope
- **Category:**  
  - `No current EU nexus; monitor GPAI route` if `gp = true`
  - otherwise `No clear EU nexus`
- **Priority:**  
  - Medium if `gp = true`
  - otherwise Low
- **Recommendation:** Document why EU nexus is absent and rescreen before EU rollout or downstream EU use.

**Key trigger text:**  
`All EU nexus questions are currently no.`

---

**Rule 3 — Likely high-risk (Annex I)**

If `a1 = true`:

- **Applicability:** Likely in scope
- **Category:** Likely high-risk (Annex I)
- **Priority:**  
  - Critical if `low = true`
  - otherwise High
- **Recommendation:** Start Annex I product-route assessment and collect technical documentation.

**Key trigger text:**  
`Annex I route selected: [selected domain or “Domain not yet specified”]`

---

**Rule 4 — Likely high-risk (Annex III)**

If `a3` contains one or more selected Annex III categories:

- **Applicability:** Likely in scope
- **Category:** Likely high-risk (Annex III)
- **Priority:** High
- **Recommendation:** Escalate into a deeper control assessment and validate the Annex III use case.

**Key trigger text:**  
`Annex III categories flagged: [list].`

---

**Rule 5 — GPAI / transparency route**

If `tr = true` or `gp = true`:

- **Applicability:** Likely in scope
- **Category:**  
  - `GPAI / transparency route` if `gp = true`
  - otherwise `Transparency route`
- **Priority:**  
  - High if `low = true`
  - otherwise Medium
- **Recommendation:** Prepare notices, synthetic-content disclosures if relevant, and clarify responsibilities.

**Key trigger text:**  
- `A GPAI dependency was indicated.` if `gp = true`
- `Transparency obligations were marked likely.` otherwise

---

**Rule 6 — Lower-risk route pending deeper facts**

If `n.y = true` and none of the earlier rules matched:

- **Applicability:** Likely in scope
- **Category:** Lower-risk route pending deeper facts
- **Priority:**  
  - Medium if `low = true`
  - otherwise Low
- **Recommendation:** Confirm the legal role, note the use-case boundary, and retain screening evidence.

**Key trigger text:**  
`At least one EU nexus answer was yes, but no prohibited or high-risk route was confirmed.`

---

**Rule 7 — Needs more facts**

If none of the above rules matched:

- **Applicability:** Unclear
- **Category:** Needs more facts
- **Priority:** Medium
- **Recommendation:** Complete the missing fields and rerun before relying on the output.

**Key trigger text:**  
`Too many key facts remain blank or unclear.`

#### 3) Additional trigger text appended by the tool

After the main rule above, append these if applicable:

- If **S12** is blank or Unclear **and** (`n.y = true` or `gp = true` or `a3` contains one or more items) →  
  `Annex I route is still unclear.`

- If **S14** is blank or Unclear **and** (`gp = true` or `n.y = true`) →  
  `Transparency obligations are still unclear.`

- If **S3 Role** is blank →  
  `Role not selected.`

- If `med = true` →  
  `Confidence is medium.`

- If `low = true` →  
  `Confidence is low.`

- If **S30 Timeline basis** is set →  
  `Timeline basis: [selected timeline].`

#### 4) Open-item formula

Single-system open items are calculated as:

`openItems = miss + annexIDomainGap + routeAdder + confidenceAdder`

Where:

- `annexIDomainGap = 1` if `a1 = true` and:
  - S13 is blank, or
  - S13 = Not using Annex I route

Otherwise `annexIDomainGap = 0`

And:

- `routeAdder = 4` if `pros` contains one or more items
- else `routeAdder = 4` if `a1 = true`
- else `routeAdder = 4` if `a3` contains one or more items
- else `routeAdder = 2` if `tr = true` or `gp = true`
- else `routeAdder = 1` if `n.y = true`
- else `routeAdder = 0`

And:

- `confidenceAdder = 2` if `low = true`
- `confidenceAdder = 1` if `med = true`
- `confidenceAdder = 0` otherwise

#### 5) Audit score formula

If all of the following are true:

- `n.y = false`
- `n.n = true`
- `pros` contains no items
- `a1 = false`
- `a3` contains no items
- `tr = false`
- `gp = false`

then:

`score = 10`

Otherwise:

`score = min(100, 12 + nexusPoints + prohibitedPoints + annexIPoints + annexIIIPoints + transparencyPoints + gpaiPoints + confidencePoints + roleGapPoints)`

Where:

- `nexusPoints = 18` if `n.y = true`
- `nexusPoints = 10` if `n.y = false` and `n.u = true`
- `nexusPoints = 0` otherwise

- `prohibitedPoints = 18 × number of prohibited indicators selected in S15–S20`
- `annexIPoints = 28` if `a1 = true`, else `0`
- `annexIIIPoints = min(24, 8 × number of Annex III categories selected in S21–S28)`
- `transparencyPoints = 8` if `tr = true`, else `0`
- `gpaiPoints = 12` if `gp = true`, else `0`
- `confidencePoints = 5` if `med = true`, `10` if `low = true`, else `0`
- `roleGapPoints = 4` if **S3 Role** is blank, else `0`

#### 6) Milestone, effort, and recommended start-by

The single-system path uses the same base timing matrix as the portfolio path, then modifies it for the chosen timeline basis.

If **Applicability = Likely out of scope**:

- **Estimated milestone:** On material change
- **Estimated effort:** <1 day
- **Recommended start-by:** Only if EU facts change

Otherwise start with the base matrix below:

| Priority | Base estimated milestone | Base estimated effort | Base recommended start-by |
|---|---|---|---|
| Critical | Within 7 days | 2–4 weeks | Immediately |
| High | Within 30 days | 1–3 weeks | This week |
| Medium | Within 60 days | 2–5 days | Within 2 weeks |
| Low | Within 90 days | 1–2 days | This month |

Then apply timeline overrides exactly as the interactive tool does:

- If **S30 = Exploratory only** and **Priority = Low or Medium**:
  - **Estimated milestone:** Before pilot approval
  - **Recommended start-by:** Before build continues
  - **Estimated effort:** unchanged from the base matrix

- If **S30 = Planned launch within 90 days** and **Priority is not Critical**:
  - **Estimated milestone:** Before launch freeze
  - **Recommended start-by:** This week
  - **Estimated effort:** unchanged from the base matrix

- If **S30 = Planned launch within 6 months** and **Priority is not Critical**:
  - **Estimated milestone:** Before launch plan sign-off
  - **Recommended start-by:** Within this quarter
  - **Estimated effort:** unchanged from the base matrix

No timeline override is applied for:

- Already live / in production
- Pilot / limited release
- Critical-priority cases under the 90-day or 6-month launch options

---

## What to Do Next

| If your result is... | Recommended next tool(s) | Why |
|---|---|---|
| Potential prohibited practice or likely high-risk | [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md), [Deployer Obligation Self-Assessment](13-deployer-obligation-assessment.md) | Use the exemption tool to test whether an Annex III route may narrow out of high-risk status, and use the deployer assessment to translate the result into operational obligations and ownership. |
| GPAI / transparency route | [Article 50 Transparency Validator](12-article-50-transparency-validator.md), [AI Content Marking Compliance Checker](14-ai-content-marking-checker.md) | Use these tools to validate disclosure, labelling, and synthetic-content handling obligations triggered by user-facing or content-generating systems. |
| Lower-risk route pending deeper facts | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [ISO/NIST Gap Analyzer](15-iso-nist-gap-analyzer.md) | If the classification is still fact-dependent, tighten vendor evidence collection and governance maturity before relying on the screening result. |
| Confidence is low or facts are incomplete | [Human Oversight Log](06-human-oversight-log.md), [Shadow AI Discovery Protocol](16-shadow-ai-discovery-protocol.md) | These tools help close evidence gaps, clarify real deployment practices, and reduce false confidence in the initial screening result. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/eu-ai-act-applicability-checker.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*