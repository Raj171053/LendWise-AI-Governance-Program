# LendWise Financial Services Ltd.
## NIST AI Risk Management Framework Assessment Report

**AI system:** AI-001 — Credit Scoring  
**Framework:** NIST AI Risk Management Framework (AI RMF 1.0)  
**Assessment type:** Portfolio-based governance assessment  
**Assessment status:** Initial assessment; remediation required  
**Overall governance recommendation:** **NOT APPROVED — REMEDIATION REQUIRED**

---

## 1. Executive Summary

This assessment evaluates the governance and risk-management arrangements for LendWise AI-001, a predictive credit-scoring system intended to generate risk scores for consumer and small-business lending workflows. Under the stated design, human reviewers make the final lending decisions.

The assessment is structured around the four NIST AI RMF functions: Govern, Map, Measure and Manage. It considers the system's intended purpose, potential impacts, fairness and performance evaluation, human oversight, data quality, risk treatment, monitoring and evidence requirements.

The assessment identifies unresolved issues involving proxy-variable risk, fairness metric definitions, label reliability and selection bias, data representativeness, subgroup disparities, human oversight, automatic rejection or gating, ongoing monitoring, stakeholder feedback, operator competency and formal residual-risk decisions.

Synthetic fairness analysis suggests that retraining improved the observed subgroup approval ratio and overall accuracy. These results are preliminary training evidence only. They do not establish real-world fairness, operational effectiveness or readiness for production.

**Recommendation:** AI-001 should remain **Not Approved — Remediation Required** until material findings are addressed, required controls are implemented and tested, supporting evidence is independently reviewed, and an authorised decision-maker records the production decision.

## 2. Assessment Scope and Method

### In scope

- AI-001 intended purpose and lending context.
- AI governance roles, responsibilities and oversight.
- Model performance and fairness evaluation requirements.
- Data quality, representativeness, label reliability and proxy-variable risks.
- Human review, challenge, override and escalation.
- Audit logging and supporting evidence access.
- Monitoring, change management and lifecycle controls.
- Remediation tracking, residual-risk review and production approval.

### Assessment approach

The assessment uses the NIST AI RMF functions as an organising structure:

- **Govern:** governance policies, accountability, roles and risk-management practices.
- **Map:** intended use, context, affected parties, potential benefits and harms.
- **Measure:** evaluation methods, performance, fairness, validation and monitoring.
- **Manage:** prioritisation, treatment, response, residual-risk decisions and lifecycle management.

The assessment is based on project documentation, proposed controls, synthetic training scenarios and the reported state of the working assessment materials. It is not an independent technical audit, a certification, or evidence that controls have passed operational testing.

## 3. Key Findings

| Finding | Priority | Principal concern |
|---|---|---|
| F-001 | High | Proxy-variable risk is unresolved |
| F-002 | High | Fairness metrics and methodology require definition and approval |
| F-003 | High | Label reliability and selection bias are uncertain |
| F-004 | High | Human oversight controls require implementation and evidence |
| F-005 | Medium — provisional | Data representativeness is unverified |
| F-006 | Medium — provisional | Residual subgroup disparities require investigation |
| F-007 | High | Automatic rejection or decision gating is unverified |
| F-008 | High | Monitoring and change-triggered reassessment are not evidenced |
| F-009 | Medium | Stakeholder feedback and risk communication are not evidenced |
| F-010 | Medium | Operator proficiency and competency evidence are not verified |
| F-011 | High | Residual-risk approval and independent closure decisions require consolidation |

Priorities are provisional governance assessments and should be confirmed against the organisation's approved risk-rating methodology.

## 4. Fairness and Model Evaluation

The synthetic training analysis reported the following comparison:

- Initial subgroup approval rates: Group A 60%, Group B 40%.
- Initial Group B-to-Group A approval ratio: approximately 0.667.
- Retrained subgroup approval rates: Group A 58%, Group B 54%.
- Retrained Group B-to-Group A approval ratio: approximately 0.931.
- Reported overall accuracy: 82% before retraining and 86% after retraining.
- Reported false-positive and false-negative rates also moved closer between the groups in the synthetic comparison.

