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

# AI-001 Audit Logging and Record Integrity Test Plan

**System:** LendWise AI-001 — Credit Scoring  
**Workstream:** F-004 Human Oversight — Audit Logging and Record Integrity  
**Document Status:** Proposed Test Plan  
**Operational Test Status:** All tests — `Not run`  
**Approval Status:** AI-001 remains `NOT APPROVED — REMEDIATION REQUIRED`

## 1. Purpose

Verify whether material AI-001 credit-scoring and human-oversight events are traceable, attributable, time-ordered, retrievable and protected against unauthorised alteration or deletion.

The tests also assess whether missing, delayed or inconsistent events are detected, investigated and recovered transparently.

This document defines proposed tests. It does not demonstrate that controls have been implemented or passed operational testing.

## 2. Scope

The test plan covers:

- AI-generated credit scores and model/version references.
- Reviewer challenges, assignments, escalations, acknowledgements and resolutions.
- Human overrides, rationales and final lending decisions.
- Unauthorised attempts to alter or delete audit records.
- Event timestamps, central log ingestion and event ordering.
- Missing or delayed events and monitoring alerts.
- Logging-service outages, recovery and event reconciliation.
- Relevant application, API, backend and security-log controls.

Use synthetic cases in an authorised test environment. Do not commit real customer records, credentials or unrestricted production logs to the public GitHub repository.

## 3. Test Result Definitions

- **Pass:** The test was executed and all acceptance criteria were met with sufficient evidence.
- **Fail:** Execution confirmed that one or more required controls were ineffective.
- **Blocked / Inconclusive:** Evidence or access is insufficient, or investigation remains incomplete.
- **Not run:** The operational test has not been executed. Discussing a scenario or drafting a test plan does not constitute operational testing.

A displayed “Permission denied” message, verbal assurance, eventual event delivery or an apparently correct lending decision is not sufficient evidence by itself.

## 4. Common Evidence Requirements

For each test, record:

1. Test ID and synthetic case/challenge ID.
2. Test date, environment, tester role and relevant permissions.
3. Expected outcome and actual observed behaviour.
4. Event IDs, correlation IDs, actor/system identity and timestamps.
5. Relevant application, API, backend, security, monitoring and central audit logs.
6. Model/version and input-snapshot references where applicable.
7. Before-and-after record comparison or integrity verification where relevant.
8. Alert generation, delivery, acknowledgement, ownership transfer and escalation evidence where applicable.
9. Search scope and method if an expected event cannot be found.
10. Defect reference, impact assessment, root cause, remediation owner, retest result and independent review.

Never fabricate, backdate, silently overwrite or misrepresent missing original events. Any recovered or reconstructed information must be clearly labelled, retain its provenance and link to the relevant investigation.

---

## 5. Test Cases

### ALR-01 — Challenge and Resolution Traceability

**Objective:** Verify that a reviewer challenge can be traced through assignment, investigation, escalation where applicable, resolution and final decision.

**Scenario:** A synthetic credit case is challenged and later resolved. The application shows the challenge and final decision, but the central audit trail lacks the required escalation acknowledgement and ownership-transfer events.

**Expected Outcomes:**

- Required challenge lifecycle events are recorded and retrievable.
- Events identify the relevant case/challenge, actor or system, event type, timestamp and outcome.
- Event relationships and sequence can be reconstructed.
- Missing events trigger investigation.
- A confirmed missing required event is recorded as a control failure.

**Required Evidence:**

- Synthetic case and challenge IDs.
- Application event history and central audit records.
- Assignment, escalation, acknowledgement, ownership-transfer, resolution and final-decision records.
- Event/correlation IDs and timestamps.
- Search scope, expected-versus-actual event list, investigation findings, defect and retest evidence.

**Failure Criteria:**

- A required event is missing or materially incomplete.
- An event cannot be attributed to the relevant actor or case.
- The event sequence cannot be reliably reconstructed.
- Verbal confirmation is used as a substitute for required records.

**Initial Status:** `Not run`

### ALR-02 — Escalation After SLA Breach

**Objective:** Verify that a breached escalation or assignment SLA is detected and that notification, acknowledgement, ownership and controlled case handling are traceable.

**Scenario:** A challenge remains unassigned beyond the approved SLA. The primary escalation owner is unavailable and the queue is full.

**Expected Outcomes:**

- The approved SLA and clock-start rule are documented.
- The breach is detected within the approved monitoring window.
- The required escalation or backup route is triggered.
- Delivery, acknowledgement and explicit ownership acceptance are evidenced where required.
- The case remains in a controlled state until an eligible owner accepts responsibility.
- Required customer communication and safeguards are documented.

**Required Evidence:**

- Case/challenge ID, approved SLA and clock-start timestamp.
- Breach timestamp and queue/assignment state.
- Alert generation, delivery and acknowledgement records.
- Backup/deputy activation, reassignment and ownership acceptance.
- Controlled case state and relevant customer communication.
- Audit logs, defect record and retest evidence.

