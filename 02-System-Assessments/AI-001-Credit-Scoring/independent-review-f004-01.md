# F-004-01 — Independent Review of Reviewer Authority Controls

## 1. Review purpose

Assess the design and reported test outcomes of the reviewer authority controls for LendWise's AI-001 Credit Scoring System, including authorisation boundaries, override controls, escalation routing, audit logging, and API-level enforcement.

## 2. Independence

**Review arrangement:** An independent team with no reported conflict of interest with the project conducted the review.

**Evidence required:** Record the review team's name, review date, scope, reviewer identities or roles, conflict-of-interest declaration, and review sign-off.

## 3. Test coverage

The review covered the reported results for:

- RAT-01 — Reviewer permissions and authorised actions
- RAT-02 — Unauthorised override prevention
- RAT-03 — Challenge recording and approved review workflow
- RAT-04 — Exceptions outside delegated authority
- RAT-05 — Unauthorised audit-record modification
- RAT-06 — API-level authorisation and alternate access routes

## 4. Reported observations

The project reported that unauthorised actions were blocked or rejected, permitted actions followed delegated authority, relevant attempts were logged, and exceptions were routed to the appropriate authority.

RAT-03 remains **Blocked / Inconclusive** until the approved assignment and escalation workflow is verified.

These observations are provisional until the independent team’s detailed findings and supporting evidence references are recorded and verified.

## 5. Governance and approval pathway

**CTO:** All six test results were presented to the CTO for approval. The formal decision, decision date, conditions, and approval evidence must be recorded.

**Governance Team:** The results were passed to the Governance Team. Its review outcome, outstanding conditions, and formal disposition must be documented.

Presentation, submission, or referral must not be recorded as approval unless the corresponding decision is evidenced.

## 6. Outstanding actions

1. Attach or reference the independent review report and its findings.
2. Verify the supporting evidence for RAT-01 through RAT-06.
3. Resolve the RAT-03 workflow-verification gap.
4. Record the CTO's formal decision and any conditions.
5. Record the Governance Team's formal disposition.
6. Update the F-004 closure matrix with evidence references, accountable owners, and closure decisions.

## 7. Current governance conclusion

**F-004-01: Open — formal closure not yet evidenced.**

The reported independent review and escalation through the governance pathway are useful process evidence. However, closure requires verified test evidence, resolution of outstanding gaps, documented approval decisions, and confirmation that the controls are implemented and operating effectively.

**AI-001 production status:** Not approved pending remediation and formal governance approval.
