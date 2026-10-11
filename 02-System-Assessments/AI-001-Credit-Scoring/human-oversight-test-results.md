# HOV-01 — Synthetic Walkthrough Record

## Test Information

- **Test ID:** HOV-01
- **System:** AI-001 Credit Scoring System
- **Scenario:** Reviewer challenges an unsupported high-risk score
- **Exercise Type:** Synthetic tabletop walkthrough
- **Operational Test Status:** Not run
- **Exercise Assessment:** Expected reviewer response identified
- **Evidence Type:** Training exercise; no live system evidence supplied

## Scenario

A fictional credit applicant receives a high-risk score. The reviewer discovers that a key financial-data field is missing and cannot obtain sufficient supporting evidence to assess the score.

## Expected Reviewer Response

The reviewer identifies the data-quality gap, avoids unsupported reliance on the score, and follows the approved hold or escalation procedure.

## Evidence Required for Operational Execution

1. Synthetic case identifier and relevant score output.
2. Record of the missing field and the evidence available to the reviewer.
3. Investigation of whether the information was unavailable at source or lost during system processing.
4. Reviewer identity or authorised role, actions taken, rationale, and timestamps.
5. Escalation recipient, acknowledgement, subsequent action, and resolution or next-step decision.
6. Audit-log evidence and confirmation that no unauthorised customer-impacting action occurred.

## Acceptance Assessment

The exercise response is consistent with the expected control behaviour. However, the operational control cannot be declared effective without execution evidence demonstrating that the reviewer workflow, escalation process, and relevant safeguards function as intended.

## Result and Follow-up

- **Operational result:** Not run.
- **Defect status:** Not assessed through operational testing.
- **Next action:** Execute HOV-01 in an approved test environment using synthetic records and collect the evidence listed above.
- **Production approval:** Not granted by this exercise.

**Conclusion:** This walkthrough demonstrates understanding of the expected reviewer response. It does not establish operational effectiveness or close the related remediation item.

# HOV-02 — Synthetic Walkthrough Record

## Test Information

- **Test ID:** HOV-02
- **System:** AI-001 Credit Scoring System
- **Scenario:** Reviewer challenges a recommendation based on outdated financial data
- **Exercise Type:** Synthetic tabletop walkthrough
- **Operational Test Status:** Not run
- **Exercise Assessment:** Expected reviewer response identified
- **Evidence Type:** Training exercise; no live system evidence supplied

## Scenario

A fictional small-business applicant receives a high-risk score. The reviewer finds that an outdated financial-data field may have influenced the score. More recent, verified documents appear to conflict with the model recommendation. The reviewer cannot approve an override because the case exceeds their delegated authority.

## Expected Reviewer Response

The reviewer validates the conflicting evidence, records the challenge and supporting rationale, and escalates the case to an appropriately authorised decision-maker. No override or final decision should occur outside the reviewer's authority.

## Evidence Required for Operational Execution

1. Synthetic case reference and original model score.
2. Relevant financial-data fields, their dates, and source references.
3. Evidence supporting and contradicting the recommendation.
4. Reviewer role, assessment, rationale, actions, and timestamps.
5. Applicable delegation limit and evidence that the case was routed to an authorised decision-maker.
6. Escalation acknowledgement, authorisation, final outcome, and audit-trail records.

## Acceptance Assessment

The proposed response is consistent with the expected oversight control. Operational effectiveness remains unverified because no execution evidence has been supplied.

## Result and Follow-up

- **Operational result:** Not run.
- **Exercise result:** Expected reviewer response identified.
- **Defects:** Not assessed through operational testing.
- **Next action:** Execute HOV-02 in an approved test environment using synthetic records and verify the reviewer workflow, authority checks, escalation, and audit trail.
- **Production approval:** Not granted by this exercise.

**Conclusion:** The walkthrough demonstrates understanding of the challenge and escalation process. It does not establish that the operational control is effective or that remediation can be closed.

# HOV-03 — Synthetic Walkthrough Record

## Test Information

- **Test ID:** HOV-03
- **System:** AI-001 Credit Scoring System
- **Scenario:** Escalation submitted but acknowledgement not received
- **Exercise Type:** Synthetic tabletop walkthrough
- **Operational Test Status:** Not run
- **Exercise Assessment:** Expected response identified
- **Evidence Type:** Training exercise; no live system evidence supplied

## Scenario

