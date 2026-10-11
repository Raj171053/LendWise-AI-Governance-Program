# Supporting Evidence Access — Test Results and Scenario Assessments

## 1. Document Information

| Field | Details |
|---|---|
| Organisation | LendWise Financial Services Ltd. |
| AI system | AI-001 — Credit Scoring System |
| Control area | F004-02 — Access to Supporting Evidence |
| Document type | Training Scenario Assessment and Test-Result Record |
| Scenarios covered | SEA-01 to SEA-07 |
| Business owner | Head of Credit Risk — proposed, subject to confirmation |
| Governance reviewer | AI Governance / Model Risk — subject to confirmation |
| Overall status | Training scenarios assessed; operational effectiveness not verified |
| Related documents | `supporting-evidence-access-test-plan.md`; `f-004-control-evidence-and-closure-matrix.md` |

## 2. Purpose

This document records seven scenario-based assessments of supporting-evidence access for the LendWise AI-001 Credit Scoring System.

The objective is to establish whether authorised lending reviewers can access evidence that is relevant, reliable, sufficiently complete, and traceable to the AI-assisted credit assessment.

The scenarios examine evidence availability, source verification, conflicting information, access restrictions, backup reviewers, SLA breaches, escalation ownership, and controlled handling when evidence retrieval is unavailable.

## 3. Important Status and Evidence Limitations

The results below record the decisions made during the training exercises. They are not proof that the corresponding controls have been implemented or successfully tested in a live or authorised operational environment.

- **Training assessment passed:** The response demonstrates appropriate governance reasoning for the scenario.
- **Blocked / Inconclusive:** The scenario contains an unresolved control or evidence question that must be investigated.
- **Operational test status:** Not run or not evidenced unless an authorised execution record and supporting evidence are available.
- **Independent verification:** Pending unless an independent reviewer has examined the underlying evidence and documented a conclusion.

Screenshots, log records, API responses, timestamps, configuration evidence, case records, and approval records must be linked when they actually exist. They must not be fabricated to complete this document.

## 4. SEA-01 — Complete Evidence Access

### Scenario

A consumer loan application uses a monthly income value of ₹60,000. The reviewer can access the AI-generated risk score, model version, income value, source document, verification status, timestamp, and evidence reference. However, the reviewer has not confirmed that the source document supports the income value.

### Expected result

The reviewer must verify the source evidence, its authenticity, verification status, relevance, and provenance before relying on it for a lending decision. The application must not be approved solely because the evidence fields are accessible or because the AI score is available.

### Training assessment

**Assessment: Pass.**

The learner selected to pause the decision, verify the source, check timestamps and provenance, and record a challenge if evidence is insufficient.

The learner correctly identified the need for a confirmed income report. The applicable income-document requirement must be grounded in the approved lending policy and relevant product requirements.

### Evidence required

- Source document and verification status.
- Document source, reporting period, timestamp, and evidence reference.
- Income value actually supplied to the model.
- Model version and relevant assessment output.
- Reviewer rationale and challenge record, if applicable.
- Case status and subsequent authorised decision.

### Acceptance criteria

The reviewer can access and verify relevant supporting evidence, trace the value used by the model to its source, and follow the approved workflow when evidence is insufficient.

### Operational status

Not run / not evidenced.

---

## 5. SEA-02 — Missing Income Data Due to Integration Failure

### Scenario

An integration failure prevents the required income field from reaching the review interface. The system displays an “Income data unavailable” warning and blocks approval in the user interface. No corresponding event has been found in the audit logs checked so far. API-level and alternate-workflow behaviour have not been verified.

### Expected result

The application must remain in a controlled state until required evidence is available or an approved alternative process has been followed. The system must prevent unauthorised approval through relevant access routes and record required security, audit, and escalation events.

### Training assessment

**Assessment: Blocked / Inconclusive.**

The learner correctly identified that the interface warning and disabled approval button do not establish that the backend and alternate routes are safe.

### Required investigation

1. Confirm the persisted case status and whether any decision or downstream workflow was triggered.
2. Test relevant API and alternate access routes in an authorised test environment.
3. Inspect application, backend, audit, and security logs.
4. Determine whether a required audit event is missing.
5. Verify escalation ownership, notification delivery, acknowledgement, and the controlled fallback.
6. Record defects and retest after remediation.

### Evidence required

