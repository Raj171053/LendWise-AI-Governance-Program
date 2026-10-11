# F004-03 — Escalation Ownership and Service-Level Matrix

## 1. Purpose

Define escalation triggers, accountable ownership, response targets, backup routes and evidence requirements for unresolved AI-001 credit-scoring challenges.

## 2. Current status

- Control ID: F004-03
- Proposed control owner: Head of Credit Risk
- Operational status: Not evidenced
- Test status: Not run
- Test data: Synthetic only
- Independent closure reviewer: AI Governance / Model Risk authority
- Production status: NOT APPROVED — REMEDIATION REQUIRED

This document defines proposed controls. It does not demonstrate that the workflow or SLAs are implemented.

## 3. Escalation and ownership matrix

| Trigger | Initial accountable owner | Required action | Proposed target | Backup route |
|---|---|---|---|---|
| Reviewer cannot resolve a data discrepancy within delegated authority | Assigned reviewer until handoff is acknowledged | Record challenge and route to the authorised decision-maker | Submit promptly; acknowledgement within 4 business hours | Designated deputy or approved escalation owner |
| No owner is assigned to a challenge | Designated queue manager or escalation owner | Assign an eligible owner and record responsibility | Assignment within 4 business hours of challenge creation | Responsible manager or alternate queue owner |
| Required evidence is unavailable | Assigned reviewer and designated evidence-retrieval owner | Keep the case in the approved controlled state; investigate the evidence failure | Acknowledge within 4 business hours; recovery target set by case impact | Approved technical or data-operations escalation route |
| Primary decision-maker is unavailable | Designated deputy or authorised backup | Accept the case only if authority and evidence access are sufficient | Acknowledge within 4 business hours | Next approved level in the escalation hierarchy |
| Assignment or response SLA is breached | Escalation owner | Record breach, assess impact and escalate | Escalate promptly after breach detection | Responsible manager or designated control owner |
| Lending decision deadline is approaching while a material challenge remains unresolved | Assigned case owner and authorised credit-risk manager | Assess urgency and prevent unsupported approval under the approved workflow | Prioritise according to assessed risk and deadline | Pre-designated senior reviewer or approved management route |

**Note:** All response targets above are proposals for training. The accountable business owner must approve or replace them after considering operating hours, customer impact, staffing, regulatory obligations and case severity.

## 4. Ownership rules

1. Every open challenge must have a named accountable owner or an explicitly monitored unassigned-case queue with a designated queue owner.
2. Responsibility transfers only when the receiving owner or approved queue acknowledges the handoff.
3. The original reviewer remains responsible for following the approved handoff procedure until the transfer is confirmed.
4. A backup reviewer must have the necessary authority, competence and access to the supporting evidence.
5. A full queue or unavailable manager does not remove the obligation to escalate.
6. The case must not proceed to approval contrary to the approved evidence and decision requirements.
7. Every unresolved challenge must have a next action, target time and escalation route.

## 5. Proposed SLA definitions

- **Acknowledgement time:** Time from escalation submission to recorded acknowledgement by the receiving owner or queue.
- **Assignment time:** Time from challenge creation to assignment to an eligible owner.
- **Resolution time:** Time until the challenge is resolved or a documented, authorised disposition is reached. This is distinct from acknowledgement.
- **Breach time:** The point at which an approved target is exceeded.
- **Escalation time:** Time from breach detection to the required next-level notification or action.

The organisation must define business hours, holidays, clock-start events, pause rules, severity categories and handling of system outages before adopting these SLAs.

## 6. Required records

For each challenge, retain:

- Synthetic case ID and challenge ID
- Challenge creation timestamp
- Assigned owner, role and assignment timestamp
- Escalation submission, delivery and acknowledgement timestamps
- Applicable SLA and deadline
- Case severity and prioritisation rationale
- Evidence-access or system failure details, where relevant
- Backup route and reason for activation
- Customer communication, where applicable
- Decision, rationale, disposition and closure timestamp
- Relevant audit logs and defect references

## 7. Acceptance criteria

The control can be considered effective only when testing demonstrates that:

1. Escalation triggers are identified correctly.
2. Every case has an accountable owner or a monitored queue with a designated owner.
3. Handoffs are acknowledged and traceable.
4. SLA breaches trigger the approved escalation route.
5. Unavailable owners and full queues activate the approved backup route.
6. The workflow prevents unsupported approval under the approved procedure.
7. Records support reconstruction of the event sequence.
8. Defects are remediated and retested, with independent review.

## 8. Closure requirements

F004-03 remains open until the escalation matrix and SLA definitions are approved, implemented, tested under relevant failure conditions, and supported by retained evidence. The remediation tracker must identify the evidence location and authorised closure decision.

## 9. Data protection

Use synthetic cases and fictitious identifiers. Do not commit real customer information, credentials or confidential production logs to the public repository.
