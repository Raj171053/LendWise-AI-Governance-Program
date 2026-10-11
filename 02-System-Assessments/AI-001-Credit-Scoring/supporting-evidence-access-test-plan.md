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
