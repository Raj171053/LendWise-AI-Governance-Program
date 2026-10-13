# LendWise AI Governance Program — Mock Audit Report

**Document status:** Portfolio simulation — Draft  
**Audit subject:** AI-001 Credit Scoring System  
**Organization:** LendWise Financial Services Ltd.  
**Markets considered:** European Union and India  
**Audit type:** Simulated governance and evidence-readiness review  
**Overall outcome:** NOT APPROVED — REMEDIATION REQUIRED

---

## 1. Executive Summary

This mock audit evaluates the governance documentation, model-risk assessment, proposed controls, and conformity-readiness materials prepared for LendWise's AI-001 Credit Scoring System.

The review draws on the project's existing AI impact assessment, model audit, governance operating model, remediation tracker, control evidence and closure matrix, technical documentation skeleton, and multi-framework crosswalk.

The portfolio identifies material unresolved issues involving proxy-variable risk, fairness evaluation, data quality, human oversight, implementation evidence, monitoring, and independent closure verification.

The available artifacts demonstrate that governance risks have been identified and proposed controls have been documented. They do not establish that every control has been implemented, independently tested, or shown to operate effectively.

**Audit conclusion:** AI-001 must remain **Not Approved — Remediation Required** until the applicable requirements have been determined, material findings have been remediated, and the required implementation and closure evidence has been independently reviewed.

This is a simulated review of portfolio artifacts. No live production environment, real customer data, or operational control environment was independently audited.

## 2. Audit Objectives

The objectives of this review are to:

1. Assess whether the AI-001 governance risks and limitations are documented.
2. Evaluate whether identified findings have accountable owners, remediation actions, and closure evidence requirements.
3. Examine whether human oversight, fairness, security, monitoring, and documentation controls have sufficient supporting evidence.
4. Identify gaps between proposed governance design and demonstrated implementation.
5. Determine whether the available portfolio evidence supports a production approval recommendation.

## 3. Scope

### In scope

- AI-001 credit scoring and its stated intended purpose.
- AI inventory and risk classification documentation.
- NIST AI RMF assessment materials.
- AI impact assessment and proposed data rights request workflow.
- Educational model audit, dataset validation, and model card.
- Governance charter, RACI, and vendor assessment template.
- AI-001 remediation tracker and F-004 control evidence and closure matrix.
- EU AI Act gap assessment and technical documentation skeleton.
- Multi-framework crosswalk and evidence index.

### Out of scope

- Live production infrastructure and deployed model behavior.
- Independent access to LendWise systems, APIs, logs, and security controls.
- Verification of real customer outcomes or lending decisions.
- Independent reproduction of all notebook results.
- Formal legal opinion, certification, or conformity assessment.
- Verification that proposed policies have received formal organizational approval.

## 4. Review Methodology

The simulated review uses four evidence-readiness categories:

| Category | Meaning |
|---|---|
| Documented | A relevant artifact or governance requirement has been recorded in the portfolio. |
| Proposed | A control or process has been designed but implementation is not established. |
| Unverified | Evidence is insufficient to confirm implementation or effectiveness. |
| Remediation required | An identified issue must be addressed and closure evidence reviewed. |

A documented policy is not automatically an implemented control. A planned test is not a completed test. A successful training exercise is not proof of operational effectiveness.

The review treats prior project completion confirmations as evidence that portfolio work was reported as completed, not as independent verification of the live repository or the operation of LendWise controls.

## 5. Evidence Reviewed

The following artifacts are identified in the portfolio record:

| Artifact | Audit relevance | Limitation |
|---|---|---|
| AI inventory and company brief | System scope and classification context | Latest ownership and classification details require reconciliation |
| NIST AI RMF assessment report | Governance, mapping, measurement, and management structure | Voluntary framework; workbook contents not independently inspected |
| AI impact assessment | Risks and impacts on individuals | Draft assessment; remediation remains open |
| DSAR for AI draft | Proposed data rights request workflow | Not an approved operational procedure |
| Dataset validation and model audit | Educational data and model evaluation | Public dataset and baseline model; not production evidence |
| Model card and audit report | Performance, limitations, and explainability | Independent production validation has not been established |
| Governance charter and RACI | Roles, accountability, and decision rights | Formal approval and implementation are unverified |
| Vendor assessment | Proposed third-party due diligence | No completed assessment of an actual vendor confirmed |
| F-004 control evidence and closure matrix | Human oversight, access, escalation, and logging evidence requirements | Operational tests and closure evidence remain outstanding |
| Consolidated remediation tracker | Findings, actions, owners, and closure requirements | Finding closure requires supporting evidence and independent review |
| Gap assessment and technical documentation skeleton | EU AI Act conformity-readiness work | Applicability and conformity route require legal review; documentation is incomplete |
| Framework crosswalk and evidence index | Cross-framework control mapping and traceability | Preliminary mapping; legal references and artifact paths require validation |

## 6. Key Audit Findings

The following findings are carried forward from the existing AI-001 remediation tracker. They are not new findings from an independent production audit.

