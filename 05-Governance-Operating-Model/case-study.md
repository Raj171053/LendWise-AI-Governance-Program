# Case Study: Designing an AI Governance Operating Model for LendWise

## 1. Project Overview

**Organization:** LendWise Financial Services Ltd. (fictional)  
**Headquarters:** Amsterdam, Netherlands  
**Operating markets:** European Union and India  
**Project:** AI Governance Operating Model  
**Status:** Draft governance framework and supporting templates  
**Role:** AI Governance Program Designer — portfolio simulation

### Objective

Design a practical governance operating model for a fictional financial-services organization using AI in credit scoring, customer support, fraud detection, biometric verification, recruitment, and other business processes.

The objective was to define governance responsibilities, establish a consistent intake process, and create a structured approach to assessing third-party AI providers.

## 2. Business Problem

AI adoption can create risks involving fairness, privacy, security, accountability, explainability, supplier dependency, and inadequate human oversight.

Without a defined operating model, an organization may lack clarity about:

- Who owns an AI system and its associated risks.
- Who can approve a system for deployment.
- Which assessments must be completed before deployment.
- How governance findings are tracked and closed.
- What evidence is required to evaluate an AI vendor.
- How incidents, material changes, and residual risks are escalated.

LendWise therefore required a proposed governance structure that connects AI risk assessments to business decisions, accountable owners, and documented evidence.

## 3. Deliverables Created

### A. Governance Charter

**Artifact:** `Governance_Charter.md`

Defined the proposed governance principles, organizational roles, AI lifecycle gates, remediation requirements, exception handling, monitoring expectations, and implementation requirements.

The charter distinguishes a documented governance design from an approved and operational governance program.

### B. RACI Matrix

**Artifact:** `RACI.csv`

Established proposed Responsible, Accountable, Consulted, and Informed assignments for activities including:

- AI intake and registration.
- Enterprise risk assessment and legal classification.
- Privacy review and model validation.
- Production approval and finding closure.
- Incident escalation and ongoing monitoring.
- Vendor assessment and system retirement.

The matrix was corrected to clarify accountability for legal classification, production approval, and finding closure verification.

Actual role holders and delegated decision-making authority remain subject to formal approval.

### C. AI Intake Form

**Artifact:** `Intake_Form.md`

Created a structured form for recording the business purpose, intended users, technical characteristics, data processing, potential impacts, human oversight, testing requirements, and preliminary governance decisions for proposed AI systems.

The form explicitly separates enterprise risk assessment from legal classification.

It also clarifies that acceptance of an intake request is not authorization to deploy an AI system.

### D. Vendor Assessment

**Artifact:** `Vendor_Assessment.xlsx`

Created a 15-question assessment covering governance, data quality, fairness, explainability, security, privacy, human oversight, monitoring, incident management, auditability, third-party dependencies, contractual safeguards, and exit arrangements.

The template identifies evidence to request, potential gaps, required actions, risk ratings, and review status.

Because this is a hypothetical exercise, no real supplier responses or independent validation evidence were received. Ratings remain pending rather than being presented as completed findings.

## 4. Governance Approach

The proposed operating model follows a lifecycle-based approach:

1. **Intake:** Register the proposed AI use case and identify its owner and intended purpose.
2. **Classification:** Assess enterprise risk and applicable legal classification separately.
3. **Assessment:** Identify relevant privacy, fairness, security, technical, and operational risks.
4. **Validation:** Obtain evidence that required controls and tests are adequate.
5. **Approval:** Submit the evidence and unresolved risks to authorized decision-makers.
6. **Monitoring:** Track performance, incidents, complaints, overrides, and material changes.
7. **Remediation:** Assign findings, collect implementation and test evidence, and obtain the required closure review.

The approach emphasizes that a policy or completed template is not sufficient proof that a control operates effectively.

## 5. Connection to AI-001 Credit Scoring

The operating model was designed to support the existing LendWise AI governance case study, including AI-001 Credit Scoring.

AI-001 has previously been assessed through the AI inventory, NIST AI Risk Management Framework assessment, AI impact assessment, and bias and explainability audit.

The existing project record identifies outstanding issues involving proxy variables, fairness evaluation, data quality, human oversight, monitoring, and production evidence.

The governance charter requires those findings to remain traceable through remediation and independent review.

**Current decision:** AI-001 remains Not Approved — Remediation Required. Creating the operating-model documents does not change this decision.

## 6. Framework Alignment

The proposed operating model uses the NIST AI Risk Management Framework as a risk-management reference and anticipates assessment of applicable obligations under the EU AI Act and relevant Indian data-protection and sectoral requirements.

This is a preliminary framework alignment exercise, not a legal opinion, regulatory conformity assessment, certification, or claim of compliance.

Applicability must be determined against the actual system, intended purpose, deployment context, and relevant legal requirements.

## 7. Limitations and Open Actions

The project remains a governance design exercise rather than a fully implemented organizational program.

The following actions remain necessary:

- Formally approve the governance charter.
- Appoint actual role holders and confirm decision-making authority.
- Validate and approve the RACI matrix.
- Approve the AI intake process and supporting procedures.
- Pilot the vendor assessment with a real supplier and obtain supporting evidence.
- Establish operating procedures for monitoring, escalation, exceptions, and record retention.
- Demonstrate that required controls operate effectively.
- Maintain traceable evidence of approvals, remediation, and independent review.

No actual vendor has been approved or rejected through this exercise.

## 8. Key Learning Outcomes

This project demonstrates the ability to:

- Translate AI governance principles into organizational responsibilities and workflows.
- Distinguish responsibility for execution from accountability for decisions.
- Build structured intake and third-party assessment templates.
- Connect governance findings to owners, evidence requirements, and approval gates.
- Distinguish documented controls from implemented and tested controls.
- Preserve the difference between enterprise AI risk and legal classification.
- Carry existing assessment findings into an operating model without duplicating earlier work.

## 9. Conclusion

The LendWise AI Governance Operating Model provides a proposed foundation for managing AI systems through defined responsibilities, intake screening, vendor due diligence, approval gates, and evidence-based remediation.

Its value lies in connecting risk assessment to accountable decisions and verifiable controls.

The next stage would be formal approval, assignment of real role holders, pilot implementation, and validation that the proposed governance processes work in practice.

**Portfolio note:** LendWise is a fictional case study. The documents demonstrate proposed governance design and analytical work; they do not establish real-world implementation or regulatory compliance.
