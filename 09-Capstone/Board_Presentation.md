# LendWise AI Governance Program
## Board Risk and Readiness Review

**Organization:** LendWise Financial Services Ltd.  
**System under review:** AI-001 Credit Scoring  
**Markets considered:** European Union and India  
**Status:** Portfolio simulation — Draft

---

## Slide 1 — Executive Decision

### AI-001 is not ready for production approval

**Recommendation: NOT APPROVED — REMEDIATION REQUIRED**

- Material governance findings remain open.
- Control implementation and operational effectiveness are not sufficiently evidenced.
- Independent validation and closure review remain necessary.
- Regulatory applicability and conformity requirements require documented legal review.

**Board decision requested:** Maintain the production hold until defined approval conditions are satisfied.

---

## Slide 2 — Business Context

LendWise is a fictional financial services company serving consumers and small businesses in the EU and India.

AI-001 generates a credit risk score. Human reviewers are intended to make lending decisions.

The system can influence access to credit and may affect individuals' financial opportunities. Governance must therefore address model performance, fairness, data quality, human oversight, security, accountability, and applicable legal requirements.

---

## Slide 3 — Governance Program Delivered

The portfolio has developed governance materials across eight workstreams:

1. AI inventory and EU AI Act classification.
2. NIST AI RMF assessment.
3. AI impact assessment and proposed data rights workflow.
4. Bias and explainability audit using a public educational dataset.
5. Governance charter, RACI, and vendor assessment template.
6. AI agent risk assessment, threat model, and proposed controls.
7. High-risk conformity gap assessment and technical documentation skeleton.
8. Multi-framework crosswalk and evidence index.

These are portfolio deliverables. Their completion does not establish that production controls are implemented or legally compliant.

---

## Slide 4 — Principal Risk Areas

| Risk area | Current concern |
|---|---|
| Fairness and proxies | Proxy-variable assessment and fairness criteria require further work |
| Data quality | Label reliability and representativeness remain unresolved |
| Human oversight | Reviewer authority, workflow enforcement, and supporting evidence require verification |
| Automated decisions | Restrictions on automatic rejection or gating remain unverified |
| Monitoring | Monitoring triggers and change-based reassessment need evidence |
| Accountability | Competency, risk acceptance, and independent closure records require consolidation |
| Regulatory readiness | Legal applicability and conformity route require review |

---

## Slide 5 — Model Audit: What We Learned

The educational baseline used the public UCI German Credit dataset and logistic regression.

Previously recorded test-set results:

- Accuracy: 77.5%
- Precision for the bad-credit class: 63.6%
- Recall for the bad-credit class: 58.3%
- False-positive rate: 14.3%
- False-negative rate: 41.7%

Subgroup analysis illustrated why aggregate metrics alone are insufficient.

**Interpretation:** These are educational results, not measurements of a production LendWise model. They do not prove fairness, unfairness, or regulatory compliance.

---

## Slide 6 — Remediation Position

The consolidated tracker contains 11 findings, F-001 through F-011.

High-priority areas include:

- Proxy-variable risk.
- Fairness measurement.
- Label reliability.
- Human oversight.
- Automated decision restrictions.
- Monitoring and reassessment.
- Residual-risk approval and independent closure.

Other findings address data representativeness, subgroup disparities, stakeholder feedback, and operator competence.

The tracker must remain the authoritative record of owners, actions, evidence, and closure status.

---

## Slide 7 — Evidence and Control Assurance

The portfolio distinguishes between documented governance design and demonstrated control effectiveness.

Current limitations include:

- Operational tests for the F-004 control areas remain outstanding.
- Proposed policies and role assignments are not automatically approved policies.
- Vendor assessment materials are templates, not evidence of an actual vendor assessment.
- Technical documentation is a skeleton with incomplete evidence.
- Model audit results use public educational data.

**Management implication:** Do not treat documentation volume as proof of effective risk control.

---

## Slide 8 — Regulatory and Framework Position

The portfolio references:

- EU AI Act — applicable legal obligations must be determined for the actual system and organizational roles.
- NIST AI RMF — voluntary AI risk management guidance.
- ISO/IEC 42001 — AI management system standard.
- India's DPDP Act and AI Governance Guidelines — applicability and legal status must be assessed separately.

The crosswalk is preliminary. Legal and compliance reviewers must validate references, applicability, dates, and conformity requirements before the organization relies on it for a production decision.

---

## Slide 9 — Conditions Before Approval

Management should require evidence that:

1. Material fairness, proxy, data-quality, and label issues have been assessed and remediated or otherwise resolved through an authorized decision.
2. Human oversight and decision workflow controls are implemented and tested.
3. Monitoring, incident response, and change-management procedures are operational.
4. Independent model and control validation has been completed as appropriate.
5. Technical documentation and applicable conformity steps are complete.
6. Each material finding has evidence-based closure review.
7. Residual risks are explicitly documented and accepted only by authorized decision-makers where permitted.

Completion of a checklist alone is not sufficient; evidence must support the decision.

---

## Slide 10 — Board Resolution Requested

The Board or delegated approval authority is asked to:

- Maintain the AI-001 production hold.
- Assign accountable owners and resources to unresolved findings.
- Require evidence-based remediation and independent closure review.
- Require legal confirmation of applicable regulatory obligations.
- Reconsider production approval only after the defined gate criteria are met.

**Proposed resolution:** AI-001 remains **NOT APPROVED — REMEDIATION REQUIRED** pending satisfactory completion and review of required evidence.

---

## Closing Statement

LendWise has established a structured AI governance portfolio and identified significant areas requiring further assurance. The next phase is not to produce more documents for their own sake, but to demonstrate that the right controls are implemented, tested, independently reviewed, and maintained throughout the system lifecycle.
