# F-004 Control Evidence and Closure Matrix

**Company:** LendWise Financial Services Ltd.  
**AI System:** AI-001 — Credit Scoring  
**Finding ID:** F-004  
**Finding Title:** Human Oversight Requirements Incomplete  
**Enterprise Risk Level:** High  
**EU AI Act Classification:** High-risk AI system — Annex III, Section 5(b), for creditworthiness assessment of natural persons  
**Finding Priority:** High  
**Finding Owner:** Head of Credit Risk  
**Governance Reviewer:** AI Governance / Model Risk  
**Overall Finding Status:** Open — Remediation Required  
**Closure Decision:** Open  
**Production Approval:** Not Approved — Remediation Required  
**Document Status:** Control evidence and closure tracking matrix

---

## 1. Purpose

This matrix consolidates the four F-004 human-oversight workstreams into one evidence-based tracking document.

Its purpose is to establish whether human oversight for AI-001 is adequately designed, implemented, tested and independently reviewed before the finding can be closed.

The matrix distinguishes between:

- **Design evidence:** Policies, matrices, procedures and test plans describing the intended control.
- **Implementation evidence:** Approved configurations, access permissions, workflow settings, operational records and other evidence showing that the control exists in the intended environment.
- **Test evidence:** Results from tests actually executed in an appropriate authorised environment.
- **Closure evidence:** Evidence reviewed by an authorised independent reviewer, supporting a documented closure decision.

A document or proposed test does not, by itself, demonstrate that a control is operationally effective.

All scenarios in this portfolio are synthetic training scenarios. Do not represent them as real customer cases or completed production tests.

## 2. Finding Description

Human oversight requirements for AI-001 require further definition and evidence.

The governance programme must establish that authorised reviewers can meaningfully assess and challenge AI-generated credit-risk scores, access the supporting evidence needed to make informed decisions, escalate unresolved issues to an accountable person within approved time limits, and rely on a complete and trustworthy audit trail.

The finding cannot be closed solely because procedures have been documented. Required controls must be implemented, tested and supported by evidence.

## 3. Control Evidence and Closure Matrix

| Workstream | Control ID | Control Objective | Accountable Owner | Required Implementation Evidence | Related Tests | Current Evidence Status | Closure Criteria |
|---|---|---|---|---|---|---|---|
| Reviewer authority and decision boundaries | F004-01 | Ensure only authorised reviewers can make or override decisions within defined authority limits, with required rationale and traceable outcomes. | Head of Credit Risk | Approved human-oversight matrix; role/permission configuration; reviewer authority rules; override workflow; training evidence; application and API access-control evidence where applicable. | RAT-01 to RAT-06, as defined in the reviewer-authority test record. | Design and test scenarios documented. RAT-01 to RAT-06 results reported and presented to the CTO. CTO reviewed the results and referred them to the AI Governance Team for final approval. Independent review reported; supporting evidence verification and final governance approval remain pending. RAT-03 workflow verification remains outstanding.. | Required authority boundaries are approved, implemented and tested. Unauthorised actions are prevented, permitted overrides are traceable, and defects are resolved or formally risk-accepted by an authorised decision-maker. |
| Supporting-evidence access | F004-02 | Ensure reviewers can retrieve complete, relevant, current and reliable evidence needed to challenge an AI-generated credit score. | Head of Credit Risk | Approved evidence-access procedure; role-based access configuration; source/provenance and timestamp visibility; missing/stale/conflicting-data indicators; challenge workflow; fallback and escalation controls. | SEA-01 to SEA-07, as defined in the supporting-evidence access test plan. | SEA-01 to SEA-07 training scenarios assessed. The learner's responses demonstrate appropriate governance reasoning for evidence verification, missing or conflicting data, role-based access, backup reviewers, SLA breaches, and escalation ownership. Operational test execution and control effectiveness have not been verified. SEA-02 remains Blocked/Inconclusive pending investigation of backend enforcement, alternate access routes, and the missing audit event. Evidence references, implementation records, operational test results, and independent review remain pending. | Required evidence is accessible to authorised reviewers. Missing, stale or conflicting evidence is detected and handled under an approved controlled process. Test evidence demonstrates the intended behaviour. |
| Escalation ownership and SLAs | F004-03 | Ensure unresolved challenges are assigned, acknowledged, escalated and owned within approved time limits, with a controlled case state when normal handling is unavailable. | Head of Credit Risk | Approved escalation and SLA matrix; named primary and backup roles; approved SLA and clock-start definitions; queue monitoring; escalation notification configuration; ownership acceptance and reassignment records; relevant communication procedures. | EOM-01 to EOM-03, as defined in the escalation ownership and SLA test plan. | The EOM-01 to EOM-03 training exercises have been completed in the prior discussion. Do not repeat these exercises. The proposed escalation matrix and scenarios document the intended control design, including SLA breaches, queue saturation, backup escalation and explicit ownership acceptance. Approval of SLA targets and clock-start rules, implementation of primary/backup ownership and escalation workflows, operational test execution and supporting evidence have not been verified. All operational tests remain Not run unless separately executed and evidenced. | SLA targets are approved by the appropriate business owner. Breaches trigger the required escalation, an eligible owner accepts responsibility, and the case remains controlled until the required review is complete. |
| Audit logging and record integrity | F004-04 | Ensure material credit-scoring and human-oversight events are attributable, time-ordered, retrievable and protected against unauthorised alteration or deletion. Ensure required security events and logging failures are detected and investigated. | Head of Credit Risk, with relevant Technology / Security control owners | Approved logging requirements; event schema; access-control and integrity configuration; timestamp and retention standards; monitoring and alert configuration; outage/recovery procedure; event reconciliation and investigation records. | ALR-01 to ALR-07, as defined in the audit-logging and record-integrity test plan. | The audit-logging test plan is documented, and ALR-01 to ALR-07 scenarios have already been discussed. Consolidation of these prior scenario assessments is pending; do not repeat the exercises. The discussions identified issues requiring investigation, including missing lifecycle events, unverified security-event logging and API enforcement, delayed central log ingestion, inconsistent timestamps, incomplete override records and uncertain outage recovery. These are scenario-based findings, not confirmed production defects. Operational implementation and effectiveness have not been verified. All seven operational tests remain Not run unless separately executed and evidenced. | Required events are logged and retrievable, unauthorised changes are prevented, required security events are recorded, timing and monitoring requirements are met, and outage recovery is evidenced. Defects are remediated and retested. |

