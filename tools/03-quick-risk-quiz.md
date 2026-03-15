<!-- 03-quick-risk-quiz.md -->
# Quick Risk Quiz — Self-Assessment

> **Time:** ~2 minutes · **Questions:** 5  
> **EU AI Act References:** Articles 5, 6(1), 8–15, 50; Annex I; Annex III; Chapter V  
> **Purpose:** Rapid first-pass classification of whether an AI system is likely prohibited, high-risk, subject to GPAI obligations, subject to transparency obligations, likely minimal risk, or likely outside scope.

**🔗 [Try the interactive version →](https://euaicompass.com/quiz.html)** — auto-scored, browser-only, zero data collection.

---

## What This Assesses

This tool is a short preliminary EU AI Act classification quiz for SMEs and other organizations that need an immediate first-pass answer. It evaluates EU nexus, system type, product-safety linkage, prohibited-practice indicators, and organization size, then maps the answers to a single likely classification and a short action list.

It is most useful for founders, CTOs, CISOs, product owners, compliance officers, procurement teams, and legal operations staff who need a fast triage result before using a deeper assessment.

---

## Instructions

Answer each question by selecting **one option**.

Use the **Scoring Guide** exactly in the order shown. This tool is **not point-based**. It uses a strict decision sequence. The **first matching rule** determines the result.

For the prohibited-practices question, the interactive tool technically allows one answer only. In this Markdown version, select the option that best matches the strongest prohibited-practice indicator present. If none apply, select **None of the above**.

---

## Questions

**Q1. Does your AI system have a connection to the EU market?**

- [ ] We develop/provide AI and place it on the EU market
- [ ] We use/deploy AI systems within the EU
- [ ] We're outside the EU, but our AI's output is used in the EU
- [ ] No connection — we don't operate in or affect the EU market

> *Guidance: The tool uses this as the EU nexus gate. If there is no EU nexus, the system is classified as likely out of scope.*

---

**Q2. What best describes your AI system's primary function?**

- [ ] Biometric identification, emotion recognition, or categorization
- [ ] Critical infrastructure, employment, education, or law enforcement
- [ ] General-purpose AI model (foundation model)
- [ ] Content generation, chatbot, recommendation, or automation
- [ ] Internal tool, analytics, spam filter, or other

> *Guidance: This is the core classification question. The tool treats biometrics and certain sectoral uses as likely Annex III high-risk, GPAI models as Chapter V cases, and content/chatbot systems as likely Article 50 transparency cases.*

---

**Q3. Is your AI system a safety component of a regulated product?**

- [ ] Yes — it's part of a medical device, vehicle, machinery, or similar regulated product
- [ ] No — it's a standalone software application or service
- [ ] Not sure

> *Guidance: If yes, the tool routes the system into the Annex I / Article 6(1) high-risk path. “Not sure” does not create a separate result category; it simply means the high-risk Annex I route is not confirmed by this quiz.*

---

**Q4. Does your AI system do any of the following?**

- [ ] Scores or rates people based on social behavior (by/for public authorities)
- [ ] Uses subliminal or manipulative techniques to distort behavior
- [ ] Scrapes facial images from the internet/CCTV to build databases
- [ ] Infers emotions in workplaces or schools (non-medical)
- [ ] None of the above

> *Guidance: The tool treats any answer other than “None of the above” as a prohibited-practice trigger under Article 5 and immediately escalates the result to the highest-severity outcome.*

---

**Q5. What is the size of your organization?**

- [ ] SME — fewer than 250 employees
- [ ] Startup — less than 5 years old, under 250 employees
- [ ] Enterprise — 250+ employees
- [ ] Public authority or government body

> *Guidance: This question does not change the core classification. It only adds support messaging for SMEs and startups.*

---

## Scoring Guide

This tool uses a **rule-based result engine**, not a point score.

Apply the rules below **in order**. The **first matching rule** determines the result.

### Rule 1 — Prohibited

If **Q4** is **anything other than “None of the above”**, the result is:

**PROHIBITED**

**Displayed headline:**  
*Your AI system likely falls under PROHIBITED practices*

**Result explanation used by the tool:**  
The system appears to engage in practices banned under Article 5. The tool states these prohibitions have been in effect since **2 February 2025** and warns of fines up to **€35 million or 7% of worldwide annual turnover**.

**Key obligations shown by the tool:**

- Immediately cease the prohibited practice
- Conduct a full legal review with qualified counsel
- Document all AI systems for compliance audit trail
- Assess whether any exemptions apply (the tool notes narrow law-enforcement exceptions for biometric identification)

**Urgency shown by the tool:**  
**CRITICAL — Action required now**

---

### Rule 2 — Likely out of scope

If **Q1 = No connection — we don't operate in or affect the EU market**, the result is:

**LIKELY OUT OF SCOPE**

**Displayed headline:**  
*Your AI system is likely outside EU AI Act scope*

**Result explanation used by the tool:**  
The system does not appear to have a connection to the EU market. The tool states the Act applies to providers placing AI on the EU market, deployers in the EU, and providers/deployers whose AI output is used in the EU.

**Key obligations shown by the tool:**

- Monitor for changes — if you later enter the EU market, the Act applies
- Consider voluntary compliance as a competitive advantage
- Track AI literacy best practices regardless of jurisdiction

**Urgency shown by the tool:**  
**LOW — Monitor only**

---

### Rule 3 — High-risk via regulated product / safety component

If **Q3 = Yes — it's part of a medical device, vehicle, machinery, or similar regulated product**, the result is:

**HIGH-RISK**

**Displayed headline:**  
*Your AI system is likely classified as HIGH-RISK*

**Result explanation used by the tool:**  
The system is a safety component of a regulated product under Annex I. The tool says this triggers **Article 6(1)**, with compliance required by **2 August 2027**, and states that full conformity assessment is mandatory before market placement.

**Key obligations shown by the tool:**

- Implement risk management system (Article 9)
- Ensure data governance (Article 10)
- Create technical documentation (Article 11)
- Implement logging/record-keeping (Article 12)
- Provide transparency info to deployers (Article 13)
- Enable human oversight (Article 14)
- Ensure accuracy, robustness, cybersecurity (Article 15)
- Complete conformity assessment before market placement

**Urgency shown by the tool:**  
**HIGH — Deadline: 2 August 2027**

---

### Rule 4 — High-risk via Annex III use case

If **Q2** is either of the following:

- **Biometric identification, emotion recognition, or categorization**
- **Critical infrastructure, employment, education, or law enforcement**

the result is:

**HIGH-RISK**

**Displayed headline:**  
*Your AI system is likely classified as HIGH-RISK*

**Result explanation used by the tool:**  
The system falls within use-case categories listed in Annex III. The tool states that high-risk AI systems must comply with strict requirements under **Articles 8–15**, with enforcement starting **2 August 2026**. It also notes that the Digital Omnibus proposes a fixed extension to **2 December 2027**, but says this is **not yet adopted law** and instructs users to plan for **August 2026**.

**Key obligations shown by the tool:**

- Implement risk management system (Article 9)
- Ensure data governance (Article 10)
- Create technical documentation (Article 11)
- Implement logging/record-keeping (Article 12)
- Provide transparency info to deployers (Article 13)
- Enable human oversight (Article 14)
- Ensure accuracy, robustness, cybersecurity (Article 15)
- Complete conformity assessment before market placement
- Register in EU database of high-risk AI systems

**Urgency shown by the tool:**  
**HIGH — Deadline: 2 August 2026**

---

### Rule 5 — GPAI obligations

If **Q2 = General-purpose AI model (foundation model)**, the result is:

**GPAI OBLIGATIONS**

**Displayed headline:**  
*Your AI model likely has GPAI-specific obligations*

**Result explanation used by the tool:**  
The tool states that general-purpose AI models have dedicated requirements under **Chapter V**, that GPAI rules have applied since **2 August 2025**, and that additional obligations apply where a model presents systemic risk, with the tool using **trained with >10²⁵ FLOPs** as the example threshold.

**Key obligations shown by the tool:**

- Maintain and provide technical documentation
- Provide information to downstream providers
- Comply with copyright law (text/data mining opt-out)
- Publish sufficiently detailed summary of training data
- If systemic risk: model evaluations, adversarial testing, serious incident reporting, cybersecurity

**Urgency shown by the tool:**  
**MEDIUM-HIGH — Already in effect since Aug 2025**

---

### Rule 6 — Transparency obligations

If **Q2 = Content generation, chatbot, recommendation, or automation**, the result is:

**TRANSPARENCY OBLIGATIONS**

**Displayed headline:**  
*Your AI system likely has TRANSPARENCY obligations*

**Result explanation used by the tool:**  
The tool states that chatbots, content generators, and deepfake tools must comply with **Article 50** transparency requirements. Users must be informed they are interacting with AI, and AI-generated content must be appropriately labelled.

**Key obligations shown by the tool:**

- Inform users they are interacting with an AI system
- Label AI-generated content (especially deepfakes)
- If emotion recognition or biometric categorization: disclose function to affected persons
- If generating text on public interest matters: label as AI-generated

**Urgency shown by the tool:**  
**MEDIUM — Deadline: 2 August 2026**

---

### Rule 7 — Minimal risk

If none of the rules above apply, the result is:

**MINIMAL RISK**

This occurs in practice when:

- **Q4 = None of the above**
- **Q1** shows an EU nexus
- **Q3** is not a confirmed regulated-product safety component
- **Q2 = Internal tool, analytics, spam filter, or other**

**Displayed headline:**  
*Your AI system is likely classified as MINIMAL RISK*

**Result explanation used by the tool:**  
The system does not appear to fall into prohibited, high-risk, or transparency categories. The tool states that no specific mandatory obligations apply, though voluntary codes of conduct are encouraged.

**Key obligations shown by the tool:**

- No mandatory obligations under the EU AI Act
- Consider adopting voluntary codes of conduct
- Ensure AI literacy for staff (Article 4 applies to all)
- Monitor regulatory developments — classifications may change

**Urgency shown by the tool:**  
**LOW — Voluntary compliance recommended**

---

### SME / Startup Support Note

After the main result is calculated, the tool adds an additional support note if **Q5** is either:

- **SME — fewer than 250 employees**
- **Startup — less than 5 years old, under 250 employees**

The support note says the EU AI Act provides:

- priority access to regulatory sandboxes
- reduced conformity assessment fees
- dedicated communication channels
- tailored awareness activities

If **Q5 = Startup**, the tool adds that startups under 5 years old qualify for **additional priority measures**.

This support note **does not change the classification**.

---

## What to Do Next

| If your result is... | Recommended next tool(s) | Why |
|---|---|---|
| High-risk or unclear high-risk route | [Detailed Applicability Scorer](02-detailed-applicability-scorer.md), [Article 6(3) Exemption Generator](04-article-6-exemption-generator.md) | The quiz is only a preliminary screen. Use the detailed scorer for a fuller classification and the Article 6(3) tool if you need to test whether an Annex III use case might narrow out of the high-risk category. |
| Transparency obligations | [Article 50 Transparency Validator](12-article-50-transparency-validator.md), [AI Content Marking Compliance Checker](14-ai-content-marking-checker.md) | These tools help turn the quiz result into concrete disclosure and labelling checks for user interaction and generated content. |
| GPAI obligations | [AI Vendor Risk Screener](17-ai-vendor-risk-screener.md), [ISO/NIST Gap Analyzer](15-iso-nist-gap-analyzer.md) | The GPAI path requires documentation, downstream information-sharing, and governance maturity. These tools help assess vendor/model dependencies and broader control readiness. |
| Minimal risk or likely out of scope | [EU AI Act Quick Checker](01-quick-checker.md), [Shadow AI Discovery Protocol](16-shadow-ai-discovery-protocol.md) | Use the 12-question checker for a broader classification pass, and use the shadow AI tool if you need to confirm whether the real deployment picture is more complex than the initial quiz suggests. |

---

## Disclaimer

This self-assessment is for educational and informational purposes only. It does not constitute legal advice. The EU AI Act is complex and fact-specific — your actual obligations depend on the specific characteristics of your AI system, your organizational role, and applicable national implementing legislation. Consult qualified legal counsel for definitive compliance guidance.

---

**🔗 [Try the interactive version of this tool →](https://euaicompass.com/quiz.html)**

*Built by [Move78 International Limited](https://move78int.com) · [EU AI Compass](https://euaicompass.com) · [All 28 Tools →](../README.md)*