# Regulatory Source Register — LendWise AI Governance Program

**Document status:** Initial source register  
**Last reviewed:** 10 October 2026  
**Scope:** EU and India AI governance, privacy, risk management and assurance  
**Organisation:** LendWise Financial Services Ltd. — fictional training case

## 1. Purpose

This register identifies the authoritative legal texts, official regulatory guidance and voluntary governance frameworks used in the LendWise AI Governance Program.

It supports traceability between an assessment conclusion and the source used to develop it. It does not establish that a system complies with a regulation or that a particular provision applies without further analysis of the facts.

## 2. Source hierarchy

Sources are categorised as follows:

- **Binding legislation:** Applicable laws and regulations, interpreted in their legal and factual context.
- **Official guidance:** Regulatory or government publications that explain or guide interpretation and implementation.
- **Voluntary frameworks and standards:** Resources used to structure governance, risk management, assurance and continual improvement. They do not automatically replace legal obligations.

Where sources differ in legal status, the applicable legislation takes precedence over non-binding guidance, subject to relevant judicial interpretation and other applicable law.

## 3. Primary source register

| ID | Source | Type | Intended use in this programme |
|---|---|---|---|
| SRC-001 | EU AI Act — Regulation (EU) 2024/1689, consolidated text | Binding EU legislation | Prohibited practices, high-risk classification, transparency, governance and system obligations |
| SRC-002 | GDPR — Regulation (EU) 2016/679 | Binding EU legislation | Personal-data processing, profiling, automated decisions, transparency and data-subject rights |
| SRC-003 | European Commission AI Act Service Desk — Annex III | Official guidance resource | Navigate and interpret listed high-risk use cases alongside the legal text |
| SRC-004 | European Commission guidelines on prohibited AI practices | Official guidance | Analyse potential prohibited practices, including workplace emotion recognition |
| SRC-005 | India Digital Personal Data Protection Act, 2023 | Indian legislation | Assess personal-data protection obligations in the Indian operating context, subject to commencement |
| SRC-006 | India Digital Personal Data Protection Rules, 2025 and official commencement notifications | Indian rules and official notifications | Assess implementation details and phased commencement of relevant provisions |
| SRC-007 | NIST AI Risk Management Framework 1.0 | Voluntary framework | Structure AI governance, context mapping, measurement and risk management |
| SRC-008 | ISO/IEC 42001:2023 | International standard | Reference for an AI management system and continual improvement |

## 4. Source details and application

### SRC-001 — EU Artificial Intelligence Act

**Official source:**  
https://eur-lex.europa.eu/eli/reg/2024/1689/2026-07-27/eng

**Relevant provisions for the LendWise case study:**

- Article 5 — prohibited AI practices.
- Article 6 — classification rules for high-risk AI systems.
- Annex III, Section 4(a) — recruitment and selection.
- Annex III, Section 5(b) — creditworthiness assessment of natural persons and credit scoring, subject to the provision's scope and exclusions.
- Annex III, Section 1(a) and Section 1(c) — relevant biometric identification and emotion-recognition use cases.
- Article 50 — transparency obligations for certain AI systems.
- Article 14 — human oversight requirements for high-risk AI systems, where applicable.

**Portfolio application:** Establish a documented legal classification for each system based on its intended purpose, actual functionality and deployment context.

**Important limitation:** Enterprise risk ratings such as High or Critical are internal governance ratings, not EU AI Act classifications. A high-risk classification or prohibited-practice conclusion must be supported by the relevant legal elements and facts.

### SRC-002 — General Data Protection Regulation

**Official source:**  
https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng

**Relevant provisions:**

- Article 5 — principles relating to personal-data processing.
- Article 6 — lawfulness of processing.
- Articles 13 and 14 — information to be provided to data subjects.
- Article 21 — right to object, including to direct marketing where applicable.
- Article 22 — automated individual decision-making, including profiling.
- Article 28 — processor obligations, where applicable.
- Article 32 — security of processing.
- Article 35 — data protection impact assessments, where the statutory conditions are met.

**Portfolio application:** Assess the lawfulness, fairness, transparency, necessity, proportionality and security of personal-data processing in the LendWise scenarios.

**Important limitation:** The presence of financial data does not automatically mean that special-category personal data under Article 9 is being processed. The actual data and inferences must be examined.

### SRC-003 — EU AI Act Service Desk: Annex III

**Official source:**  
https://ai-act-service-desk.ec.europa.eu/en/ai-act/annex-iii