- Test ID, synthetic case ID, environment, and timestamp.
- Screenshot of the warning and disabled approval control.
- API/backend response and persisted case status.
- Relevant application, audit, security, and escalation logs.
- Expected versus actual result.
- Defect reference, remediation owner, and retest evidence.

### Acceptance criteria

Required income evidence cannot be bypassed through alternate routes; the case remains controlled; required events are logged; and the integration failure is assigned and handled through an approved process.

### Operational status

Not run / not evidenced. The missing audit event requires investigation.

---

## 6. SEA-03 — Conflicting Income Evidence

### Scenario

The credit-scoring system contains a monthly income value of ₹60,000. A newer verified document contains a different value of ₹45,000. The lending decision is pending, and the system has not established which value should be used.

### Expected result

The reviewer must pause the decision, investigate the discrepancy, verify the source records and reporting periods, and determine which evidence is authoritative under the approved lending policy.

The newer document must not automatically be treated as more authoritative solely because it is newer.

### Training assessment

**Assessment: Pass.**

The learner correctly selected to pause and investigate, cross-check the information with the customer where appropriate, verify document authenticity, review the model input, assess potential score impact, and retain timestamped records.

### Required investigation

1. Verify both sources and their verification status.
2. Compare timestamps, reporting periods, and evidence provenance.
3. Confirm the income value actually supplied to the model.
4. Determine whether the discrepancy affects the score or assessment.
5. Record the challenge and the authorised resolution.
6. Reassess the model input and score where appropriate.
7. Resume the lending workflow only after the discrepancy is resolved through the approved process.

### Evidence required

- Both source records and their evidence references.
- Verification status, timestamps, and reporting periods.
- Model input, model version, and relevant assessment output.
- Challenge record and any customer clarification.
- Reviewer rationale and resolution.
- Audit history and final workflow state.

### Acceptance criteria

Conflicting evidence is detected, investigated, and resolved by an authorised reviewer. The decision is traceable to the evidence relied upon, and the case cannot proceed on an unsupported value.

### Operational status

Not run / not evidenced.

---

## 7. SEA-04 — Reviewer Cannot Access Supporting Evidence

### Scenario

An authorised credit reviewer can see the income value and risk score but receives an “Access denied” message when opening the underlying income document. The cause may be a permissions misconfiguration, a temporary service failure, or a legitimate restriction.

### Expected result

The reviewer must not bypass access controls or approve using unverified evidence. The access issue must be investigated and escalated early enough to protect the decision deadline.

The application remains pending while required evidence is unavailable. An authorised backup reviewer or approved alternative process may be used where it meets the evidence and control requirements.

### Training assessment

**Assessment: Pass.**

The learner correctly considered SLA timing, reviewer identity, authority, access controls, security logs, timestamps, escalation, and customer communication.

### Required investigation

1. Confirm the reviewer’s identity, role, and delegated authority.
2. Review access-control configuration and authorisation logs.
3. Determine whether the restriction is legitimate or a technical defect.
4. Record the access request, response, and remaining time before the SLA deadline.
5. Escalate early and arrange an authorised alternative reviewer where appropriate.
6. Confirm that access is restored or that an approved alternative process is available.
7. Document the resolution and the resulting case state.

### Evidence required

- Error screenshot and case ID.
- Reviewer identity, role, and access request.
- Permission configuration and relevant security logs.
- Request, response, and escalation timestamps.
- SLA status, assigned owner, and acknowledgement.
- Case status and final review outcome.
- Defect and retest records, where applicable.

### Acceptance criteria

Only authorised personnel can access supporting evidence, access failures are investigated and escalated, and the lending decision remains controlled until sufficient evidence is available.

### Operational status

Not run / not evidenced.

---

## 8. SEA-05 — Backup Reviewer Cannot Access the Documents

### Scenario

The primary reviewer cannot access the income document. The case is assigned to an approved backup reviewer, who accepts the assignment but encounters the same access-denied error. The review deadline is approaching.

### Expected result

The case must remain pending. The access failure must be investigated, and ownership must move to an authorised person or management route capable of resolving the issue.

A technical team may restore access, but it does not automatically receive lending decision authority. An authorised reviewer must still assess the evidence and record the decision.

### Training assessment

**Assessment: Pass.**

The learner correctly proposed immediate escalation, inclusion of the remaining SLA time, examination of access-control and authorisation logs, and transfer to an authorised senior reviewer or the responsible technical team.

The learner also identified the need to confirm whether the document became accessible and whether the review was completed after escalation.

