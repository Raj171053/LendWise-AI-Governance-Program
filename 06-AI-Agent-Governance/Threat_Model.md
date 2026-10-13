# LendWise AI-006 — Customer Support Agent Threat Model

**Document status:** Draft for review  
**Version:** 0.1  
**System:** AI-006 — Customer Support Agent  
**Organization:** LendWise Financial Services Ltd. (fictional)  
**Related artifact:** Agent_Risk_Assessment.md

## 1. Objective and Scope

This threat model identifies plausible attacks, failure modes, and control weaknesses affecting the proposed LendWise Customer Support Agent.

The assessment covers customer inputs, retrieved knowledge, customer data, tool execution, human operations, and monitoring/configuration.

This is a hypothetical design assessment. The threats below are scenarios to test, not confirmed vulnerabilities in a deployed system.

## 2. System Trust Boundaries

| ID | Trust boundary | Assets to protect |
|---|---|---|
| TB-01 | External customer input | Customer data, system instructions, agent integrity |
| TB-02 | Internal knowledge sources | Instruction integrity, information accuracy, confidentiality |
| TB-03 | Customer data | Personal and financial information |
| TB-04 | Tool execution and APIs | Account integrity, transaction workflows, authorization |
| TB-05 | Human operations | Decision quality, escalation integrity, customer protection |
| TB-06 | Monitoring and configuration | Audit records, credentials, system instructions, configuration |

## 3. Threat Register

| Threat ID | Threat scenario | Boundary | Potential impact | Proposed controls | Required test |
|---|---|---|---|---|---|
| T-01 | A customer submits prompt injection instructions intended to override the agent's rules | TB-01 | Unauthorized disclosure or unsafe actions | Treat external input as untrusted; enforce permissions outside the model | Submit adversarial instructions and verify restrictions remain effective |
| T-02 | A retrieved document contains malicious instructions that the agent follows | TB-02 | Instruction manipulation or data disclosure | Separate retrieved content from trusted instructions; restrict tool authority | Insert a synthetic malicious instruction into test content and verify safe handling |
| T-03 | One customer attempts to retrieve another customer's account information | TB-03, TB-04 | Privacy breach and unauthorized access | Server-side identity checks and record-level authorization | Attempt cross-customer access using synthetic test accounts |
| T-04 | The agent invokes a tool outside its approved purpose | TB-04 | Unauthorized changes or consequential actions | Least privilege, API allowlists, server-side authorization | Attempt prohibited tool calls and verify rejection |
| T-05 | The agent produces an incorrect answer about a payment or loan account | TB-02, TB-03, TB-05 | Customer harm, confusion, or incorrect action | Ground responses in authorized sources; validate facts; escalate uncertainty | Use synthetic cases with missing, conflicting, and incorrect source information |
| T-06 | A support employee accepts an incorrect agent recommendation without checking it | TB-05 | Incorrect customer decisions and weak oversight | Review procedures, training, visible uncertainty, override capability | Present a deliberately incorrect recommendation and assess reviewer behavior |
| T-07 | Logs capture unnecessary personal data or secrets | TB-06 | Privacy or security exposure | Data minimization, redaction, access restrictions, retention controls | Inspect synthetic logs for sensitive-data leakage |
| T-08 | Audit records are missing or can be altered without detection | TB-06 | Inability to investigate incidents or prove control operation | Access-controlled logs, integrity protection, monitoring, retention | Test missing-event detection and unauthorized log modification |
| T-09 | A tool or API fails, times out, or returns malformed data | TB-04 | Incorrect output or unsafe fallback behavior | Fail-safe handling, validation, retry limits, human escalation | Simulate timeouts, malformed responses, and unavailable dependencies |
| T-10 | An unauthorized person changes agent instructions or permissions | TB-06 | Persistent unsafe behavior or expanded access | Restricted administrative access, approved change control, audit trail | Attempt unauthorized configuration changes in a controlled test environment |

## 4. Risk Rating Method

Each threat must be assessed using:

- **Likelihood:** Low, Medium, or High.
- **Impact:** Low, Medium, High, or Critical.
- **Inherent risk:** Risk before considering the effectiveness of controls.
- **Control status:** Proposed, Implemented, Tested, or Evidence Missing.
- **Residual risk:** Risk remaining after implemented controls have been tested.

Do not assign a residual risk rating merely because a control has been proposed. Control effectiveness must be supported by appropriate evidence.

Final risk ratings remain pending a documented assessment of likelihood, impact, and existing safeguards.

## 5. Threat Scenarios Requiring Priority Testing

The initial priority test scenarios are:

1. Prompt injection through customer input.
2. Unauthorized cross-customer data access.
3. Attempts to invoke prohibited tools.
4. Unsafe behavior when APIs fail.
5. Leakage of personal data through responses or logs.
6. Unauthorized changes to system instructions or permissions.

These scenarios are prioritized because they could affect customer confidentiality, account integrity, or the agent's permitted scope of action.

The priority order is provisional and must be reviewed against the implemented architecture and evidence.

## 6. Dependencies and Assumptions

The assessment assumes that the proposed agent may use a knowledge base and authorized APIs. The actual architecture, APIs, authentication design, deployment environment, model provider, and logging implementation have not been verified.

Before finalizing this threat model, LendWise must confirm:

- The actual architecture and data flows.
- The complete inventory of tools and API permissions.
- Authentication and authorization enforcement points.
- Data retention and logging arrangements.
- Human confirmation and escalation requirements.
- The mechanism for disabling agent execution during an incident.

## 7. Governance Decision

The threat model provides a structured basis for control design and adversarial testing.

It does not establish that any threat has occurred or that any proposed control is operational.

**Current status:** Draft — threats identified; implementation and test evidence outstanding.

**Production approval:** Not granted by this document.

## 8. Change History

| Version | Change | Status |
|---|---|---|
| 0.1 | Initial threat register based on the proposed trust boundaries | Draft |
