# Case Study: High-Risk AI Conformity Readiness at LendWise

## 1. Project Overview

**Organization:** LendWise Financial Services Ltd. (fictional)  
**Headquarters:** Amsterdam, Netherlands  
**Operating markets:** European Union and India  
**AI system:** AI-001 — Credit Scoring  
**Project:** High-Risk AI Conformity Readiness  
**Role:** AI Governance Program Designer — portfolio simulation  
**Status:** Gap assessment and technical documentation structure prepared; conformity not established

## 2. Objective

The objective was to establish a structured approach for assessing AI-001 against relevant EU AI Act requirements, identifying documentation gaps, and organizing the evidence needed for a future conformity assessment.

The project builds on the existing AI inventory, NIST AI RMF assessment, AI impact assessment, bias and explainability audit, remediation tracker, and governance operating model.

It does not repeat those assessments. Instead, it maps their existing outputs to conformity-readiness requirements and identifies where further evidence or legal review is needed.

## 3. System Context

AI-001 is a proposed credit-scoring system that generates a credit-risk score to support human lending decisions.

The system is part of the fictional LendWise financial-services environment, which operates in the European Union and India.

The EU AI Act identifies certain systems intended to evaluate the creditworthiness of natural persons or establish their credit score as high-risk under Annex III, point 5(b), subject to the applicable provisions and exceptions.

LendWise must document its intended purpose, affected populations, deployment context, and applicable legal roles before finalizing the classification and conformity route.

## 4. Deliverables Created

### A. Conformity Gap Assessment

**Artifact:** `Gap_Assessment.csv`

Created a structured assessment covering 18 requirement areas, including:

- High-risk classification.
- Risk management.
- Data and data governance.
- Technical documentation.
- Record-keeping and logging.
- Transparency and human oversight.
- Accuracy, robustness, and cybersecurity.
- Provider and deployer obligations.
- Quality management and corrective action.
- Fundamental rights impact assessment applicability.
- Conformity assessment and registration.
- Production readiness and approval.

Each row records an existing evidence reference or evidence limitation, an identified gap or concern, a required action, a proposed owner, a priority, and a status.

The assessment distinguishes missing or unverified evidence from confirmed control failures.

### B. Technical Documentation Skeleton

**Artifacts:**
- `Technical_Documentation_Skeleton.md`
- `Technical_Documentation_Skeleton.pdf`

Prepared a structured documentation template covering system purpose, provider roles, design and development, data governance, risk management, model validation, fairness, human oversight, logging, transparency, cybersecurity, quality management, conformity assessment, monitoring, and evidence indexing.

The template contains explicit evidence requirements and placeholders for unresolved matters.

It is a working structure, not a completed technical documentation package.

## 5. Existing Evidence Reused

The assessment reuses previously reported LendWise artifacts:

- AI inventory and classification discussions.
- NIST AI RMF assessment and report.
- AI impact assessment and proposed DSAR response draft.
- Model audit notebook, model card, and audit report.
- Consolidated remediation tracker containing findings F-001 through F-011.
- Human oversight matrix and F-004 control-evidence and closure matrix.
- Governance charter, RACI matrix, and intake form.

These artifacts provide a starting evidence base. Their existence does not by itself demonstrate that a regulatory requirement has been satisfied.

## 6. Key Findings and Open Issues

The conformity-readiness exercise identified several areas requiring further evidence or review.

### Data governance and fairness

The existing model audit identified unresolved questions involving proxy variables, data representativeness, label reliability, and subgroup performance. The public UCI German Credit dataset used for the educational audit does not establish the quality or representativeness of a real production dataset.

### Human oversight and logging

The existing F-004 record remains open. Proposed oversight and logging controls require implementation evidence, operational testing, retained evidence, and the required independent review.

### Technical documentation completeness

The technical documentation skeleton provides the relevant structure, but its sections contain open evidence requirements. A requirement-by-requirement review is needed to determine which Annex IV elements are complete and which remain outstanding.

### Legal roles and conformity route

LendWise must establish the relevant legal roles and confirm the applicable conformity-assessment procedure, registration obligations, and other requirements based on the actual system and deployment circumstances.

### Fundamental rights impact assessment

The existing AI impact assessment must not automatically be treated as a completed assessment under Article 27. Applicability must be determined against the statutory criteria and LendWise's role in the relevant deployment.

## 7. Governance Decision

AI-001 remains **Not Approved — Remediation Required**.

The conformity-readiness documents do not close existing remediation findings, demonstrate operational control effectiveness, establish regulatory conformity, or authorize production deployment.

Any future approval decision must be supported by the required technical documentation, applicable legal review, implemented and tested controls, resolution or authorized treatment of outstanding findings, and formal decision records.

## 8. Limitations

This project is a fictional portfolio simulation. No claim is made that:

- LendWise has completed an EU AI Act conformity assessment.
- The technical documentation is complete or legally sufficient.
- Applicable registration or declaration requirements have been fulfilled.
- All identified controls have been implemented or tested.
- AI-001 is approved for production.
- The assessment constitutes legal advice or regulatory certification.

Legal requirements, applicability, and implementation timelines must be verified against the relevant consolidated legal text and applicable provisions when the assessment is used for a real system.

## 9. Key Learning Outcomes

This project demonstrates the ability to:

- Translate legal and governance requirements into a structured gap assessment.
- Link existing AI risk assessments to technical documentation requirements.
- Distinguish documentary evidence from operational assurance.
- Identify unresolved legal, technical, and governance questions.
- Track remediation through proposed owners, priorities, and required actions.
- Preserve approval restrictions until the necessary evidence and decisions exist.

## 10. Conclusion

The LendWise conformity-readiness exercise provides a structured starting point for organizing technical documentation and identifying outstanding requirements for AI-001 Credit Scoring.

Its central principle is that conformity cannot be established by a completed checklist or well-organized documentation alone. Applicable requirements must be assessed, evidence must support the relevant claims, controls must be validated where required, and authorized decisions must be recorded.

**Portfolio note:** LendWise is fictional. This case study demonstrates conformity-readiness analysis, not completed regulatory conformity or production approval.
