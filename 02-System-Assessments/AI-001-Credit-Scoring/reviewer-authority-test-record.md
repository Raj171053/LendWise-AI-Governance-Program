# F004-01 — Reviewer Authority Test Record

## 1. Purpose

Verify that reviewer permissions, override authority and escalation routes for AI-001 Credit Scoring match the approved Human Oversight Matrix and prevent unauthorised changes to credit-scoring outcomes.

## 2. Test status and limitations

- **Current status:** Not run
- **Environment:** To be confirmed
- **Test data:** Synthetic cases only
- **Execution owner:** To be assigned
- **Independent reviewer:** AI Governance / Model Risk authority
- **Production decision:** NOT APPROVED — REMEDIATION REQUIRED

This document defines proposed tests. It does not prove that system controls have been implemented or tested.

## 3. Test cases

| Test ID | Scenario | Expected result | Evidence to capture | Status |
|---|---|---|---|---|
| RAT-01 | Authorised reviewer opens an assigned case | Reviewer can access only the information and actions permitted by their role | Role configuration, test case reference, access log | Not run |
| RAT-02 | Reviewer without override authority attempts to override a credit score | System blocks the action or routes the case through an approved authorisation workflow | Test role, attempted action, system response, timestamp and logs | Not run |
| RAT-03 | Authorised reviewer challenges a score using verified conflicting evidence | Challenge is recorded with rationale and supporting evidence; case follows the approved review workflow | Case record, evidence reference, reviewer rationale and decision history | Not run |
| RAT-04 | Reviewer attempts to approve an exception outside their delegated authority | Approval is prevented and the case is routed to the authorised decision-maker | Permission configuration, escalation record, recipient and final outcome | Not run |
| RAT-05 | Reviewer attempts to modify or bypass the audit record of an override | Unauthorised modification is prevented or detected; the audit trail preserves the relevant event history | Access-control configuration, audit logs, integrity-check results | Not run |

## 4. Results record

For each test, record:

- Test ID and execution date/time
- Tester identity and assigned role
- Environment and synthetic case reference
- Preconditions and steps performed
- Expected result and actual result
- Pass / Fail / Blocked
- Evidence location
- Defect or incident reference, if applicable
- Remediation owner and retest result, if applicable
- Independent reviewer and review decision

## 5. Pass and closure criteria

A test passes only when the observed behaviour meets the documented expected result and supporting evidence is retained.

A failed or blocked test must be investigated. Missing evidence must not be treated as a pass.

F004-01 remains open until the approved authority rules are implemented, relevant tests pass, defects are addressed, evidence is reviewed independently, and the closure decision is recorded in the remediation tracker.

## 6. Evidence integrity

Use synthetic identifiers in training artifacts. Do not include real customer records, credentials, personal data or confidential production logs in the public repository.

Link only to evidence that actually exists. Clearly label tabletop exercises and mock results; never present them as tests of a live or configured system.
