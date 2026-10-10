# AI-001 Human Oversight Test Plan

## 1. Document Control

- **Company:** LendWise Financial Services Ltd.
- **System ID:** AI-001
- **System:** Credit Scoring System
- **Enterprise Risk:** High
- **EU AI Act Classification:** High-risk — Annex III, Section 5(b), for creditworthiness assessment of natural persons
- **Document Status:** Draft — Testing Not Yet Executed
- **Test Data:** Synthetic scenarios only
- **Approval Status:** NOT APPROVED — REMEDIATION REQUIRED

## 2. Objective

Assess whether the proposed human oversight controls allow authorised credit reviewers to critically assess AI-generated risk scores, identify questionable recommendations, request further evidence, override recommendations within their authority, escalate unresolved concerns, and maintain appropriate records.

This plan defines intended tests and acceptance criteria. It does not establish that any control has passed.

## 3. Preconditions

Before execution:

1. Confirm reviewer roles, decision authority, and escalation contacts.
2. Confirm the documented procedure for recording overrides and reviewer rationale.
3. Use a test environment and synthetic customer records.
4. Confirm reviewers can access the relevant evidence needed to challenge a score.
5. Define the expected response time for review and escalation.
6. Ensure test cases cannot trigger real lending decisions or customer-impacting actions.

## 4. Test Scenarios

### HOV-01: Reviewer challenges an unsupported score

- **Scenario:** The AI produces a high-risk score, but the reviewer identifies that a key supporting data field is missing or unreliable.
- **Test:** Ask the reviewer to examine the evidence and determine the appropriate next action.
- **Expected result:** The reviewer identifies the evidence gap, does not blindly accept the score, and follows the documented review or escalation procedure.
- **Evidence to capture:** Synthetic case ID, reviewer action, rationale, escalation record if applicable, and timestamp.

### HOV-02: Reviewer disagrees with the recommendation

- **Scenario:** The reviewer finds credible evidence that conflicts with the AI-generated risk assessment.
- **Test:** Ask the reviewer to follow the authorised challenge and override process.
- **Expected result:** The reviewer can challenge the recommendation and, where authorised, override it with a documented rationale. Otherwise, the case is escalated.
- **Evidence to capture:** Original recommendation, review rationale, action taken, authorisation, and audit-log entry.

### HOV-03: Case requires escalation

- **Scenario:** The reviewer encounters an unresolved data-quality concern or a case outside their decision authority.
- **Test:** Ask the reviewer to escalate the case through the documented route.
- **Expected result:** The case reaches the designated responsible person or team, remains subject to the appropriate safeguard, and is traceable until resolution.
- **Evidence to capture:** Escalation timestamp, recipient, case status, resolution, and elapsed time.

### HOV-04: Oversight evidence is unavailable

- **Scenario:** The reviewer cannot access the information required to understand or challenge the AI score.
- **Test:** Simulate the missing evidence or unavailable explanation.
- **Expected result:** The reviewer follows the defined fallback procedure and does not treat the unexplained score as sufficient evidence for a decision.
- **Evidence to capture:** Failure condition, reviewer response, fallback action, and incident record.

### HOV-05: Audit trail is incomplete

- **Scenario:** The system cannot record the reviewer’s rationale or the required action history.
- **Test:** Simulate the logging failure in the test environment.
- **Expected result:** The defined failure-handling procedure is followed, and the case is not treated as having complete oversight evidence. Any temporary recordkeeping or recovery method must be documented.
- **Evidence to capture:** Failure log, case status, recovery action, and evidence of record reconciliation.

## 5. Acceptance Criteria

A scenario passes only when evidence demonstrates that:

- The reviewer can access and critically assess the relevant evidence.
- The reviewer follows the documented authority and escalation boundaries.
- Challenges, overrides, and escalations are recorded and traceable.
- Required safeguards operate when information or logging is unavailable.
- No real customer-impacting action is triggered by the test.

A scenario fails if the expected control does not operate, required evidence is missing, or the reviewer cannot follow the defined procedure.

## 6. Results Register

Record one result per scenario after execution.

| Test ID | Status | Evidence Reference | Defect / Gap | Retest Status |
|---|---|---|---|---|
| HOV-01 | Not run | Pending | Pending | Not applicable |
| HOV-02 | Not run | Pending | Pending | Not applicable |
| HOV-03 | Not run | Pending | Pending | Not applicable |
| HOV-04 | Not run | Pending | Pending | Not applicable |
| HOV-05 | Not run | Pending | Pending | Not applicable |

Permitted statuses: Not run, Pass, Fail, Blocked.

## 7. Defect Management

Any failed or blocked test must be recorded, assigned to an accountable owner, assessed for customer and compliance impact, and tracked through remediation and retesting.

Do not mark a control effective solely because its documentation exists.

## 8. Exit Criteria

Testing is complete only when all scenarios have recorded outcomes, evidence has been reviewed, defects have been dispositioned, and required retests have been completed or explicitly remain open.

Passing these tests alone does not approve AI-001 for production.

**Current conclusion:** Test execution is pending. AI-001 remains NOT APPROVED — REMEDIATION REQUIRED.

## 9. Escalation Service Levels and Fallback

### Proposed Internal Targets — Pending Approval

- **Case ownership:** Every escalated case must have a named owner or designated team.
- **Acknowledgement:** The escalation must be acknowledged within 4 business hours.
- **Resolution or next-step decision:** The responsible team must provide a documented resolution or an approved next-step decision within 1 business day.
- **Missed deadline:** If either target is missed, the case must escalate to the designated senior owner, and the delay must be recorded.
- **Customer-impacting decisions:** The unexplained AI score must not be used as sufficient justification for a credit decision. The case must follow the approved manual-review or hold procedure.
- **Recordkeeping:** Record the case reference, reason for escalation, owner, timestamps, actions taken, outcome, and any deadline breach.
- **Fallback availability:** If the assigned reviewer, required evidence, or escalation channel is unavailable, follow the documented alternative route. Do not bypass required safeguards to meet the deadline.

### Approval and Validation

These targets remain proposed until approved by the accountable business owner. Test execution must verify that the routing, timestamps, fallback process, and deadline-breach escalation work as documented.

Resolution time targets must not pressure reviewers into making unsupported or inadequately reviewed lending decisions.
