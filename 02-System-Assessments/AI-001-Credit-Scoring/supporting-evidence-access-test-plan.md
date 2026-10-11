# F004-02 — Supporting Evidence Access Test Plan

## 1. Purpose

Assess whether authorised credit reviewers can access complete, relevant and sufficiently reliable supporting evidence to challenge AI-001 credit scores and make informed human decisions.

## 2. Current status

- Control ID: F004-02
- Enterprise risk context: High
- Test status: Not run
- Test environment: To be confirmed
- Test data: Synthetic only
- Proposed control owner: Head of Credit Risk
- Independent reviewer: AI Governance / Model Risk authority
- Production status: NOT APPROVED — REMEDIATION REQUIRED

This document defines proposed tests. It does not establish that the controls have been implemented or tested.

## 3. Control requirements

1. Authorised reviewers can access the supporting data needed for the assigned case.
2. Source, timestamp and data-quality information is available where relevant.
3. Missing, stale, inconsistent or disputed data are visible to the reviewer.
4. Reviewers can record a challenge and submit a case for correction or escalation.
5. If required evidence is unavailable or unreliable, the workflow prevents unsupported approval and provides a defined fallback.
6. Access is restricted according to role, and access to sensitive information is appropriately logged.
7. The reviewer can distinguish source data, model-generated explanations and their own assessment.

## 4. Proposed test cases

| Test ID | Scenario | Expected result | Status |
|---|---|---|---|
| SEA-01 | Reviewer opens a complete synthetic credit case | Required supporting fields and source references are available to the authorised reviewer | Not run |
| SEA-02 | A required financial field is missing | Missing data are clearly indicated; the reviewer can investigate or escalate rather than assume a value | Not run |
| SEA-03 | A financial field is stale or conflicts with newer verified evidence | The discrepancy and relevant timestamps are visible; the reviewer can challenge the case | Not run |
| SEA-04 | A source-data integration fails | The workflow identifies the unavailable evidence and follows the approved pause, escalation or fallback procedure | Not run |
| SEA-05 | A reviewer attempts to access a case outside their authorised scope | Access is denied or restricted according to policy, and the relevant event is logged | Not run |
| SEA-06 | A reviewer challenges a score based on conflicting evidence | The challenge, rationale, evidence references, responsible owner and outcome are recorded | Not run |

## 5. Evidence to capture

For each test, record:

- Test ID, date/time and tester role
- Synthetic case reference and test environment
- Required evidence and expected access permissions
- Actual data displayed, including source and timestamp where applicable
- Missing-data, stale-data or conflict indicators
- Actions attempted and system responses
- Relevant access, application and audit logs
- Expected versus actual result
- Pass, Fail or Blocked/Inconclusive
- Defect reference, remediation owner and retest result
- Independent reviewer and review decision

## 6. Acceptance criteria

A test passes only when the expected control behaviour is demonstrated and the supporting evidence is retained.

A test fails when the system exposes a material control weakness, such as allowing an unsupported decision despite missing required evidence, failing to enforce access restrictions, or losing a required challenge record.

A test is Blocked/Inconclusive when execution or evidence is insufficient to determine whether the control works. Missing evidence must not be treated as a pass.

## 7. Fallback and escalation

When required supporting evidence is unavailable, materially inconsistent or unreliable:

1. Follow the approved lending workflow to pause or route the case for review, as applicable.
2. Record the missing or conflicting evidence and its potential impact.
3. Assign an accountable owner to investigate or obtain corrected evidence.
4. Escalate through the approved route if the issue exceeds the reviewer’s authority or service-level threshold.
5. Resume the workflow only when the required evidence and authorisation conditions are satisfied.

Any fallback must be approved, documented and tested. This plan does not authorise an unverified manual workaround.

## 8. Closure requirements

F004-02 remains open until:

- Required reviewer evidence and access permissions are defined and approved.
- Relevant access and workflow controls are implemented.
- Tests are executed in an appropriate environment.
- Failures are remediated and successfully retested.
- Evidence is reviewed independently.
- The remediation tracker records the evidence location and authorised closure decision.

## 9. Data protection

Use synthetic cases and fictitious identifiers. Do not place real customer records, credentials or confidential production logs in the public repository.

SEA-02 — Initial Test Assessment

### SEA-03 — Conflicting or Newer Verified Evidence