**Failure Criteria:**

- The breach is not detected as required.
- Required escalation is not triggered.
- No eligible owner accepts responsibility under the approved procedure.
- The case proceeds without required safeguards.
- Required escalation or ownership events are missing.

**Initial Status:** `Not run`

### ALR-03 — Unauthorised Alteration/Deletion and Security-Event Logging

**Objective:** Verify two separate control objectives:

1. Unauthorised alteration or deletion of audit records is prevented.
2. Unauthorised attempts are recorded in security logs when required by approved policy.

**Scenario:** An ordinary reviewer attempts to delete an audit event. The interface displays “Permission denied” and the original record appears intact, but the attempted deletion is absent from security logs even though policy requires it to be recorded.

**Expected Outcomes:**

- Unauthorised changes are prevented through relevant application, API and server-side routes.
- The original audit record remains intact.
- The attempted deletion is recorded in the required security logs.
- The security event contains required context, such as actor/role, target record, attempted action, outcome, timestamp and event/correlation ID.
- Required monitoring can detect the event.
- Record integrity and security-event logging are assessed independently.

**Required Evidence:**

- Synthetic audit event ID and original record/integrity reference.
- Tester identity, role and permission configuration.
- Application response and relevant API/backend authorisation evidence.
- Before-and-after record comparison or approved integrity verification.
- Security logs and monitoring evidence, or a documented search establishing that the required event is absent.
- Defect, impact assessment, remediation, retest and independent review.

**Failure Criteria:**

- Unauthorised deletion or alteration succeeds.
- The original audit record is changed or lost.
- A required security event is not logged.
- The test is marked Pass based only on the interface displaying “Permission denied.”
- Relevant alternate access paths have not been tested where they are in scope.

**Result Handling:** If the missing security event is confirmed, mark the test `Fail` even if deletion was prevented. If evidence is incomplete, use `Blocked / Inconclusive` until investigated.

**Initial Status:** `Not run`

### ALR-04 — Missing or Delayed Event Detection

**Objective:** Verify that material events reach the central audit log within the approved latency threshold and that missing or delayed events are detected.

**Scenario:** The application records an escalation at 10:15 UTC, but the central audit log receives it at 11:30 UTC. The approved control requires central availability within five minutes.

**Expected Outcomes:**

- The event is available centrally within the approved five-minute threshold.
- The measurement convention distinguishes event occurrence time from ingestion time.
- Monitoring detects a breach within its approved detection window.
- The original occurrence time remains traceable.
- The delay is investigated; eventual arrival does not erase the original SLA breach.

**Required Evidence:**

- Application event timestamp and central ingestion timestamp.
- Event/correlation ID and source system.
- Approved latency threshold and measurement convention.
- Monitoring configuration, alert timestamp, delivery and acknowledgement.
- Relevant ingestion/system logs.
- Root-cause analysis, affected-event scope, defect and retest evidence.

**Failure Criteria:**

- Event availability exceeds the approved threshold.
- Required monitoring fails to detect the delay.
- Timestamps cannot distinguish occurrence from ingestion.
- Missing or delayed events are not reconciled or investigated.

**Result Handling:** The described scenario breaches the five-minute timeliness requirement. Assess monitoring effectiveness separately; it may also fail if the delay was not detected as required.

**Initial Status:** `Not run`

### ALR-05 — Timestamp Consistency and Event Ordering

**Objective:** Verify that timestamps follow the approved UTC convention and that event order and SLA calculations remain reliable.

**Scenario:** The application records an override at 14:05 UTC, while the central audit log records the same event ID at 13:05 UTC. The team suspects a timezone conversion issue.

**Expected Outcomes:**

- Timestamp format, timezone, precision and event-time/ingestion-time conventions are documented.
- Source clock synchronisation and timestamp transformations are checked.
- The discrepancy is explained using evidence rather than assumption.
- Event order, actor attribution and SLA calculations remain reliable.
- Any correction follows an authorised, traceable process and preserves the original value.

**Required Evidence:**

- Original application event and central audit record.
- Event/correlation ID, actor and source/ingestion timestamps.
- UTC configuration and clock-synchronisation evidence.
- Relevant time-service, ingestion and transformation logs.
- Reconstructed event sequence, root-cause conclusion, defect and retest evidence.

**Failure Criteria:**

- Timestamp conventions are not followed or remain ambiguous.
- The discrepancy makes event ordering, attribution or SLA assessment unreliable.
- Original evidence is silently overwritten or backdated.
- The test is closed without a documented investigation.

**Result Handling:** Use `Blocked / Inconclusive` during investigation. Mark `Fail` if a required timestamp or traceability control is confirmed ineffective. Consider Pass only after remediation and successful retesting.