These figures are illustrative, not verified production results. Before using fairness metrics to support a decision, the assessment requires documented definitions of the target, positive class, false-positive and false-negative calculations, denominators, reference outcomes, evaluation population, subgroup counts and uncertainty.

The four-fifths ratio can be used as a screening indicator, but it is not proof of fairness or legal compliance. Improved aggregate accuracy or subgroup parity does not by itself demonstrate that a model is appropriate, reliable or safe for lending decisions.

Required follow-up includes proxy-variable analysis, data provenance and quality review, representativeness assessment, independent model validation, mitigation testing and documented residual-risk analysis.

## 5. Human Oversight and Control Evidence

Finding F-004 remains open. The project has documented intended human-oversight controls and developed test plans covering reviewer authority, supporting evidence access, escalation ownership and service-level expectations, and audit logging.

However, documentation and scenario exercises do not demonstrate that controls are implemented or operationally effective.

Closure requires, as applicable:

1. Approved reviewer authority, challenge and override rules.
2. Evidence that authorised reviewers can access relevant supporting information.
3. Approved escalation ownership, backup arrangements and service-level targets.
4. Implemented audit events, record-integrity protections and relevant logging controls.
5. Operational tests executed in an authorised environment.
6. Retained expected-versus-actual results and supporting evidence.
7. Remediation and retesting of failures.
8. Independent evidence review and a documented closure decision.

Operational tests must remain marked Not Run unless actual execution evidence supports a different status. Missing evidence must not be treated as a pass.

## 6. Remediation and Risk Treatment

The consolidated AI-001 remediation tracker contains findings F-001 through F-011 and links them to relevant NIST AI RMF topics. It is the working source of truth for accountable owners, actions, dependencies, closure evidence, residual-risk decisions and production gates.

The immediate remediation priorities are:

1. Define and independently review fairness metrics and evaluation methodology.
2. Investigate proxy-variable risks, label reliability, selection effects and data representativeness.
3. Verify the actual lending workflow and establish that unapproved automatic rejection or gating cannot bypass the approved human decision process.
4. Implement and test human-oversight controls, including evidence access, escalation and audit logging.
5. Establish monitoring, change-triggered reassessment, rollback and lifecycle procedures.
6. Consolidate evidence, independent review and authorised residual-risk decisions.

Proposed owners and target weeks in the tracker are planning assumptions until confirmed by accountable stakeholders. No finding should be marked closed solely because a document has been drafted or a planned action has been discussed.

## 7. Production Approval Conditions

AI-001 should not be recommended for production approval until the organisation has:

- Resolved material findings or documented an authorised and justified risk decision where risk acceptance is permitted.
- Completed appropriate model and data validation.
- Investigated material subgroup disparities and proxy-variable risks.
- Verified the intended human decision workflow and absence of unapproved automated decision pathways.
- Implemented and tested required human-oversight and logging controls.
- Established monitoring, incident response and change-management arrangements.
- Retained evidence for each material control and remediation decision.
- Obtained independent review and formal approval from the authorised decision-maker.

Any residual-risk acceptance must identify the risk, rationale, evidence, affected parties, mitigations, decision authority and review conditions. It must not be inferred from silence or from completion of the assessment workbook.

## 8. Limitations

- This is a portfolio assessment using a fictional company and synthetic training scenarios.
- The live Google Sheet and repository contents have not been independently inspected as part of this report.
- Operational control implementation and test results have not been verified.
- Synthetic fairness metrics cannot establish production performance or real-world fairness.
- Proposed owners, priorities, target weeks and closure requirements require organisational confirmation.
- The report does not constitute legal advice, regulatory approval or certification of compliance.

## 9. Final Recommendation

**AI-001 — NOT APPROVED: REMEDIATION REQUIRED.**

The governance programme has established an initial framework for documenting risks, assigning remediation actions and defining evidence requirements. The next decision must be based on verified implementation, appropriate testing, independent review and explicit risk acceptance or closure decisions—not on documentation completion alone.

## 10. Framework Reference

National Institute of Standards and Technology (NIST), *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*, 2023. The NIST AI RMF is voluntary guidance; this assessment does not establish certification or compliance.