**Portfolio application:** Use as a navigation and explanatory resource when assessing whether an AI system falls within a listed high-risk use case.

**Important limitation:** The underlying regulation remains the primary legal source. The assessment must consider the precise statutory wording and applicable conditions.

### SRC-004 — European Commission guidelines on prohibited AI practices

**Official source:**  
https://ai-act-service-desk.ec.europa.eu/sites/default/files/2025-08/guidelines_on_prohibited_artificial_intelligence_practices_established_by_regulation_eu_20241689_ai_act_english_ied3r5nwo50xggpcfmwckm3nuc_112367-1.PDF

**Portfolio application:** Support the fact-specific assessment of potentially prohibited practices, including the distinction between emotion recognition and other forms of physical-state assessment.

**Important limitation:** Guidance supports interpretation but does not replace the legislation or eliminate the need to assess the system's technical function, intended purpose, actual use and any relevant exception.

### SRC-005 — India Digital Personal Data Protection Act, 2023

**Official source:**  
https://www.meity.gov.in/static/uploads/2024/06/2bf1f0e9f04e6fb4f8fef35e82c42aa5.pdf

**Portfolio application:** Assess the relevance of India's digital personal-data protection framework to LendWise's Indian operations and affected individuals.

**Important limitation:** Check applicable commencement notifications, amendments and implementing rules before concluding that a particular provision is in force or applies to a scenario.

### SRC-006 — India Digital Personal Data Protection Rules, 2025

**Official source:**  
https://www.meity.gov.in/documents/act-and-policies/digital-personal-data-protection-rules-2025-gDOxUjMtQWa?pageTitle=Digital-Personal-Data-Protection-Rules-2025

**Portfolio application:** Assess implementing requirements alongside the Act and relevant commencement notifications.

**Important limitation:** The Act and Rules have phased commencement arrangements. Do not assume every provision became operative on the date the Rules were notified. Record the relevant provision, notification and applicable date when performing a legal assessment.

### SRC-007 — NIST AI Risk Management Framework 1.0

**Official source:**  
https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf

**Framework resource:**  
https://airc.nist.gov/

**Core functions:**

- Govern
- Map
- Measure
- Manage

**Portfolio application:** Organise LendWise's enterprise governance model, context and impact analysis, measurement plans, risk treatment and ongoing monitoring.

**Important limitation:** NIST AI RMF is voluntary guidance. It is not legislation and does not automatically establish compliance with the EU AI Act, GDPR or Indian law. Check the NIST website for framework revision status and newer resources before future updates.

### SRC-008 — ISO/IEC 42001:2023

**Official source:**  
https://www.iso.org/standard/81230.html

**Portfolio application:** Use as a reference for establishing, implementing, maintaining and continually improving an AI management system, including organisational responsibilities and governance processes.

**Important limitation:** This portfolio does not establish ISO/IEC 42001 conformity or certification. Any detailed control mapping must be based on the applicable standard and its requirements.

## 5. Source-to-project mapping

| Project or artifact | Principal sources |
|---|---|
| AI inventory and legal classification | SRC-001, SRC-003 |
| AI-001 Credit Scoring and fairness assessment | SRC-001, SRC-002, SRC-007 |
| AI-003 Fraud Detection | SRC-001, SRC-002, SRC-007 |
| AI-005 CV Screening | SRC-001, SRC-002, SRC-007 |
| AI-006A and AI-006B emotion analysis | SRC-001, SRC-002, SRC-004 |
| Privacy and impact assessments | SRC-002, SRC-005, SRC-006 |
| Enterprise AI governance operating model | SRC-007, SRC-008 |
| Cross-framework mapping | SRC-001, SRC-002, SRC-005, SRC-006, SRC-007, SRC-008 |

## 6. Citation and change-control rules

For each detailed assessment:

1. Identify the specific provision, section or framework component relied upon.
2. Link the source directly where possible.
3. Explain how the provision relates to the documented system facts.
4. Separate statutory requirements from voluntary guidance and proposed internal controls.
5. Record assumptions, uncertainty and any legal questions requiring specialist review.
6. Recheck sources when legislation, implementing rules, official guidance or the system's intended purpose changes.
7. Update this register and the affected assessment when a material source change alters the analysis.

## 7. Limitations

This register supports a fictional educational portfolio. It is not a complete legal register for a real financial-services organisation and does not replace a jurisdiction-specific legal review.

All system scenarios and synthetic performance figures should be labelled as such. Regulatory conclusions must be validated against the applicable law, commencement dates and actual technical and operational facts before being used for a real deployment.