A reviewer submits an escalation to the senior credit-risk owner concerning an unresolved AI-generated credit score. The case-management system records submission, but no acknowledgement is received within the proposed four-business-hour target.

## Expected Response

The responsible process owner verifies delivery and follows the approved backup escalation route if acknowledgement remains absent. The case stays subject to required safeguards until an authorised next step is determined.

## Evidence Required for Operational Execution

1. Case reference and reason for escalation.
2. Submission timestamp and communication or case-management reference.
3. Designated recipient and evidence of delivery, where available.
4. Acknowledgement status and timestamp, or evidence that acknowledgement was absent at the deadline.
5. Backup escalation recipient, timestamp, and confirmation of ownership.
6. Case status, actions taken, resolution or next-step decision, and audit-trail references.
7. Customer communication record where required by the approved process.

## Acceptance Assessment

The proposed response aligns with the expected control design. Operational effectiveness remains unverified because no execution evidence has been supplied.

## Result and Follow-up

- **Operational result:** Not run.
- **Exercise result:** Expected response identified.
- **Defects:** Not assessed through operational testing.
- **Next action:** Execute HOV-03 in an approved test environment and verify delivery tracking, deadline monitoring, backup escalation, ownership, and recordkeeping.
- **Production approval:** Not granted by this exercise.

**Conclusion:** This walkthrough demonstrates understanding of escalation traceability. It does not establish operational effectiveness or justify closing remediation.

# HOV-04 — Synthetic Walkthrough Record

## Test Information

- **Test ID:** HOV-04
- **System:** AI-001 Credit Scoring System
- **Scenario:** Supporting evidence unavailable because of an integration failure
- **Exercise Type:** Synthetic tabletop walkthrough
- **Operational Test Status:** Not run
- **Exercise Assessment:** Expected response identified
- **Evidence Type:** Training exercise; no live system evidence supplied

## Scenario

A reviewer can access the AI-generated credit-risk score but cannot access the explanation and supporting financial-data fields because of a simulated system integration failure. The normal review process requires those fields to be examined.

## Expected Response

The reviewer follows the approved hold or fallback procedure, records the failure, and escalates the issue. The case remains subject to required safeguards until an authorised next step is determined. If the relevant deadline is exceeded, the defined deadline-breach escalation is triggered.

## Evidence Required for Operational Execution

1. Affected synthetic case references and failure timestamps.
2. Failed integration component, error details, and affected data fields.
3. Incident reference, incident owner, and investigation of the number of affected cases.
4. Actions taken to prevent unsupported decisions while evidence is unavailable.
5. Escalation recipient, acknowledgement, target deadline, and any deadline breach.
6. Recovery procedure, restoration timestamps, and evidence that the restored data is complete and accessible.
7. Confirmation that the reviewer reassessed the case using the recovered evidence.
8. Documented next-step decision, outcome, and audit-trail references.

## Acceptance Assessment

The proposed response is consistent with the expected control design. The walkthrough also identifies the need to distinguish service restoration from successful recovery of the evidence required for credit review.

Operational effectiveness remains unverified because no execution evidence has been supplied.

## Result and Follow-up

- **Operational result:** Not run.
- **Exercise result:** Expected response identified.
- **Defects:** Not assessed through operational testing.
- **Next action:** Execute HOV-04 in an approved test environment using synthetic records. Test the failure, deadline-breach escalation, recovery, and controlled resumption of review.
- **Production approval:** Not granted by this exercise.

**Conclusion:** The walkthrough demonstrates understanding of fallback and incident escalation. It does not establish that the operational control is effective or justify closing remediation.

# HOV-05 — Synthetic Walkthrough Record

## Test Information

- **Test ID:** HOV-05
- **System:** AI-001 Credit Scoring System
- **Scenario:** Audit-trail failure during human review
- **Exercise Type:** Synthetic tabletop walkthrough
- **Operational Test Status:** Not run
- **Exercise Assessment:** Expected response identified
- **Evidence Type:** Training exercise; no live system evidence supplied

## Scenario

A reviewer challenges an AI-generated credit-risk score and escalates the case appropriately. However, a logging failure prevents the system from recording the reviewer's rationale and subsequent action history.

## Expected Response

The reviewer follows the approved logging-failure procedure. An authorised alternative record is used if the procedure permits it, and actions requiring unavailable audit evidence remain subject to the appropriate safeguards. Once logging is restored, required records are reconciled and discrepancies are investigated.

