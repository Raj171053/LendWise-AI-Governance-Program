# F004-04 — Audit Logging and Record Integrity Test Plan

## 1. Purpose

Verify that material AI-001 credit-scoring and human-oversight events are recorded accurately, can be reconstructed, and are protected against unauthorised alteration or deletion.

## 2. Current status

- Control ID: F004-04
- Proposed control owner: Head of Credit Risk
- Technical implementation owner: To be assigned
- Test status: Not run
- Test data: Synthetic only
- Independent closure reviewer: AI Governance / Model Risk authority
- Production status: NOT APPROVED — REMEDIATION REQUIRED

This plan defines proposed controls and tests. It does not demonstrate that logging controls are implemented or effective.

## 3. Control requirements

1. Material events have identifiable actors or system identities, event timestamps, case references and recorded outcomes.
2. Challenge, escalation, assignment, acknowledgement, override and resolution events can be reconstructed in the correct sequence.
3. Records identify the relevant model version and scoring event where required.
4. Access to audit records is restricted to authorised roles.
5. Unauthorised alteration and deletion of audit records are prevented or reliably detected.
6. Missing, delayed, duplicated or inconsistent log events can be identified and investigated.
7. Logging failures trigger an approved response, with accountable ownership and a defined recovery process.
8. Timestamps are consistently defined and sufficiently reliable for reconstructing event order.
9. Retention, access, monitoring and disposal follow approved policies and applicable requirements.

## 4. Proposed test cases

| Test ID | Scenario | Expected result | Status |
|---|---|---|---|
| ALR-01 | A reviewer raises and resolves a synthetic credit challenge | Challenge, ownership, actions and resolution are recorded and traceable | Not run |
| ALR-02 | An escalation is triggered after an SLA breach | Trigger, notification, delivery, acknowledgement and subsequent ownership are traceable | Not run |
| ALR-03 | An unauthorised user attempts to alter or delete an audit record | The action is prevented or reliably detected and investigated | Not run |
| ALR-04 | A required audit event is missing or delayed | Monitoring or reconciliation identifies the gap and initiates the approved response | Not run |
| ALR-05 | Events from relevant systems have inconsistent timestamps or ordering | The discrepancy can be detected and investigated using defined timestamp conventions and correlation references | Not run |
| ALR-06 | An authorised reviewer performs an override | The record captures the actor, authority, original outcome, rationale, resulting outcome and timestamp | Not run |
| ALR-07 | The logging service becomes unavailable | The approved failure procedure activates, responsibility is assigned, and records are recovered or gaps are explicitly documented | Not run |

## 5. Evidence to capture

For each test, retain:

- Test ID, synthetic case ID and environment
- Tester identity and role
- Preconditions, actions and timestamps
- Expected versus actual event records
- Relevant application, backend and audit records
- Event IDs or correlation IDs
- Model/version and case references where applicable
- Access-control and integrity-check evidence
- Detected gaps, defect references and remediation owner
- Retest result and independent review decision

## 6. Acceptance criteria

A test passes only when the expected logging and integrity behaviour is demonstrated, supporting evidence is retained, and the result is reviewed appropriately.

A test fails when a required event is lost without detection, an unauthorised change succeeds without reliable detection, or the event sequence cannot be reconstructed contrary to the approved control requirements.

A test is Blocked/Inconclusive when evidence is insufficient to determine whether the control worked.

Missing evidence must not be treated as a pass. A successfully completed business process does not by itself prove that the audit trail is complete.

## 7. Failure handling and recovery

When logging is unavailable or a material event is missing:

1. Record the issue and identify potentially affected cases.
2. Assign an accountable incident or control owner.
3. Follow the approved workflow for preserving required records and controlling affected decisions.
4. Investigate the cause, scope and integrity of the available evidence.
5. Recover records where technically and procedurally valid, distinguishing recovered records from original contemporaneous events.
6. Document irrecoverable gaps without fabricating or backdating events.
7. Retest the relevant control after remediation.

Any temporary alternative recordkeeping process must be approved, access-controlled, auditable and reconciled when normal service is restored.

## 8. Closure requirements

F004-04 remains open until the required logging and integrity controls are implemented, relevant tests pass, defects are addressed, evidence is independently reviewed, and the remediation tracker records an authorised closure decision.

## 9. Data protection

Use synthetic cases and fictitious identifiers. Do not commit real customer records, credentials, unrestricted production logs or sensitive documents to the public repository.

## ALR-01 — Missing Escalation and Ownership Events

**Scenario:** A synthetic credit challenge has a recorded challenge and final decision, but the escalation acknowledgement and ownership-transfer events are missing.

**Expected result:** The required events are recorded accurately and can be traced to the relevant case, actor or system identity, and timestamps.

**Observed result:** The challenge and final decision are present. The escalation acknowledgement and ownership-transfer events cannot be located in the available records.

**Assessment:** The audit-trail completeness requirement is not demonstrated. Treat this as a failure of the logging control if the required events are confirmed missing; otherwise, retain Blocked/Inconclusive while investigating the evidence gap.

**Evidence to retain:**
- Synthetic case ID and challenge ID
- Event IDs, reviewer or system identities, and available timestamps
- Existing challenge and final-decision records
- Log search scope, relevant backend records and audit-log results
- Investigation steps, findings and integrity checks
- Expected versus actual event sequence
- Defect reference, remediation owner and retest evidence

**Remediation:** Determine whether the events were never generated, were lost, were filtered from the available view, or were recorded in another authoritative system. Correct the root cause and test the logging workflow again.

**Evidence integrity:** Do not backdate or fabricate missing events. Any recovered or reconstructed information must be clearly identified, dated when recovered, and linked to its source.

**Status:** Not run as an operational test; scenario assessment identifies an evidence gap.

**Production implication:** F004-04 remains open until the required logging controls are implemented, tested and independently reviewed.

### ALR-03 — Unauthorised Audit-Record Deletion

**Scenario:** A user with ordinary reviewer permissions attempts to delete a synthetic audit event. The interface displays “Permission denied.”

**Initial observation:** The application denied the attempted deletion. This is preliminary evidence that the interface-level restriction operated.

**Test result:** Blocked/Inconclusive pending verification of record preservation, server-side authorisation and relevant audit evidence.

**Expected result:** The unauthorised deletion is prevented across relevant access paths; the original record remains intact; and the attempted action is logged where required by the approved policy.

**Evidence required:**
- Synthetic event ID and original record or integrity reference
- Reviewer role and permission configuration
- Application response and relevant API/backend test results
- Before-and-after record comparison or integrity verification
- Relevant audit logs and correlation IDs
- Evidence of the attempted action being recorded, where required
- Independent reviewer assessment

**Remediation:** Investigate any successful unauthorised modification, missing required security event or integrity discrepancy. Correct the control and retest.

**Status:** Not run as an operational test.

**Closure criteria:** Relevant access paths have been tested, the record-integrity requirements are satisfied, supporting evidence is retained, and the result is independently reviewed.

**Production implication:** F004-04 remains open until implementation and successful testing are evidenced.
