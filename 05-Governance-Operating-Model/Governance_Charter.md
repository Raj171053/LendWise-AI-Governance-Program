# LendWise AI Governance Charter

**Document status:** Draft for review  
**Version:** 0.1  
**Organization:** LendWise Financial Services Ltd.  
**Headquarters:** Amsterdam, Netherlands  
**Operating markets:** European Union and India

## 1. Purpose

This charter establishes the proposed governance structure through which LendWise identifies, assesses, manages, monitors, and reviews risks arising from the development, procurement, deployment, and use of artificial intelligence systems.

The objective is to ensure that AI systems support legitimate business purposes while protecting customers, maintaining accountability, managing model and data risks, and meeting applicable legal and regulatory obligations.

This charter is a proposed governance design. It does not establish that LendWise has implemented these controls or achieved regulatory compliance.

## 2. Scope

This charter applies to AI systems developed internally, procured from third parties, or materially modified by LendWise.

The scope includes:

- Credit scoring and lending support.
- Customer-support chatbots and generative AI.
- Fraud detection and transaction monitoring.
- Biometric identification and document verification.
- CV screening and recruitment-related AI.
- Autonomous or semi-autonomous AI agents introduced in the future.

The governance process covers the full AI lifecycle, from initial intake and risk classification through approval, deployment, monitoring, change management, and retirement.

## 3. Governance principles

LendWise's proposed governance program follows these principles:

1. **Accountability:** Every AI system must have an identified business owner and accountable control owners.
2. **Risk proportionality:** Governance requirements must reflect the system's intended purpose, potential impact, autonomy, and applicable legal classification.
3. **Human oversight:** Human review must be meaningful, appropriately authorized, and supported by sufficient information.
4. **Fairness and non-discrimination:** Potential bias, proxy variables, group-level performance differences, and unjustified disparities must be investigated.
5. **Transparency and explainability:** Relevant stakeholders must receive explanations appropriate to their role and the system's impact.
6. **Privacy and security:** Data access, processing, retention, and security risks must be assessed and controlled.
7. **Evidence-based decisions:** Approval and closure decisions must be supported by documented evidence rather than policy statements alone.
8. **Continuous monitoring:** Material changes, incidents, performance deterioration, and emerging risks must trigger review.

## 4. Proposed governance roles

### Executive Sponsor

Provides executive support, allocates resources, and resolves material governance escalations. The sponsor must not bypass mandatory controls or substitute commercial urgency for required approval.

### AI Governance Lead

Maintains the AI governance framework, coordinates risk assessments, monitors remediation, manages governance records, and prepares risk reports for decision-makers.

### Business / AI System Owner

Defines the intended purpose, business justification, operating context, and acceptable performance requirements. Ensures that the system remains within its approved scope.

### Model Development / Technical Owner

Maintains technical documentation, model and data lineage, testing records, performance monitoring, and technical remediation evidence.

### Risk and Compliance

Reviews risk classification, applicable obligations, control adequacy, residual risk, and proposed exceptions. Coordinates independent review where required.

### Data Protection and Information Security

Reviews privacy, data minimization, access controls, security threats, retention, and incident handling within their respective areas of responsibility.

### Independent Reviewer

Challenges the assessment and evaluates whether required evidence supports the proposed approval or finding closure. Must have appropriate competence and independence from the activity being reviewed.

### Human Decision-Makers / Operators

Follow approved procedures, exercise their assigned authority, document overrides where required, escalate exceptions, and avoid treating model outputs as automatically correct.

These roles are proposed assignments. Actual role holders, delegated authority, and reporting lines must be formally approved before the operating model is treated as implemented.

## 5. AI lifecycle governance gates

Every AI system must pass the applicable governance gates before proceeding.

| Gate | Required decision or evidence |
|---|---|
| Intake | Business purpose, owner, users, data, vendor involvement, and intended actions documented |
| Classification | Enterprise risk assessment and applicable legal classification documented separately |
| Assessment | Privacy, fairness, security, human oversight, and other relevant impacts assessed |
| Validation | Required data, model, performance, fairness, and operational tests completed |
| Approval | Authorized decision-maker reviews evidence, open findings, and residual risk |
| Deployment | Approved controls implemented and production readiness documented |
| Monitoring | Performance, incidents, overrides, complaints, and relevant group outcomes monitored |
| Change / retirement | Material changes trigger reassessment; retirement includes access, data, and record-management decisions |

A system must not bypass a required gate because of a launch deadline or a favorable overall performance metric.

## 6. Findings and remediation

Governance findings must be recorded with a unique identifier, risk rating, accountable owner, required action, target date, dependencies, and closure evidence.

Finding closure requires:

- Evidence that the corrective action has been implemented.
- Relevant test results demonstrating that the control works.
- Traceable evidence retained in the designated repository.
- Independent review where required.
- An explicit closure decision by an authorized reviewer.

A planned action, completed training exercise, or drafted control document does not by itself prove operational implementation.

## 7. Exceptions and residual risk

Exceptions must be documented with a rationale, affected system, risk implications, compensating controls, accountable decision-maker, and review or expiry date.

Residual-risk acceptance must be performed only by an authorized person under the approved delegation framework. Acceptance cannot override applicable legal requirements or mandatory controls.

Where required controls are absent, evidence is inconclusive, or approval authority is unclear, the system must remain subject to the applicable restriction until the issue is resolved.

## 8. Monitoring and reporting

The AI Governance Lead should coordinate periodic reporting on:

- AI inventory completeness and classification status.
- Open findings and overdue remediation.
- Model performance and fairness indicators.
- Human oversight and override activity.
- Incidents, complaints, and escalations.
- Third-party and vendor risks.
- Material model, data, or purpose changes.
- Outstanding approvals and accepted residual risks.

Reporting frequency, thresholds, escalation timelines, and recipients must be specified in the supporting procedures and approved by the appropriate authority.

## 9. Relationship to external frameworks

The governance program should use the NIST AI Risk Management Framework as a risk-management reference and assess applicable obligations under relevant legislation, including the EU AI Act and applicable Indian data-protection and sectoral requirements.

Framework mapping does not itself establish legal compliance. Legal applicability, system classification, and effective dates must be assessed for the relevant facts and jurisdictions.

## 10. Immediate application to AI-001 Credit Scoring

AI-001 remains **Not Approved — Remediation Required** under the current project record.

The governance process must preserve the distinction between documented assessment findings and verified production defects. Outstanding remediation, operational testing, supporting evidence, independent review, and formal approval must be resolved as applicable before production approval can be reconsidered.

No provision in this charter changes AI-001's current approval status.

## 11. Implementation requirements

Before this charter is treated as approved and operational, LendWise must:

1. Appoint and document the relevant role holders.
2. Approve delegated decision-making and escalation authority.
3. Establish the RACI matrix and AI intake process.
4. Define approval gates, evidence standards, and exception procedures.
5. Establish the vendor assessment process.
6. Approve monitoring, reporting, and record-retention arrangements.
7. Record formal approval of this charter and its effective date.

## 12. Approval record

| Role | Name | Decision | Date |
|---|---|---|---|
| Executive Sponsor | To be assigned | Pending | Pending |
| AI Governance Lead | To be assigned | Pending | Pending |
| Risk / Compliance Approver | To be assigned | Pending | Pending |

**Current status:** Proposed draft — not yet formally approved.