## Evidence Required for Operational Execution

1. Synthetic case reference and incident reference.
2. Failure timestamp, affected functions, and investigation of the scope of missing records.
3. Reviewer identity or authorised role, rationale, actions, and escalation details.
4. Evidence that any alternative record was authorised, protected against unauthorised changes, and accessible only to authorised personnel.
5. Logging restoration timestamp and evidence that the service is functioning correctly.
6. Reconciliation of relevant actions during the failure period, including investigation of missing, duplicated, or inconsistent records.
7. Documented disposition of discrepancies and evidence that required safeguards operated throughout the incident.

## Acceptance Assessment

The proposed response aligns with the expected control design. Operational effectiveness remains unverified because no execution evidence has been supplied.

## Result and Follow-up

- **Operational result:** Not run.
- **Exercise result:** Expected response identified.
- **Defects:** Not assessed through operational testing.
- **Next action:** Execute HOV-05 in an approved test environment using synthetic records. Simulate the logging failure, verify the approved fallback, restore logging, and test reconciliation and record integrity.
- **Production approval:** Not granted by this exercise.

**Conclusion:** The walkthrough demonstrates understanding of audit-trail resilience. It does not establish that the operational control is effective or justify closing remediation.

# Human Oversight Test Results — AI-001 Credit Scoring

**System:** LendWise AI-001 — Credit Scoring  
**Finding:** F-004 — Human Oversight Requirements Incomplete  
**Test Environment:** Authorised test environment (assumed for this training exercise; execution evidence pending)  
**Document Status:** Test results pending evidence  
**Overall Test Status:** Not verified  
**Finding Status:** Open — Remediation Required

## 1. Purpose

This document records the results of tests assessing whether AI-001 human-oversight controls operate as intended.

Expected outcomes are defined in the test plan. Actual results must be supported by evidence from the test environment. A test must not be marked Pass solely because the expected behaviour has been documented.

## 2. Test Result Recording Requirements

For each test, record:

- Test ID and test date.
- Expected result.
- Actual result.
- Evidence reference.
- Test status: Pass, Fail, Blocked / Inconclusive, or Not run.
- Defect and remediation, where applicable.
- Retest result, where applicable.
- Tester and independent reviewer, where applicable.

Until actual results and supporting evidence are available, the test status remains `Not verified` or `Not run`, as appropriate to the evidence available.

## 3. Reviewer Authority Test Results

### RAT-01 — Role-Based Access and Permitted Actions

**Expected Result:** Reviewer can access only the information and actions permitted by their role.

**Actual Result:** Pending evidence.

**Evidence Reference:** Pending.

**Test Status:** Not verified.

**Defect and Remediation:** Pending test evidence.

**Retest Result:** Not applicable yet.

**Closure Evidence Required:** Role and permission configuration, test user role, observed access results, relevant application/backend logs and evidence that prohibited actions are inaccessible.

### RAT-02 — Unauthorised Override Attempt

**Expected Result:** System blocks the action or routes the case through an approved authorisation workflow.

**Actual Result:** Pending evidence.

**Evidence Reference:** Pending.

**Test Status:** Not verified.

**Defect and Remediation:** Pending test evidence.

**Retest Result:** Not applicable yet.

**Closure Evidence Required:** Attempted action, role and permissions, application/API response where applicable, persisted score and decision state, and audit/security logs. Verify that the action was prevented or properly authorised and that required events were recorded.

### RAT-03 — Challenge and Review Workflow

**Expected Result:** Challenge is recorded with rationale and supporting evidence; case follows the approved review workflow.

**Actual Result:** Pending evidence.

**Evidence Reference:** Pending.

**Test Status:** Not verified.

**Defect and Remediation:** Pending test evidence.

**Retest Result:** Not applicable yet.

**Closure Evidence Required:** Challenge record, rationale, supporting evidence references, case status, assigned reviewer, timestamps, workflow history and relevant audit events.

### RAT-04 — Approval Authority and Decision Routing

**Expected Result:** Approval is prevented and the case is routed to the authorised decision-maker.

**Actual Result:** Pending evidence.

**Evidence Reference:** Pending.

**Test Status:** Not verified.

**Defect and Remediation:** Pending test evidence.

**Retest Result:** Not applicable yet.

**Closure Evidence Required:** Reviewer role and authority, attempted approval, observed system response, routing record, authorised decision-maker assignment and persisted case state.

### RAT-05 — Unauthorised Modification and Audit Trail

