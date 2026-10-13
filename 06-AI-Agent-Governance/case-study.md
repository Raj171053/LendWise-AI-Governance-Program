# Case Study: AI Agent Governance at LendWise

## 1. Project Overview

**Organization:** LendWise Financial Services Ltd. (fictional)  
**Headquarters:** Amsterdam, Netherlands  
**Operating markets:** European Union and India  
**Project:** AI Agent Governance  
**System:** AI-006 — Customer Support Agent  
**Role:** AI Governance Program Designer — portfolio simulation  
**Status:** Governance design completed; implementation and testing not verified

## 2. Business Scenario

LendWise is considering a customer-support AI agent that could retrieve authorized account information, search approved knowledge sources, draft customer responses, and recommend next steps.

The proposed agent may interact with customer records and service APIs. These capabilities introduce risks beyond those of a chatbot that only generates text.

Potential risks include unauthorized data access, prompt injection, excessive tool permissions, incorrect account information, inadequate human oversight, and insufficient auditability.

This project develops a proposed governance approach for identifying and managing these risks before deployment.

The system is hypothetical. The assessment does not establish that LendWise has deployed this agent.

## 3. Project Objectives

The project aimed to:

- Define the agent's intended purpose and autonomy boundaries.
- Identify trust boundaries and sensitive assets.
- Develop a structured threat model.
- Map threats to proposed controls and accountable owners.
- Design controlled adversarial tests.
- Define evidence and review requirements for future production decisions.

## 4. Deliverables

### A. Agent Risk Assessment

**Artifact:** `Agent_Risk_Assessment.md`

Documented the proposed agent's capabilities, prohibited or restricted actions, trust boundaries, security requirements, and unresolved design questions.

The assessment established an initial principle: technical capability does not automatically confer authorization.

### B. Threat Model

**Artifact:** `Threat_Model.md`

Identified ten potential threats:

1. Customer prompt injection.
2. Malicious instructions in retrieved content.
3. Unauthorized cross-customer data access.
4. Unauthorized tool execution.
5. Incorrect or conflicting account information.
6. Overreliance on agent recommendations.
7. Sensitive data leakage through logs.
8. Missing or altered audit events.
9. Unsafe behavior during tool or API failures.
10. Unauthorized configuration changes.

These are hypothetical threat scenarios, not confirmed vulnerabilities.

### C. Control Matrix

**Artifact:** `Control_Matrix.xlsx`

Mapped ten threats to proposed controls, suggested owners, test procedures, required evidence, and residual-risk fields.

The matrix provides a traceable link between risk identification and future control validation.

All controls remain proposed, all tests remain untested, and residual risk remains pending.

### D. Red-Team Test Plan

**Artifact:** `Red_Team_Test_Plan.md`

Defined ten controlled test cases covering prompt injection, retrieval manipulation, access control, tool restrictions, response reliability, human review, logging, audit integrity, dependency failures, and configuration security.

The plan specifies expected outcomes, evidence requirements, escalation procedures, and test-completion criteria.

Tests are planned but have not been executed.

## 5. Key Governance Decisions

### Least privilege

The agent should receive only the permissions needed for its approved purpose. Authorization must be enforced at the tool or API layer rather than relying solely on model instructions.

### Human confirmation

Consequential activities, such as customer-record changes and payment-related workflows, must not be enabled merely because the model can request them. They require explicit authorization, appropriate safeguards, and separate assessment.

### Untrusted inputs

Customer messages and retrieved documents must be treated as untrusted content. They must not be allowed to override trusted instructions or grant additional permissions.

### Fail-safe behavior

When an API fails, authorization is unavailable, or information is conflicting, the agent should avoid fabricating results or taking unsafe fallback actions. Defined escalation procedures should apply.

### Evidence-based approval

A proposed control is not equivalent to an implemented control. A completed test plan is not evidence that a test passed. Production decisions require appropriate implementation records, test results, risk review, and authorized approval.

## 6. Safety and Testing Approach

The red-team plan uses synthetic data and a controlled test environment.

It prohibits unauthorized production testing, real customer-data access, real payment actions, and disruptive testing outside an approved scope.

Each executed test must record the environment, configuration, procedure, expected and actual results, evidence, outcome, and any remediation or retest requirements.

Failures and inconclusive outcomes must remain visible rather than being treated as successful validation.

## 7. Relationship to the LendWise Governance Program

This project builds on the earlier AI inventory, NIST AI Risk Management Framework assessment, AI impact assessment, bias and explainability audit, and governance operating model.

The existing governance framework provides the roles, intake process, escalation principles, and evidence-based approval expectations needed to govern an agent with tool access.

The agent-specific assessment extends that foundation to autonomous actions, tool permissions, prompt injection, and adversarial testing.

## 8. Limitations and Open Actions

The project is a design exercise, not a completed security assessment of a deployed system.

The following actions remain outstanding:

- Confirm the actual agent architecture, APIs, and data flows.
- Establish the real permission model and identity controls.
- Assign and approve actual control owners.
- Implement the proposed controls.
- Execute the red-team tests in an authorized environment.
- Preserve test evidence and remediate failures.
- Assess residual risks and obtain independent review where required.
- Obtain formal approval before any production deployment.

No claim is made that the proposed agent is secure, compliant, or production-ready.

## 9. Key Learning Outcomes

This project demonstrates the ability to:

- Identify AI agent risks across data, tools, human operations, and configuration.
- Define trust boundaries and autonomy limits.
- Translate threats into proposed technical and organizational controls.
- Link controls to testable expected outcomes and evidence requirements.
- Design safe adversarial testing using synthetic data.
- Distinguish governance documentation from operational assurance.
- Establish a traceable path from risk identification to remediation and approval.

## 10. Conclusion

The LendWise AI Agent Governance project establishes a proposed foundation for assessing and controlling the risks of a customer-support agent with access to customer data and business tools.

Its central principle is that agent permissions, actions, and outcomes must be governed through enforceable controls, meaningful human oversight, traceable evidence, and structured testing.

The next stage is to validate the proposed design against an actual architecture, implement the safeguards, execute authorized tests, and review the evidence before making a production decision.

**Portfolio note:** LendWise is fictional. The artifacts demonstrate governance design and analytical work, not verified implementation, completed testing, certification, or regulatory compliance.