**Important:** The owner roles in this matrix are proposed accountability assignments for the training case. Confirm the actual accountable role for each technical control and any separate Technology, Security or Model Risk responsibilities before treating this as an approved operating model.

## 4. Evidence Classification Register

Use the following classifications for each artifact or evidence item.

| Evidence Category | Meaning | Example |
|---|---|---|
| Design | Describes the intended control. | Human-oversight matrix, escalation procedure, audit-logging test plan. |
| Implementation | Demonstrates that the control is configured or operating in the intended environment. | Approved role configuration, workflow settings, monitoring rules, access-control configuration. |
| Operational Test | Demonstrates the result of a test actually executed in an appropriate environment. | Dated test record with expected and actual results, logs and supporting evidence. |
| Remediation | Demonstrates that a defect has been corrected. | Change record, updated configuration, corrective-action record and successful retest. |
| Closure | Demonstrates an authorised reviewer has assessed the evidence and made a documented closure decision. | Independent review record and approved closure decision. |

Do not classify a proposed test plan or tabletop answer as operational test evidence.

## 5. Test Status Register

The training scenarios below have been discussed in the project history. Their completion does not constitute operational test execution. Preserve the operational status as `Not run` until a test has actually been executed in an authorised environment and the required evidence retained.

| Workstream | Test IDs | Training / documentation status | Current operational status | Remaining action |
|---|---|---|---|---|
| F004-01 — Reviewer authority | RAT-01 to RAT-06 | Scenarios discussed; results reportedly presented to CTO and referred for final AI Governance approval | Not run unless separately executed and evidenced | Verify supporting evidence, complete RAT-03 workflow verification, and obtain documented governance approval |
| F004-02 — Supporting-evidence access | SEA-01 to SEA-07 | Scenarios assessed | Not run unless separately executed and evidenced | Investigate SEA-02, finalise the consolidated results record, and verify implementation and operational evidence |
| F004-03 — Escalation ownership and SLAs | EOM-01 to EOM-03 | All three training exercises completed in the prior discussion | Not run unless separately executed and evidenced | Obtain approval for SLA targets and ownership arrangements, verify implementation, and execute tests when authorised; do not repeat training exercises |
| F004-04 — Audit logging and record integrity | ALR-01 to ALR-07 | Scenarios discussed; consolidated assessment record remains to be completed | Not run | Consolidate prior assessments, investigate identified scenario gaps, verify implementation, and execute tests when authorised |

**Status rules**

- `Pass` requires actual execution, evidence meeting the acceptance criteria and appropriate review.
- `Fail` requires evidence that an executed test confirmed a control failure.
- `Blocked / Inconclusive` applies when evidence is insufficient or investigation is incomplete.
- `Not run` means no operational execution has been evidenced.
- A tabletop assessment may identify a potential control gap, but it must not be represented as a confirmed operational defect without supporting evidence.

Update this register only when the corresponding test record supports the change.
## 6. Defect and Remediation Tracking

For every failed or inconclusive test, maintain a linked defect or remediation record containing:

- Defect ID and related finding/control/test IDs.
- Expected versus actual behaviour.
- Severity and potential impact on customers, lending decisions, traceability and governance.
- Affected systems, event types, cases and time period.
- Confirmed root cause, or `Under investigation`.
- Accountable remediation owner and target date.
- Corrective action and implementation evidence.
- Retest date, evidence and result.
- Independent reviewer and closure decision.