**Expected Result:** Unauthorised modification is prevented or detected; the audit trail preserves the relevant event history.

**Actual Result:** Pending evidence.

**Evidence Reference:** Pending.

**Test Status:** Not verified.

**Defect and Remediation:** Pending test evidence.

**Retest Result:** Not applicable yet.

**Closure Evidence Required:** Original record and integrity reference, tester role and permissions, attempted modification, before-and-after comparison, relevant application/backend/security logs and verification of required audit events.

### RAT-06 — API-Level Authorisation and Alternate Access Paths

**Expected Result:** To be confirmed against the approved Reviewer Authority test plan before execution. The test should establish whether applicable authorisation controls are enforced through relevant API/server-side routes and whether persisted outcomes and required audit events are correct.

**Actual Result:** Pending evidence.

**Evidence Reference:** Pending.

**Test Status:** Not verified.

**Defect and Remediation:** Pending test evidence.

**Retest Result:** Not applicable yet.

**Closure Evidence Required:** Approved test criteria, tester role and permissions, relevant API/backend response, persisted state, audit/security events and any defect/retest records.

## 4. Defect and Remediation Register

No defect conclusion is recorded here because final test evidence has not yet been supplied.

For each failed or inconclusive test, record:

- Defect ID.
- Related test ID.
- Expected versus actual behaviour.
- Customer and operational impact.
- Root cause or investigation status.
- Accountable remediation owner.
- Corrective action and target date.
- Retest evidence and outcome.
- Independent review decision.

## 5. Overall Assessment

**Overall Test Status:** Not verified — supporting evidence pending.

The expected outcomes for RAT-01 through RAT-05 have been documented. Final outcomes and evidence have not yet been established in this record. RAT-06 acceptance criteria must also be confirmed against the approved test plan.

### RAT-01 — Role-Based Access and Permitted Actions

**Control Objective:** Ensure reviewers can access only the information and actions permitted by their assigned roles.

**Expected Result:** Reviewer can access only the information and actions permitted by their role.

**Reported Actual Result:** Permitted actions worked and unauthorised actions were blocked.

**Evidence References:**
- Permission configuration/log: Reference to be recorded.
- Test result report: Reference to be recorded.
- System action responses: Reference to be recorded.
- Backend and security logs: Reference to be recorded.
- Exact attempted actions: Reference to be recorded.
- Persisted-state verification: Reference to be recorded.

**Evidence Assessment:** The reported observation is consistent with the expected result. The test evidence must be reviewed to confirm the tested role, exact attempted actions, application and backend enforcement, persisted state, and required security logging.

**Provisional Test Status:** Pass — pending evidence verification.

**Defect and Remediation:** No defect reported in the supplied observation. This does not establish that no defect exists outside the tested scope.

**Retest Result:** Not applicable unless a defect is identified or retesting is otherwise required.

**Independent Review:** Pending.

**Closure Note:** RAT-01 may be treated as passed only after the supporting evidence is available, traceable and sufficient to demonstrate that the acceptance criteria were met.

**F-004 Closure Decision:** Open — Remediation Required.

F-004 must not be closed until required controls are implemented, the relevant tests are executed and evidenced, defects are addressed or formally risk-accepted by an authorised decision-maker, and an independent review supports the closure decision.

**AI-001 Production Approval:** Not Approved — Remediation Required.

### RAT-02 — Unauthorised Override Attempt

**Control Objective:** Ensure unauthorised reviewers cannot override an AI-generated credit-risk outcome or bypass the approved authorisation workflow.

**Expected Result:** System blocks the action or routes the case through an approved authorisation workflow.

**Reported Actual Result:** The system blocked the unauthorised override, preserved the original decision and recorded the attempt in the required audit/security logs.

**Evidence References:**
- Test report: Reference to be recorded.
- Reviewer role and permission configuration: Reference to be recorded.
- Application response and authorisation result: Reference to be recorded.
- Original and post-test decision state: Reference to be recorded.
- Audit/security event and correlation ID: Reference to be recorded.
- Relevant backend/API evidence, where applicable: Reference to be recorded.

**Evidence Assessment:** The reported observation meets the expected control behaviour. Final acceptance depends on reviewing the underlying records and confirming that the original decision remained unchanged and the required security event was persisted and retrievable.

**Provisional Test Status:** Pass — pending evidence verification.

