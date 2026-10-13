# LendWise AI-006 — Customer Support Agent Risk Assessment

**Document status:** Draft for assessment  
**Version:** 0.1  
**System ID:** AI-006 — Customer Support Agent  
**Organization:** LendWise Financial Services Ltd. (fictional)  
**Assessment type:** AI agent risk assessment  
**Related projects:** AI Inventory, NIST AI RMF Assessment, AI Impact Assessment, Governance Operating Model

## 1. Purpose and Intended Use

The proposed Customer Support Agent is intended to assist LendWise support staff with customer enquiries about loan payments, account status, and routine service requests.

The agent may retrieve authorized information, draft responses, recommend next steps, and escalate complex or sensitive cases to human support staff.

This is a hypothetical training scenario. It does not establish that the system exists in production.

## 2. Proposed Capabilities

The proposed agent may be designed to:

- Retrieve customer information through authorized APIs.
- Search approved internal knowledge sources.
- Draft customer-support responses.
- Recommend next steps based on approved procedures.
- Prepare service requests for human review.
- Escalate complaints, suspected fraud, and sensitive cases.

## 3. Potentially Consequential Actions

The following actions require explicit governance decisions before implementation:

- Updating customer contact details.
- Initiating payment-related workflows.
- Submitting complaints or service requests.
- Accessing sensitive customer records.
- Communicating consequential information directly to customers.

The fact that an action is technically possible does not mean the agent is authorized to perform it.

## 4. Initial Autonomy Boundaries

| Activity | Proposed initial permission | Rationale |
|---|---|---|
| Search approved knowledge base | Permitted | Limited to approved sources |
| Retrieve account information | Restricted | Requires verified identity and least-privilege access |
| Draft customer responses | Permitted for review | Human can verify before sending |
| Send routine responses independently | Not authorized initially | Requires separate risk assessment and approval |
| Update customer records | Human confirmation required | Prevents unauthorized or erroneous changes |
| Initiate payment-related actions | Not authorized initially | Requires separate controls and approval |
| Handle suspected fraud or sensitive complaints | Escalate to human | Requires specialist assessment |
| Change permissions or disable safeguards | Prohibited | Agent must not grant itself additional authority |

These are proposed training controls, not verified technical capabilities or implemented safeguards.

## 5. Initial Risk Hypotheses

The assessment must investigate the following potential risks:

1. Prompt injection through customer messages or retrieved documents.
2. Unauthorized access to customer information.
3. Incorrect or fabricated answers about loan accounts.
4. Excessive tool permissions or unintended actions.
5. Failure to escalate sensitive or exceptional cases.
6. Exposure of confidential information in logs or outputs.
7. Inadequate human review of agent-generated recommendations.
8. Failure to record actions and tool calls for investigation.
9. Unsafe behavior following tool errors or unavailable services.
10. Unauthorized changes to system instructions, permissions, or configuration.

These are risks to investigate, not confirmed system defects.

## 6. Preliminary Governance Position

The agent must not be approved for production solely on the basis of this initial assessment.

Before deployment, LendWise must define and validate its identity controls, tool permissions, human confirmation requirements, escalation procedures, monitoring, audit logging, incident response, and testing arrangements.

**Current status:** Assessment in progress.  
**Production approval:** Not granted by this document.
