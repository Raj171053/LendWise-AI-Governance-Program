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

## 7. Trust Boundaries and Tool Access

### 7.1 Trust Boundaries

The proposed agent operates across the following trust boundaries:

| Boundary | Components or data | Primary concern |
|---|---|---|
| TB-01: External input | Customer messages, uploaded files, and customer-provided links | Prompt injection, malicious instructions, and misleading information |
| TB-02: Internal knowledge | Approved support documentation and retrieved content | Untrusted or outdated instructions embedded in retrieved material |
| TB-03: Customer data | Account information and personal or financial records | Unauthorized access and disclosure |
| TB-04: Tool execution | APIs for account lookup, customer-record updates, and service requests | Excessive permissions and unauthorized actions |
| TB-05: Human operations | Support agents, supervisors, and escalation teams | Automation bias and unclear decision authority |
| TB-06: Monitoring and configuration | Logs, system instructions, credentials, and agent settings | Sensitive-data leakage, tampering, and unauthorized configuration changes |

### 7.2 Proposed Tool Permission Matrix

| Tool or capability | Proposed permission | Required control |
|---|---|---|
| Search approved knowledge base | Read-only | Approved source allowlist and input sanitization |
| Retrieve customer account details | Restricted read | Authentication, authorization, and least privilege |
| Draft a support response | Draft only | Output validation and human review |
| Send a customer response | Not authorized initially | Separate approval and tested safeguards before reconsideration |
| Update customer contact details | Human confirmation required | Server-side authorization and confirmation of the exact change |
| Initiate payment-related actions | Prohibited initially | Separate risk assessment and explicit authorization before any future consideration |
| Submit a complaint or service request | Prepare draft only | Human review before submission |
| Read audit logs | Restricted | Role-based access and sensitive-data protection |
| Change system instructions or permissions | Prohibited to the agent | Authorized human-controlled change process |

These are proposed design requirements. They do not establish that the APIs, permissions, or safeguards currently exist.

### 7.3 Security Requirements

1. Enforce authorization at the tool or API layer; do not rely on the language model to enforce access restrictions.
2. Give each tool only the minimum permissions needed for its approved purpose.
3. Treat customer messages and retrieved documents as untrusted input.
4. Never allow content from a customer message or retrieved document to grant new permissions or override system safeguards.
5. Require explicit confirmation and server-side validation before any permitted consequential action.
6. Keep credentials and secrets outside prompts and model-visible content wherever feasible.
7. Record tool calls, authorization outcomes, and consequential actions without unnecessarily logging sensitive customer information.
8. Fail safely when authorization, validation, or required dependencies are unavailable.
9. Provide a mechanism to stop agent execution and escalate unexpected behavior.
10. Test the controls against adversarial inputs before production approval.

### 7.4 Open Questions

The following information remains unknown in this training scenario:

- Which APIs will actually be available to the agent?
- How will customer identity and authorization be verified?
- Which actions will require human confirmation?
- How will tool permissions be enforced and tested?
- What data will be retained in prompts, tool results, and logs?
- Who can change the agent's configuration or permissions?
- How will the agent be stopped during an incident?

These questions must be resolved during detailed design and validation.

**Assessment status:** Trust boundaries documented as proposed design requirements. Implementation and testing evidence remain outstanding.
