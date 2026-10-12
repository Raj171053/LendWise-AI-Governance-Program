# Case Study: NIST AI RMF Assessment of an AI Credit-Scoring System

**Organisation:** LendWise Financial Services Ltd. (fictional)  
**AI system:** AI-001 — Credit Scoring  
**Framework:** NIST AI Risk Management Framework (AI RMF 1.0)  
**Assessment outcome:** Not Approved — Remediation Required

## Business Context

LendWise uses a predictive AI system to generate credit-risk scores for consumer and small-business lending workflows. Under the stated design, human reviewers make the final lending decisions. Because credit scoring can affect access to financial services, the system requires structured governance, fairness evaluation, effective human oversight and documented risk treatment.

## Objective

Develop an evidence-oriented AI risk assessment using the four NIST AI RMF functions: Govern, Map, Measure and Manage. Identify material governance gaps, define remediation actions and establish conditions for production approval.

## Work Performed

- **Govern:** Structured governance responsibilities, risk accountability and oversight requirements.
- **Map:** Documented intended use, context, potential impacts, affected stakeholders and risk areas.
- **Measure:** Organised performance, fairness, data-quality and independent-validation requirements.
- **Manage:** Consolidated risk treatment, remediation priorities, ownership, residual-risk decisions and production gates.
- Created a consolidated remediation tracker covering findings F-001 to F-011.
- Linked existing human-oversight work to evidence requirements for reviewer authority, supporting evidence access, escalation and audit logging.

## Key Findings

The assessment identified unresolved proxy-variable risk, incomplete fairness metric definitions, uncertain label reliability and selection bias, unverified data representativeness, subgroup disparities requiring investigation, incomplete human-oversight evidence, and an unverified automatic-rejection or gating pathway. Monitoring, lifecycle controls, stakeholder feedback, operator competency and formal residual-risk decisions also require further evidence.

Synthetic training metrics showed improved observed subgroup approval parity and overall accuracy after retraining. These results are illustrative and do not establish real-world fairness or production readiness.

## Recommended Actions

1. Approve the fairness metric methodology and validate the evaluation data.
2. Investigate proxy effects, label quality, selection bias and data representativeness.
3. Verify the end-to-end lending workflow and prevent unapproved automated decision pathways.
4. Implement and test human-oversight, escalation and audit-logging controls.
5. Establish monitoring, change management and lifecycle controls.
6. Obtain independent evidence review and authorised residual-risk decisions.

## Outcome

The assessment established a structured governance baseline and a consolidated remediation register. AI-001 remains **Not Approved — Remediation Required** because documentation and synthetic exercises are not substitutes for implementation evidence, operational testing and independent review.

## Scope and Limitations

This is a fictional portfolio project using synthetic scenarios. It is not an independent production audit, legal opinion, regulatory approval or certification of compliance. Proposed owners, priorities and actions require organisational confirmation.

**Reference:** NIST, *Artificial Intelligence Risk Management Framework (AI RMF 1.0)* (2023).
