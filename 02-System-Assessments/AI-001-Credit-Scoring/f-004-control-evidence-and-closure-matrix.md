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
| Escalation ownership and SLAs | F004-03 | Ensure unresolved challenges are assigned, acknowledged, escalated and owned within approved time limits, with a controlled case state when normal handling is unavailable. | Head of Credit Risk | Approved escalation and SLA matrix; named primary and backup roles; approved SLA and clock-start definitions; queue monitoring; escalation notification configuration; ownership acceptance and reassignment records; relevant communication procedures. | EOM-01 to EOM-03, as defined in the escalation ownership and SLA test plan. | Proposed matrix and scenarios documented; approval, implementation and operational test evidence not yet verified. | SLA targets are approved by the appropriate business owner. Breaches trigger the required escalation, an eligible owner accepts responsibility, and the case remains controlled until the required review is complete. |
| Audit logging and record integrity | F004-04 | Ensure material credit-scoring and human-oversight events are attributable, time-ordered, retrievable and protected against unauthorised alteration or deletion. Ensure required security events and logging failures are detected and investigated. | Head of Credit Risk, with relevant Technology / Security control owners | Approved logging requirements; event schema; access-control and integrity configuration; timestamp and retention standards; monitoring and alert configuration; outage/recovery procedure; event reconciliation and investigation records. | ALR-01 to ALR-07, as defined in the audit-logging and record-integrity test plan. | Test plan committed to GitHub based on user confirmation; all seven operational tests remain Not run unless subsequently executed with evidence. | Required events are logged and retrievable, unauthorised changes are prevented, required security events are recorded, timing and monitoring requirements are met, and outage recovery is evidenced. Defects are remediated and retested. |

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

All operational tests must remain `Not run` until they are genuinely executed and evidence is retained.

| Workstream | Test IDs | Current Operational Status | Required Next Action |
|---|---|---|---|
| F004-01 — Reviewer authority | RAT-01 to RAT-06 | Not run unless separately executed and evidenced | Confirm the test cases in the committed reviewer-authority test record, implement the relevant controls and execute the tests. |
| F004-02 — Supporting-evidence access | SEA-01 to SEA-07 | Not run unless separately executed and evidenced | Confirm the test cases in the supporting-evidence test plan, implement the relevant controls and execute the tests. |
| F004-03 — Escalation ownership and SLAs | EOM-01 to EOM-03 | Not run unless separately executed and evidenced | Obtain approval for SLA targets and ownership arrangements, implement them and execute the tests. |
| F004-04 — Audit logging and record integrity | ALR-01 to ALR-07 | Not run | Finalise control implementation requirements, execute the tests in an authorised environment and retain the evidence. |

If any test has been executed since this matrix was drafted, update its status only when the corresponding evidence record supports that status.

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

The following items must be resolved or explicitly accepted by the appropriate authority before closure:

1. **Reviewer authority:** Confirm the end-to-end lending workflow, permitted reviewer roles, override authority and restrictions on automated rejection or decision gating.
2. **Supporting evidence:** Define which source documents and data fields are required, how source reliability and freshness are assessed, and what happens when evidence is unavailable or conflicting.
3. **Escalation and SLAs:** Approve acknowledgement, assignment and escalation targets; define business-hour calendars, clock-start rules, backup ownership and queue-saturation procedures.
4. **Audit logging:** Confirm required event types, timestamp conventions, security-event logging, integrity protection, retention, monitoring and outage-recovery requirements.
5. **Implementation evidence:** Identify the systems and environments where controls are configured and the authorised individuals who can provide evidence.
6. **Independent review:** Confirm who is authorised to review the evidence and approve closure independently of the control implementation.
7. **Residual risk:** Document any remaining limitations and obtain formal risk acceptance from an authorised decision-maker where applicable.

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

**Rationale:** The project has documented the intended human-oversight controls and developed test scenarios. However, this matrix does not establish that all controls have been implemented or that operational tests have passed. Closure requires implementation evidence, test results, remediation of identified defects and independent review.

## 10. Closure Sign-Off Record

Complete this section only after the required evidence has been reviewed.

| Field | Value |
|---|---|
| Finding ID | F-004 |
| Closure recommendation | Pending evidence review |
| Control owner | Head of Credit Risk, subject to confirmation |
| Independent reviewer | AI Governance / Model Risk, subject to confirmation |
| Evidence review date | Not yet completed |
| Outstanding defects | To be confirmed after operational testing |
| Residual risk decision | Pending |
| Final closure decision | Open |
| Closure rationale | Awaiting implementation evidence, operational test results and independent review |

---

## 11. Document Maintenance

Update this matrix whenever a control is implemented, a test is executed, a defect is raised or remediated, evidence is added, or a formal closure decision is made.

Ensure every referenced artifact exists at the stated path in the repository before relying on it as closure evidence. Keep the matrix consistent with the remediation tracker, test records and the AI-001 risk-and-fairness assessment.