- **Scenario:** The scoring system contains synthetic monthly income of ₹60,000, while a newer verified document records ₹45,000.
- **Expected result:** The discrepancy and source timestamps are visible; the reviewer can challenge the case; the system records the evidence and routes the challenge appropriately.
- **Additional validation:** Establish which income value was actually used by the model, assess the relevance of the discrepancy, and verify the documented resolution and any required rescoring.
- **Evidence:** Source records, timestamps, input snapshot, model version, score-generation record, challenge history, escalation outcome and relevant logs.
- **Status:** Not run.
- **Acceptance criteria:** The discrepancy can be traced, investigated and resolved through an accountable workflow. No unsupported assumption is made about its effect on the score.
- **Production implication:** F004-02 remains open until the relevant controls are implemented and successfully tested.

### SEA-03 — Unassigned Challenge and Escalation Delay

- **Scenario:** A reviewer challenges a credit score based on conflicting verified evidence. The workflow records the challenge, but no owner is assigned.
- **Expected result:** The challenge is assigned within the approved service level. If assignment fails or the deadline is breached, the system identifies the overdue case and routes it through the defined backup or escalation process.
- **Evidence:** Challenge creation timestamp, assignment timestamp, queue state, SLA configuration, alert or escalation record, designated owner and final disposition.
- **Failure criteria:** An assignment deadline is breached without the required alert, escalation or fallback, or the case proceeds contrary to the approved workflow.
- **Investigation:** Determine whether the cause was capacity, routing configuration, unavailable staff, a technical failure or another factor.
- **Status:** Not run.
- **Production implication:** F004-02 remains open until the assignment and escalation controls are implemented and tested.

### SEA-03 — Prioritisation of Unassigned Challenges

**Decision principle:** Prioritisation considers potential customer harm, decision urgency, uncertainty, SLA breaches and existing safeguards.

- Case C requires immediate triage because the assignment SLA has been breached and potential impact is unknown.
- Case A requires urgent assessment because potentially incorrect income data may affect a pending lending decision.
- Case B may receive lower immediate priority because the decision is paused and the discrepancy appears minor, subject to confirmation and a defined resolution deadline.
- Initial triage and owner assignment should occur promptly across cases; substantive investigation should be prioritised by assessed risk and urgency.
- The rationale, assigned owner, escalation actions, customer impact assessment and final disposition must be recorded.
- These are proposed governance actions, not evidence of an implemented or tested LendWise workflow.


### Fallback — Reviewer Unavailable or Escalation Queue Full

**Trigger:** A material credit-data challenge is unresolved, the primary decision-maker is unavailable or the escalation queue is full, and the lending decision deadline is approaching.

**Required behaviour:**

1. Keep the case in the appropriate controlled review state; do not permit approval contrary to the approved evidence and decision requirements.
2. Route the case to a pre-designated, authorised backup reviewer or escalation owner.
3. Record the original challenge time, decision deadline, assignment attempts, queue condition and escalation actions.
4. Alert the designated backup or responsible manager when the assignment or resolution SLA is at risk or breached.
5. Maintain an accountable owner until the case is resolved, and communicate any material delay according to approved procedures.
6. Resume the lending workflow only when the evidence issue and applicable approval requirements have been addressed.

**Evidence required:** Workflow configuration, backup-owner mapping, assignment and escalation timestamps, case-state history, audit logs, reviewer decision and rationale, and relevant customer communication records.

**Test status:** Proposed control; not run.

**Closure condition:** The fallback is implemented, tested under primary-reviewer unavailability and queue saturation, and independently reviewed.


### Fallback Validation — Backup Reviewer Lacks Supporting Evidence

**Scenario:** The primary decision-maker is unavailable. The designated backup reviewer is authorised to review the case but cannot access the underlying income evidence.

**Expected behaviour:**

1. The workflow prevents unsupported approval under the approved lending procedure.
2. The access problem is recorded and assigned to an accountable owner.
3. The case is routed through an approved evidence-retrieval or alternative escalation process.
4. The decision deadline and escalation status are monitored.
5. The case resumes only when the evidence and applicable authorisation requirements are satisfied.

**Evidence to retain:** Reviewer role and permissions, evidence-access failure, case state before and after the attempt, assignment and escalation timestamps, owner acknowledgement, retrieval outcome and final decision record.

**Acceptance criteria:** The backup reviewer cannot bypass the evidence requirement; the access issue has an accountable owner; and the workflow provides a tested route to resolution.

**Status:** Not run.

**Production implication:** F004-02 remains open until implementation and successful testing are evidenced.