**Initial Status:** `Not run`

### ALR-06 — Override Traceability and Rationale

**Objective:** Verify that a human override can be reconstructed and scrutinised, including the original AI outcome and the human decision and rationale.

**Scenario:** A reviewer overrides an AI-generated risk score. The audit record contains the reviewer ID and new decision but omits the original AI outcome and the override reason.

**Expected Outcomes:**

- Required records include the original AI outcome/score, model/version reference, case reference, final human decision, reviewer identity and authority, timestamp and rationale.
- The record distinguishes the AI recommendation from the human decision.
- Override records are retrievable for case review and aggregate monitoring.
- Historical gaps are assessed without misrepresenting newly reconstructed information as contemporaneous evidence.

**Required Evidence:**

- Synthetic case and override event IDs.
- Original AI outcome/score and model/version reference.
- Final human decision, reviewer identity/authority, rationale and timestamps.
- Application and central audit records.
- Workflow configuration, defect record and retest evidence.

**Failure Criteria:**

- Required original outcome, decision, actor/authority, rationale or timestamp is missing.
- The AI recommendation and human decision cannot be distinguished.
- Verbal assurance substitutes for required audit evidence.
- Historical records are silently changed to conceal missing fields.

**Additional Note:** Override records support monitoring of human-review behaviour but do not alone establish model accuracy. Accuracy analysis also requires appropriate outcome labels, evaluation data and defined metrics.

**Initial Status:** `Not run`

### ALR-07 — Logging Service Outage and Recovery

**Objective:** Verify that logging outages are detected, controlled, recovered transparently and reconciled so material events are not silently lost.

**Scenario:** The central audit logging service is unavailable for 20 minutes. Reviewers can still submit lending decisions, but those decisions are not recorded centrally during the outage. After recovery, the team cannot establish whether all events were recovered.

**Expected Outcomes:**

- The outage is detected and recorded, with an accountable incident owner.
- The approved fallback or controlled-pending procedure is followed.
- Decisions do not bypass required governance safeguards merely because logging is unavailable.
- Queued or buffered events, where supported, are recovered and reconciled against source records.
- Original event times remain distinguishable from recovery/ingestion times.
- Missing, duplicate, out-of-order or irrecoverable events are identified and assessed.
- Affected decisions receive any required review.

**Required Evidence:**

- Incident ID, outage timeline and response logs.
- Monitoring alerts and incident ownership records.
- Application/source records and central logs before, during and after the outage.
- Queue/buffer and recovery/replay evidence where applicable.
- Expected-versus-received event reconciliation.
- Affected case list and documented safeguards/review decisions.
- Root cause, corrective action, defect and retest evidence.

**Failure Criteria:**

- The outage is not detected or handled according to the approved process.
- Event gaps are not detected or reconciled.
- Decisions proceed without required safeguards.
- Recovery is claimed without evidence of event completeness.
- Missing events are silently recreated, backdated or represented as original records.

**Result Handling:** Keep the control open until event completeness, recovery effectiveness and safeguards for affected decisions are evidenced. If events are irrecoverably missing, document the limitation and assess the impact rather than claiming the control passed.

**Initial Status:** `Not run`

---

## 6. Defect and Remediation Record

For every failed or inconclusive test, record:

- Defect ID and test ID.
- Expected versus actual behaviour.
- Severity and customer, decision, traceability, regulatory and operational impact.
- Confirmed root cause or `Under investigation`.
- Affected systems, event types, cases and time window.
- Accountable owner and corrective action.
- Due date and remediation evidence.
- Retest date, evidence and outcome.
- Independent reviewer and documented closure decision.

## 7. Workstream Closure Criteria

Do not close the F-004 audit-logging workstream merely because this document exists or the tabletop scenarios were answered correctly.

Closure requires:

1. Approved control requirements and timestamp/SLA conventions.
2. Evidence that relevant controls are implemented in the intended environment.
3. Operational execution in a suitable authorised environment.
4. Evidence retained for every test.
5. Defects remediated and retested, or formally risk-accepted by an authorised decision-maker.
6. Independent review of the evidence.
7. A documented closure decision.

Until those conditions are met, keep the workstream open or in progress under the approved tracker convention. AI-001 remains `NOT APPROVED — REMEDIATION REQUIRED`.

## 8. Test Status Register

| Test ID | Test Name | Operational Status |
|---|---|---|
| ALR-01 | Challenge and resolution traceability | Not run |
| ALR-02 | Escalation after SLA breach | Not run |
| ALR-03 | Unauthorised alteration/deletion and security-event logging | Not run |
| ALR-04 | Missing or delayed event detection | Not run |
| ALR-05 | Timestamp consistency and event ordering | Not run |
| ALR-06 | Override traceability and rationale | Not run |
| ALR-07 | Logging service outage and recovery | Not run |
