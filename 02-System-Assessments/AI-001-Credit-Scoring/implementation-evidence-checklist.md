# AI-001 Human Oversight — Implementation Evidence Checklist

## 1. Document Control

- **Company:** LendWise Financial Services Ltd.
- **AI System ID:** AI-001
- **System:** Credit Scoring System
- **Related Finding:** F-004 — Human oversight requirements are incomplete
- **Priority:** High
- **Accountable Owner:** Head of Credit Risk
- **Closure Reviewer:** AI Governance / Model Risk authority
- **Document Status:** Draft — Implementation Evidence Not Yet Verified
- **Operational Test Status:** Not run
- **Production Approval:** Not approved — remediation required

## 2. Objective

Identify the evidence required to demonstrate that human oversight controls have been implemented, are operationally defined, and can be validated.

This checklist distinguishes control design documentation from implementation evidence and effectiveness-testing evidence.

The existence of a policy, matrix, test plan, or synthetic walkthrough does not by itself demonstrate operational effectiveness.

## 3. Implementation Evidence Checklist

### F004-01 — Reviewer Authority and Decision Boundaries

**Control objective:** Reviewers understand their authority, including when they can challenge a recommendation, when an override is permitted, and when escalation is mandatory.

- Required implementation evidence:
  - Approved Human Oversight Matrix.
  - Approved reviewer roles and delegation limits.
  - Documented review and override procedure.
  - Defined responsibilities for the Head of Credit Risk and delegated reviewers.
- Validation evidence:
  - Test showing a reviewer can challenge a recommendation.
  - Test showing an override outside the reviewer's authority is prevented or routed for authorisation.
- Proposed owner: Head of Credit Risk.
- Current status: Design documentation exists; operational implementation not evidenced.
- Operational test status: Not run.

### F004-02 — Access to Supporting Evidence

**Control objective:** Reviewers can access the relevant information needed to assess and challenge an AI-generated credit-risk score.

- Required implementation evidence:
  - Documented list of information reviewers must access.
  - Evidence of configured access to relevant case data and supporting information.
  - Defined procedure for missing, incomplete, outdated, or inaccessible data.
- Validation evidence:
  - Synthetic test showing that missing or unreliable information is identified.
  - Evidence that the prescribed hold, fallback, or escalation procedure is followed.
  - Evidence that the review resumes only when the required information is available or an authorised alternative process applies.
- Proposed owner: Credit Platform Engineering Lead, with Head of Credit Risk oversight.
- Current status: Operational implementation not evidenced.
- Operational test status: Not run.

### F004-03 — Escalation Ownership and Service Levels

**Control objective:** Unresolved cases reach an accountable person and remain traceable until an authorised next step is determined.

- Required implementation evidence:
  - Approved escalation procedure and escalation matrix.
  - Named accountable role and backup route.
  - Approved acknowledgement and resolution or next-step targets.
  - Defined procedure for missed deadlines and unacknowledged escalations.
- Validation evidence:
  - Synthetic test demonstrating delivery and acknowledgement tracking.
  - Evidence that the backup escalation route activates when required.
  - Evidence of case ownership, deadline-breach handling, and documented outcome or next step.
- Proposed owner: Head of Credit Risk.
- Current status: Proposed service levels and escalation expectations documented; operational implementation not evidenced.
- Operational test status: Not run.

### F004-04 — Audit Logging and Record Integrity

**Control objective:** Reviewer challenges, rationales, overrides, escalations, authorisations, and outcomes can be reconstructed from reliable records.

- Required implementation evidence:
  - Documented audit-log requirements.
  - Evidence of configured logging for relevant review and decision events.
  - Defined access and record-protection controls.
  - Approved logging-failure and record-reconciliation procedure.
- Validation evidence:
  - Sample audit-log records from the test environment.
  - Test showing relevant actions are recorded with timestamps and accountable roles.
  - Test of the approved fallback during a logging failure.
  - Evidence that records are reconciled after recovery and discrepancies are investigated.
- Proposed owner: Credit Platform Engineering Lead, with AI Governance / Model Risk review.
- Current status: Operational implementation not evidenced.
- Operational test status: Not run.

### F004-05 — Reviewer Training and Competence

**Control objective:** Reviewers can follow the approved process and understand the limitations of AI-generated recommendations.

- Required implementation evidence:
  - Approved training material and documented review procedures.
  - Defined reviewer competency requirements.
  - Training completion records for relevant reviewers.
- Validation evidence:
  - Assessment or observed exercise showing that reviewers can challenge scores, follow escalation rules, and respect authority boundaries.
  - Records of identified competency gaps and follow-up training.
- Proposed owner: Head of Credit Risk, with the designated training owner.
- Current status: Training implementation and completion evidence not supplied.
- Operational test status: Not run.

### F004-06 — Workflow Safeguards and Controlled Recovery

**Control objective:** Required safeguards remain in place when evidence, escalation, or audit logging is unavailable.

- Required implementation evidence:
  - Documented end-to-end lending workflow.
  - Defined hold, fallback, and recovery procedures.
  - Evidence that unapproved automatic rejection or other customer-impacting pathways cannot bypass the intended human decision process.
- Validation evidence:
  - Synthetic tests of evidence unavailability, escalation failure, and logging failure.
  - Evidence that required safeguards remain active.
  - Evidence of controlled resumption after recovery.
- Proposed owner: Credit Platform Engineering Lead, with Head of Credit Risk oversight.
- Current status: Operational implementation not evidenced.
- Operational test status: Not run.

## 4. Consolidated Evidence Register

| Control ID | Implementation Evidence | Validation Evidence | Status |
|---|---|---|---|
| F004-01 | Not evidenced | Not run | Open |
| F004-02 | Not evidenced | Not run | Open |
| F004-03 | Not evidenced | Not run | Open |
| F004-04 | Not evidenced | Not run | Open |
| F004-05 | Not evidenced | Not run | Open |
| F004-06 | Not evidenced | Not run | Open |

The statuses above reflect the evidence available for this portfolio exercise. Update them only when actual supporting artifacts have been reviewed.

## 5. Evidence Collection Rules

For each control:

1. Identify the accountable implementation owner.
2. Obtain the relevant approved procedure, configuration record, training record, or system evidence.
3. Record a traceable evidence reference and date.
4. Confirm the evidence relates to the intended AI-001 workflow and the correct environment.
5. Execute the corresponding test in an approved test environment.
6. Record the actual result, supporting evidence, and any defects.
7. Retest material failures after remediation.
8. Submit the evidence to the authorised closure reviewer.

Do not treat a planned test, hypothetical scenario, or draft procedure as evidence of successful implementation.

## 6. Closure Criteria

F-004 must remain open until the required human oversight controls are operationally defined and implemented, the required evidence is available, effectiveness testing has been completed, material defects have been addressed, and the authorised closure reviewer has accepted the evidence.

Completion of this checklist alone does not approve AI-001 for production.

## 7. Current Conclusion

The Human Oversight Matrix, test plan, and synthetic walkthrough records document the proposed control design and expected reviewer behaviour.

No evidence of actual operational control implementation has been established in the material reviewed so far. All six control areas therefore remain open for evidence collection and validation.

**Next action:** Obtain and verify implementation evidence for F004-01 through F004-06 before claiming that operational testing has passed or that F-004 is ready for closure.