| Finding | Priority | Audit observation | Required response |
|---|---|---|---|
| F-001 — Proxy-variable risk | High | Proxy-variable assessment remains unresolved | Complete documented assessment and review material proxies |
| F-002 — Fairness metrics | High | Fairness evaluation criteria require stronger definition | Establish justified metrics, thresholds, subgroup analysis, and escalation criteria |
| F-003 — Label reliability | High | Label reliability and selection bias remain uncertain | Document label provenance, limitations, and validation |
| F-004 — Human oversight | High | Oversight requirements and supporting evidence remain incomplete | Verify reviewer authority, workflow enforcement, escalation, and auditability |
| F-005 — Data representativeness | Medium, provisional | Representativeness has not been sufficiently verified | Assess population coverage and relevant data limitations |
| F-006 — Residual group disparities | Medium, provisional | Observed group differences require further investigation | Investigate material disparities and document justified mitigations |
| F-007 — Automatic rejection or gating | High | Restrictions on automated adverse decisions are unverified | Verify decision workflow, human intervention, and technical enforcement |
| F-008 — Monitoring and reassessment | High | Monitoring and change-triggered reassessment evidence is insufficient | Define triggers, thresholds, owners, and retained monitoring evidence |
| F-009 — Stakeholder feedback | Medium | Feedback and risk communication arrangements are not evidenced sufficiently | Define accessible feedback, complaints, and risk communication processes |
| F-010 — Operator proficiency | Medium | Competency evidence has not been verified | Define role-specific competency requirements and retain training evidence |
| F-011 — Residual-risk approval | High | Independent closure and residual-risk decisions require consolidation | Record evidence-based decisions, authorized risk acceptance, and independent review |

**Priority note:** The listed priorities are carried forward from the existing tracker. Medium priorities are provisional where indicated. This table does not establish that the findings have been independently reproduced.

## 7. Model Audit Interpretation

The portfolio's educational baseline used the public UCI German Credit dataset and logistic regression.

Previously recorded test-set metrics included:

- Accuracy: 77.5%
- Precision for the bad-credit class: approximately 63.6%
- Recall for the bad-credit class: approximately 58.3%
- False-positive rate: approximately 14.3%
- False-negative rate: approximately 41.7%

The educational analysis also examined age and housing subgroups, feature contributions, and a feature-removal comparison.

These results illustrate the need to examine model performance beyond aggregate accuracy. They do not demonstrate that a production LendWise model has these characteristics or that the model is fair, unfair, suitable, or compliant.

The observed subgroup differences and small subgroup samples require careful interpretation. A lack of statistically conclusive evidence is not proof of fairness or equivalence.

Before any production decision, LendWise would need evidence appropriate to its actual model, data, intended population, lending workflow, and applicable legal requirements.

## 8. Human Oversight and Control Effectiveness

The existing F-004 matrix records unresolved control evidence and closure requirements across reviewer authority, access restrictions, escalation ownership, and audit logging.

The portfolio history records training scenarios and review discussions, but operational control tests have not been established as completed.

Accordingly, this audit does not conclude that the relevant controls are defective in production. It concludes that their operational implementation and effectiveness remain unverified in the available evidence.

Closure should require, as applicable:

1. Approved control design and accountable ownership.
2. Evidence of implementation in the relevant workflow and systems.
3. Test procedures, results, timestamps, and retained evidence.
4. Documented exceptions and corrective actions.
5. Independent review and a recorded closure decision.

## 9. Regulatory and Framework Considerations

The crosswalk references the EU AI Act, NIST AI RMF, ISO/IEC 42001, India's DPDP Act, and India's AI Governance Guidelines.

These sources serve different purposes and do not create identical obligations.

The EU AI Act classification and applicable obligations must be determined from the system's actual intended purpose, relevant legal provisions, the organization's provider or deployer role, and applicable transitional and implementation dates.

NIST AI RMF is voluntary guidance. ISO/IEC 42001 is a management-system standard. India's data protection requirements and AI governance guidance must be considered according to their respective legal status, applicability, and effective dates.

This portfolio review is not a legal opinion. The crosswalk and conformity gap assessment require validation by appropriately qualified legal or compliance reviewers before being used to support a regulatory conclusion.

## 10. Required Remediation and Closure Conditions

Before reconsidering AI-001 for production approval, LendWise should:

1. Resolve material proxy-variable, fairness, label reliability, and representativeness questions.
2. Define and validate the applicable performance, fairness, and monitoring criteria.
3. Verify the human decision workflow and restrictions on automated adverse decisions.
4. Demonstrate implementation and operational effectiveness of required controls.
5. Complete technical documentation using verified system-specific evidence.
6. Establish incident handling, monitoring, change management, and reassessment procedures.
7. Confirm accountable owners, reviewer competence, escalation arrangements, and independent closure authority.
8. Obtain a documented legal applicability assessment and complete applicable conformity or registration steps.
9. Update the consolidated remediation tracker with evidence references, test status, residual-risk decisions, and closure reviewers.
10. Record an explicit, authorized production decision after required remediation and independent review.

No finding should be marked closed solely because a policy, template, or case study has been created.

## 11. Final Audit Opinion

Based on the portfolio evidence described above, the AI-001 governance package demonstrates meaningful progress in identifying risks and structuring governance controls. However, material evidence gaps remain, and implementation and operational effectiveness have not been sufficiently established.

**Final recommendation: NOT APPROVED — REMEDIATION REQUIRED.**

This recommendation is limited to the fictional LendWise portfolio scenario and its documented evidence status. It is not a certification, legal determination, or independent audit opinion concerning a real production system.

## 12. Document Control

| Field | Value |
|---|---|
| Document | Mock Audit Report |
| Version | 1.0 — Draft |
| Prepared for | LendWise Financial Services Ltd. |
| System | AI-001 Credit Scoring |
| Review type | Simulated portfolio exercise |
| Approval status | Not a formally approved audit report |
| Next review | After material remediation evidence is available |