Where evidence is missing, preserve the gap transparently. Do not backdate records, fabricate evidence or silently recreate historical events.

## 7. Dependencies and Open Questions

The following dependencies remain open unless and until supporting evidence demonstrates otherwise.

1. **Reviewer authority — F004-01:** Verify reviewer permissions and decision boundaries, complete the outstanding RAT-03 workflow verification, confirm the integrity of the supporting evidence, and obtain the final AI Governance approval decision.
2. **Supporting evidence — F004-02:** Investigate SEA-02, including alternate application/API access routes and the missing audit event. Confirm approved evidence requirements, source reliability and freshness rules, conflict handling, controlled fallback and escalation.
3. **Escalation and SLAs — F004-03:** Obtain business-owner approval for acknowledgement, assignment and escalation targets; define business calendars and clock-start rules; confirm primary and backup ownership, queue-saturation handling, notification delivery, acknowledgement and explicit ownership acceptance.
4. **Audit logging — F004-04:** Consolidate the previously discussed ALR assessments. Verify required event types, timestamp and ingestion conventions, security-event logging, access controls, record integrity, retention, monitoring, outage handling and recovery.
5. **Implementation and operational evidence:** Identify the relevant systems and authorised test environments. Retain approved configurations, workflow records, dated test evidence, defects, remediation and retest records.
6. **Independent review:** Confirm the authorised independent reviewer and retain a documented review of the implementation and operational evidence before closure.
7. **Residual risk:** Assess unresolved limitations and obtain formal risk acceptance from an authorised decision-maker where applicable.

These items are open dependencies, not assertions that all underlying controls have failed. Record a confirmed defect only when supported by evidence; otherwise retain the item as pending verification or under investigation.

## 8. Closure Acceptance Criteria

F-004 may be considered for closure only when all applicable criteria below have been satisfied:

- [ ] The control design and relevant procedures are approved by the appropriate owners.
- [ ] Reviewer authority and decision boundaries are implemented and evidenced.
- [ ] Authorised reviewers can access the evidence required for meaningful review and challenge.
- [ ] Escalation ownership, backup arrangements and SLA targets are approved and implemented.
- [ ] Required audit events, security events and record-integrity protections are implemented.
- [ ] Applicable tests have been executed in an appropriate authorised environment.
- [ ] Expected and actual results, logs and other supporting evidence are retained.
- [ ] Failed tests have been remediated and successfully retested, or remaining risk has been formally accepted by an authorised decision-maker.
- [ ] Missing evidence and unresolved limitations have been investigated and documented.
- [ ] An independent reviewer has assessed the evidence and recorded the closure decision.
- [ ] The remediation tracker has been updated with accurate statuses and links to committed evidence.

Checking a box indicates completion only when the corresponding evidence supports it. Do not check items based solely on planned actions or draft documentation.

## 9. Current Governance Decision

**Finding F-004:** Open — Remediation Required  
**Closure Decision:** Open  
**AI-001 Production Approval:** Not Approved — Remediation Required

**Rationale:** The project has documented proposed human-oversight controls and discussed the associated synthetic training scenarios. However, the available records do not establish that all required controls have been implemented and operationally tested. Supporting evidence verification, outstanding workflow investigation, approval of escalation arrangements, audit-logging verification, operational test evidence and the required independent closure review remain outstanding.

The completion of training scenarios must not be represented as successful operational testing. Potential gaps identified during scenario discussions must be investigated before they are recorded as confirmed operational defects. F-004 must remain open until the applicable closure criteria are evidenced and an authorised closure decision is recorded.

## 10. Closure Sign-Off Record

Complete this section only after the required evidence has been reviewed.

| Field | Value |
|---|---|
| Finding ID | F-004 |
| Closure recommendation | Remediation required; closure not recommended at this stage |
| Control owner | Head of Credit Risk, subject to confirmation |
| Independent reviewer | AI Governance / Model Risk, subject to confirmation |
| Evidence review date | Pending |
| Outstanding defects and gaps | Confirmed defects and unresolved evidence gaps to be recorded after investigation and operational testing |
| Residual risk decision | Pending authorised assessment |
| Final closure decision | Open — Remediation Required |
| Closure rationale | Awaiting verification of implementation, operational test results, remediation and retest evidence where applicable, independent review, and authorised closure approval |

No sign-off or approval should be inferred from the completion of training exercises or preparation of this matrix.

---

## 11. Document Maintenance

Update this matrix whenever a control is implemented, a test is executed, a defect is raised or remediated, evidence is added, or a formal closure decision is made.

Ensure every referenced artifact exists at the stated path in the repository before relying on it as closure evidence. Keep the matrix consistent with the remediation tracker, test records and the AI-001 risk-and-fairness assessment.