**Defect and Remediation:** No defect reported in the supplied observation. This does not establish that no defect exists outside the tested scope.

**Retest Result:** Not applicable unless a defect is identified or retesting is otherwise required.

**Independent Review:** Pending.

**Closure Note:** RAT-02 may be treated as passed after the supporting evidence is verified as complete and traceable.

### RAT-03 — Challenge and Review Workflow

**Control Objective:** Ensure a reviewer challenge is documented with rationale and supporting evidence and follows the approved review workflow.

**Expected Result:** Challenge is recorded with rationale and supporting evidence; case follows the approved review workflow.

**Reported Actual Result:** The following evidence was identified: case record, evidence reference, reviewer rationale and decision history. Adherence to the complete approved review workflow remains to be verified.

**Evidence References:**
- Case record: Reference to be recorded.
- Supporting evidence reference: Reference to be recorded.
- Reviewer rationale: Reference to be recorded.
- Decision history: Reference to be recorded.
- Assignment and escalation records, where required: Pending verification.

**Evidence Assessment:** The reported evidence supports challenge documentation and decision traceability. It does not yet establish that every required assignment, review and escalation step occurred in accordance with the approved workflow.

**Provisional Test Status:** Blocked / Inconclusive — pending workflow verification.

**Defect and Remediation:** No confirmed defect recorded. Verify the workflow history and identify any missing required steps before deciding whether remediation is necessary.

**Retest Result:** Not applicable unless a defect is identified or retesting is required.

**Independent Review:** Pending.

**Closure Note:** RAT-03 may be marked Pass if the evidence confirms that the challenge was properly recorded and all required workflow steps were followed. If a required step was omitted, assess and record the resulting control failure.

### RAT-04 — Approval Authority and Decision Routing

**Control Objective:** Ensure reviewers cannot approve exceptions outside their delegated authority and that cases are routed to the appropriate authorised decision-maker.

**Expected Result:** Approval is prevented and the case is routed to the authorised decision-maker.

**Reported Actual Result:** A reviewer attempted to approve an exception outside their delegated authority. The case was routed to the correct authorised decision-maker. Logs, timestamps and SLA information were recorded.

**Evidence References:**
- Reviewer role and delegated-authority configuration: Reference to be recorded.
- Exception case record: Reference to be recorded.
- System response and routing record: Reference to be recorded.
- Audit logs and event/correlation IDs: Reference to be recorded.
- Timestamps and SLA record: Reference to be recorded.
- Final authorised decision and persisted case state: Reference to be recorded.

**Evidence Assessment:** The reported behaviour is consistent with the expected control. Verify that the unauthorised reviewer could not approve the exception, that the receiving decision-maker had the appropriate authority, and that routing, timestamps and SLA records are complete and retrievable.

**Provisional Test Status:** Pass — pending evidence verification.

**Defect and Remediation:** No defect reported in the supplied observation. This does not establish that no defect exists outside the tested scope.

**Retest Result:** Not applicable unless a defect is identified or retesting is otherwise required.

**Independent Review:** Pending.

**Closure Note:** RAT-04 may be treated as passed after the supporting evidence confirms that the authority boundary was enforced and the case was routed and recorded correctly.

### RAT-05 — Unauthorised Audit-Record Modification

**Test objective:** Verify that unauthorised modification or bypass of an audit record associated with an override is prevented or detected, and that the relevant event history remains preserved.

**Test scenario:** A reviewer attempts to modify or bypass the audit record associated with an override without the required authority.

**Expected result:** Unauthorised modification is prevented or detected, and the audit trail preserves the relevant event history.

**Reported observation:** The unauthorised modification was prevented or detected, and the relevant audit history was preserved.

**Evidence reported:**
- Access-control configuration
- Audit logs
- Integrity-check results

**Provisional result:** Pass — evidence verification pending.

**Evidence verification required:**
1. Confirm the original override audit record remained intact.
2. Verify the access-control configuration prevents the unauthorised action through the relevant application and API paths.
3. Confirm the attempted modification or bypass generated the required audit or security event.
4. Verify integrity-check results demonstrate that the relevant audit history was not altered or deleted.
5. Record exact evidence references, test timestamp, test environment, and any defects.

**Limitation:** This is a reported training-test outcome. The result must not be treated as independently verified operational evidence until the underlying records have been reviewed.

**Closure status:** RAT-05 does not independently establish that F-004 is closed. The overall finding remains open pending completion and verification of all required tests and independent review.
