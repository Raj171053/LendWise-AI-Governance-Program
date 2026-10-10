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