### Required investigation

1. Confirm the backup reviewer’s assignment, authority, and acknowledgement.
2. Determine whether the issue affects the reviewer, the document, the permissions configuration, or the document service.
3. Assign the technical issue to an appropriate support owner.
4. Identify an authorised alternative reviewer or approved management escalation route.
5. Monitor the overdue case and preserve its controlled status.
6. Record resolution, access restoration, and the final review outcome.

### Evidence required

- Primary and backup reviewer access failures.
- Case ID, timestamps, and remaining SLA time.
- Reviewer authority and access-control records.
- Escalation delivery, acknowledgement, and ownership-transfer history.
- Technical support ticket and resolution evidence, where applicable.
- Confirmation that the evidence became accessible.
- Final review outcome and audit trail.

### Acceptance criteria

The escalation results in an accountable owner and a viable route to evidence access. The case remains controlled, and only an appropriately authorised reviewer completes the lending assessment.

### Operational status

Not run / not evidenced.

---

## 9. SEA-06 — Evidence Retrieval Failure After the SLA Deadline

### Scenario

The primary and backup reviewers cannot retrieve the required income document. The escalation owner has not responded, and the applicable review SLA has expired. The AI-generated risk score remains visible, but the income evidence is unavailable.

### Expected result

The application must remain pending under the approved overdue-case and escalation process. A missed SLA does not make missing evidence acceptable and does not grant additional decision-making authority.

Management must assign an authorised owner, initiate the approved SLA-breach procedure, and arrange an appropriate route to evidence retrieval and review.

### Training assessment

**Assessment: Pass.**

The learner correctly chose to keep the application pending, escalate the overdue case to management, and communicate appropriately with the customer.

Customer communication should accurately describe the delay and next steps without promising a resolution date that has not been confirmed.

### Required investigation

1. Record the SLA breach and its cause, where known.
2. Escalate through the approved overdue-case route.
3. Assign an authorised owner and record acceptance of responsibility.
4. Arrange evidence retrieval or an approved alternative review process.
5. Preserve the case in a controlled state.
6. Communicate with the customer where appropriate.
7. Record the final resolution and any corrective action needed to prevent recurrence.

### Evidence required

- SLA definition, clock start, deadline, and breach timestamp.
- Failed access attempts and relevant logs.
- Escalation history and management acknowledgement.
- Assigned owner and ownership-acceptance record.
- Case status and evidence-retrieval status.
- Customer communication, where appropriate.
- Final review outcome and audit history.
- Root-cause analysis and remediation records, where required.

### Acceptance criteria

The overdue case is actively managed, ownership is explicit, the missing evidence is addressed through an approved process, and the final decision is traceable. The SLA breach is not silently reset or concealed.

### Operational status

Not run / not evidenced.

---

## 10. SEA-07 — Evidence Retrieval Unavailable and Escalation Owner Unresponsive

### Scenario

The primary and backup reviewers cannot retrieve the income document. The review SLA has expired, and the assigned escalation owner has not acknowledged the escalation. The AI-generated risk score is visible, but the underlying income evidence remains unavailable. The availability of an authorised alternative reviewer or approved retrieval process has not been confirmed.

### Expected result

The application remains pending in a controlled state. The organisation follows the approved deputy or management escalation route, assigns an authorised alternative reviewer or responsible owner, and continues to investigate the evidence-access failure.

A notification to an unavailable escalation owner is not sufficient to demonstrate that the issue has been addressed. Ownership transfer, acknowledgement, and the next action must be recorded.

### Training assessment

**Assessment: Pass.**

The learner correctly selected to keep the application pending and have management arrange an authorised alternative reviewer. The learner also identified the need to document access failures, timestamps, SLA breach records, escalation delivery and acknowledgement, ownership transfer, case status, and final review outcome.

### Required investigation

1. Record the failed access attempts and the overdue status.
2. Trigger the approved deputy or management escalation route.
3. Confirm delivery and acknowledgement of the escalation.
4. Assign an authorised alternative reviewer or accountable owner.
5. Confirm acceptance of ownership and the next action.
6. Keep the case pending until the required evidence is available and reviewed.
7. Document customer communication where appropriate.
8. Record the final resolution and any remedial action.

### Evidence required

- Primary and backup reviewer access failures.
- Case ID, timestamps, and SLA-breach record.
- Escalation delivery, acknowledgement, and ownership-transfer records.
- Identity, role, and authority of the replacement reviewer or owner.
- Evidence-retrieval status and case state.
- Relevant application, security, audit, and escalation logs.
- Customer communication, where appropriate.
- Final authorised review outcome and supporting evidence.

### Acceptance criteria

An unavailable escalation owner does not leave the case unmanaged. The approved alternate route establishes accountable ownership, preserves the controlled case state, and enables an authorised review once sufficient evidence becomes available.

### Training conclusion

The scenario response demonstrates appropriate governance reasoning. Actual effectiveness remains unverified until the relevant operational evidence and test records have been examined.

### Operational status

Not run / not evidenced.

---

## 11. Consolidated Training Assessment

| Test ID | Scenario | Training assessment | Key unresolved operational evidence |
|---|---|---|---|
| SEA-01 | Complete evidence access | Pass | Source verification and traceability evidence |
| SEA-02 | Missing income data | Blocked / Inconclusive | Backend and alternate-route enforcement; missing audit event |
| SEA-03 | Conflicting income evidence | Pass | Discrepancy resolution and model-input traceability |
| SEA-04 | Reviewer access denied | Pass | Access-control, escalation, and resolution records |
| SEA-05 | Backup reviewer cannot access evidence | Pass | Accepted ownership and restored evidence access |
| SEA-06 | SLA deadline expired | Pass | SLA-breach handling and final resolution evidence |
| SEA-07 | Escalation owner unresponsive | Pass | Verified ownership transfer and evidence-access resolution |

**Interpretation:** “Pass” in this table refers to the training response, not an operational control pass. SEA-02 remains Blocked / Inconclusive because the scenario explicitly leaves material control behaviour unresolved.

## 12. Common Control Requirements

Across all seven scenarios, LendWise should demonstrate the following:

1. Required evidence is accessible to appropriately authorised reviewers.
2. Evidence is verified, relevant, sufficiently complete, and traceable to its source.
3. Conflicting or missing evidence triggers a controlled review or challenge.
4. Missing evidence cannot be bypassed through alternate access routes.
5. The case remains in a controlled state while required evidence is unavailable.
6. Access restrictions are investigated without weakening security controls.
7. Escalation has an accountable owner, acknowledgement, and a documented next action.
8. SLA breaches are recorded and handled through the approved process.
9. Relevant application, security, audit, and decision-history records are preserved.
10. An authorised reviewer completes the review before the lending workflow resumes where required by policy.
11. Customer communication is appropriate, accurate, and documented where applicable.
12. Defects are assigned, remediated, and retested before the relevant control is declared effective.

## 13. Defect and Retest Record

For each operational test that identifies a defect, record:

| Field | Required information |
|---|---|
| Test ID | SEA-01 to SEA-07 |
| Defect ID | Actual defect or ticket reference |
| Description | Observed control failure or missing evidence |
| Severity | Approved organisational severity rating |
| Root cause | Confirmed cause, or investigation status |
| Remediation owner | Accountable individual or team |
| Corrective action | Approved remediation |
| Retest result | Actual result from authorised retesting |
| Evidence reference | Link or identifier for the supporting records |
| Independent review | Reviewer, date, findings, and exceptions |
| Closure decision | Open, remediated pending retest, or formally closed |

Do not invent defect identifiers, evidence links, test timestamps, or approval records.

## 14. Overall F004-02 Conclusion

**Current conclusion: Training scenarios assessed; operational control effectiveness not verified.**

The scenarios establish the expected governance response to missing, conflicting, inaccessible, or delayed supporting evidence. They also identify the importance of role-based access, case-state protection, escalation ownership, SLA monitoring, and auditability.

The next steps are to:

1. Execute the relevant tests in an authorised environment where required.
2. Attach the actual test records and supporting evidence.
3. Investigate unresolved findings, including SEA-02's missing audit event.
4. Remediate and retest identified defects.
5. Obtain the required independent review.
6. Update the F-004 control evidence and closure matrix.

**F004-02 closure status:** Open — operational evidence and independent verification pending.

**AI-001 production status:** Not approved pending completion of required remediation and formal governance approval.

## 15. Related Documents

- `supporting-evidence-access-test-plan.md`
- `f-004-control-evidence-and-closure-matrix.md`
- `human-oversight-matrix.md`
- `human-oversight-test-plan.md`
- `audit-logging-and-record-integrity-test-plan.md`
- `escalation-ownership-and-sla-matrix.md`

