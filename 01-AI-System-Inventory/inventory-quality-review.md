# AI Inventory Quality Review — LendWise Financial Services Ltd.

## 1. Review purpose

This document records a desk-based quality review of the LendWise AI System Inventory supplied for this training programme. It checks the inventory's structure, internal consistency, clarity of risk and classification fields, and visibility of unresolved evidence gaps.

LendWise is fictional. System details and any performance figures used elsewhere in the programme are synthetic. This review is an educational governance exercise, not legal advice, independent assurance, or evidence of regulatory compliance.

## 2. Review scope and method

The reviewed register contains 11 entries across 19 columns:

- AI-001 through AI-010
- Separate entries AI-006A and AI-006B

The review considered whether:
1. Each system has a distinct identifier and name.
2. Enterprise risk is distinguished from EU AI Act classification.
3. The intended purpose supports the stated classification on the documented facts.
4. Human oversight and autonomous actions are described.
5. Unknown facts are marked for confirmation rather than assumed.
6. Governance status is consistent with unresolved material risks.

This review is based on the submitted CSV only. It does not independently validate the underlying systems, vendor documentation, test results, or legal interpretations.

## 3. Overall conclusion

**Outcome: Suitable to proceed to detailed project documentation, with material evidence gaps retained for follow-up.**

The register contains 11 system entries and 19 named fields. It generally distinguishes enterprise AI risk from EU AI Act classification and identifies unresolved facts using terms such as `TBD`, `provisional`, or equivalent qualification.

The inventory should not be interpreted as granting production approval. Several systems remain not approved, rejected, or limited to controlled testing. Those restrictions must be reflected in any corresponding test plan or deployment workflow.

## 4. System-specific review notes

### AI-001 — Credit Scoring System

- The register identifies a high-risk classification under Annex III, Section 5(b), for assessing the creditworthiness of natural persons.
- The rationale appropriately distinguishes natural-person applicants from legal-entity small-business applicants.
- The autonomous-actions field states that no autonomous lending decision is intended, while requiring confirmation of automated rejection, eligibility gating, or other customer-impacting actions.
- **Follow-up:** confirm the system's actual applicant scope and whether any automated gating or rejection occurs.

### AI-002 — Customer Support AI

- The register describes an internal assistant that retrieves approved information and drafts responses for human review.
- Its classification rationale does not assume that an internal drafting assistant necessarily triggers Article 50(1)'s direct AI-interaction disclosure provision.
- **Follow-up:** confirm whether any customer-facing interface or direct AI communication exists, and assess transparency requirements against the deployed interaction design.

### AI-003 — Fraud Detection AI

- The register records a critical enterprise risk and distinguishes the stated fraud-detection purpose from creditworthiness assessment under Annex III, Section 5(b).
- The autonomous-actions field describes threshold-based automated blocking and says customer-impacting production blocking is not approved pending controls.
- **Follow-up:** explicitly record whether automated blocking is disabled in testing, enabled in a restricted environment, or active in production. Define thresholds, validation criteria, review/override authority, response times, and rollback conditions before any approved live use.

### AI-004 — KYC Document AI

- The register describes one-to-one biometric verification for confirming a claimed identity and records the relevant Annex III, Section 1(a) distinction.
- The autonomous-actions field says the system may automatically determine an initial KYC outcome and allow onboarding to continue.
- **Follow-up:** document which outcomes can be automated, which require human review, the exception-handling process, and the technical purpose and scope of the biometric component. The stated exclusion from the remote-biometric-identification category does not by itself establish compliance with all other applicable requirements.

### AI-005 — CV Screening AI

- The register identifies high-risk classification under Annex III, Section 4(a), for recruitment and selection.
- The classification field contains both the category and a supporting explanation; the regulatory-rationale field separately describes the recruitment and selection purpose.
- **Follow-up:** for readability and maintainability, keep the classification field concise and retain the fuller explanation in the rationale field. The system's automatic rejection behaviour and opaque vendor evidence remain important governance concerns. Do not treat a vendor's general assertion of fairness as sufficient evidence.

### AI-006A — Customer Emotion/Vulnerability AI

- The register records a potential high-risk classification under Annex III, Section 1(c), conditional on the technical processing meeting the legal definition of biometric-data-based emotion recognition.
- **Follow-up:** obtain technical documentation on the inputs, inference method, outputs and intended purpose; validate performance and customer impact; define human review, challenge, escalation and monitoring. Keep the classification conditional until the relevant facts are established.

### AI-006B — Employee Emotion Analysis AI

- The register records a potentially prohibited workplace emotion-recognition use under Article 5(1)(f), subject to confirmation of the technical basis and applicable exception.
- Its governance status rejects the proposed use on current facts.
- **Follow-up:** do not treat accuracy improvements or ordinary managerial oversight as curing a prohibited use. Obtain a fact-specific legal assessment if the technical purpose or proposed use changes. Keep any alternative fatigue-only safety proposal separate from this entry.

### AI-007 — Marketing Recommendation AI

- The register appropriately treats marketing personalisation as not automatically high-risk while flagging possible downstream creditworthiness or financial-product access implications.
- **Follow-up:** document the target variable, features, outputs, campaign triggers, customer exclusions and any connection to product eligibility or credit decisions. Resolve privacy, profiling, direct-marketing objection, and customer-harm controls before live deployment.

### AI-008 — Loan Document Summarisation AI

- The register recognises that summarisation alone does not establish an Annex III high-risk use case and identifies the potential harm from inaccurate or incomplete financial terms.
- **Follow-up:** define critical-term accuracy and completeness tests, source-clause traceability, human verification requirements, data handling, retention and vendor reuse restrictions before any customer-facing or consequential use.

### AI-009 — Collections Prioritisation AI

- The register treats classification as conditional on the actual purpose and downstream use, rather than assuming that collections prioritisation automatically constitutes creditworthiness assessment.
- **Follow-up:** document the target variable, contact/escalation actions, features, hardship and dispute handling, contact-frequency limits, human review and challenge mechanisms. Define evidence and acceptance criteria before controlled shadow testing.

### AI-010 — Autonomous Operations Agent

- The register distinguishes autonomy from statutory high-risk classification and records security, privacy, prompt-injection, data-exfiltration and cascading-action risks.
- The enterprise risk is marked high provisionally, with potential escalation to critical depending on permissions and containment.
- **Follow-up:** produce an action-by-action permission inventory; identify irreversible and customer-impacting actions; apply least privilege, allowlists, server-side authorisation, logging, rate limits, emergency stop and recovery tests. Confirm whether communications, account updates and workflow initiation are shadow-only or enabled.

## 5. Cross-inventory findings

### Finding Q-01 — Production and test-state clarity

**Priority:** High  
**Observation:** AI-003 describes automated blocking while restricting customer-impacting production use pending controls. AI-004 also describes automated KYC outcomes.  
**Required action:** Record the actual environment and enabled permissions for each material autonomous action.  
**Closure evidence:** Approved system configuration, action-permission matrix, test/production boundary, and signed deployment decision.

### Finding Q-02 — Accountability and evidence ownership

**Priority:** Medium  
**Observation:** Some provider details, system ownership, exact data fields, decision rules, or permissions remain uncertain.  
**Required action:** Assign an accountable owner and due date for each material unresolved field.  
**Closure evidence:** Updated inventory plus linked evidence or a documented reason why the field is not applicable.

### Finding Q-03 — Consistent classification rationale

**Priority:** Medium  
**Observation:** Some classification fields contain longer explanations while the rationale field repeats part of the explanation. The substance is generally understandable, but a consistent format would improve reviewability.  
**Required action:** Keep the classification field concise; put the legal reasoning, factual assumptions and limitations in the rationale field.  
**Closure evidence:** Consistent format across all 11 entries.

### Finding Q-04 — Conditional legal conclusions

**Priority:** High  
**Observation:** Some conclusions depend on technical details, actual intended purpose, or downstream use, particularly AI-006A, AI-006B, AI-007, AI-009 and AI-010.  
**Required action:** Preserve conditional wording and obtain technical or legal validation where needed. Reassess after material changes.  
**Closure evidence:** Documented facts, applicable source references, assessment decision and approver.

### Finding Q-05 — Remediation traceability

**Priority:** Medium  
**Observation:** The inventory records governance status but is not a complete remediation register.  
**Required action:** Maintain a separate register with finding ID, system ID, severity, action, owner, due date, evidence link, validation result and closure approval.  
**Closure evidence:** A maintained remediation register linked to the relevant system assessments.

## 6. Recommended governance status interpretation

- **In testing:** controlled testing is underway; this is not production approval.
- **Not approved / remediation required:** the system must not be deployed beyond explicitly authorised testing until required controls are validated and approval is recorded.
- **Rejected — prohibited use on current facts:** the described use is rejected; ordinary mitigation does not override an applicable legal prohibition.
- **Not approved for unrestricted live deployment:** any limited testing must have explicit scope, safeguards, access boundaries and approval conditions.

## 7. Review decision

The inventory is sufficiently structured to serve as the baseline for detailed system assessments and governance documentation. This is a **documentation-readiness decision only**. It is not a conclusion that every legal classification is final, all evidence gaps are closed, or any system is approved for production.

## 8. Next steps

1. Preserve the current register as a version-controlled baseline.
2. Resolve the production/test-state and permission questions for AI-003 and AI-004.
3. Standardise classification/rationale formatting.
4. Create a separate remediation register.
5. Begin the detailed AI-001 credit-scoring assessment, including fairness metrics, proxy analysis, human oversight and evidence requirements.

## 9. Source and limitation note

The legal analysis in this training artifact should be checked against the applicable official text of Regulation (EU) 2024/1689, GDPR, and relevant Indian data-protection provisions, including commencement and implementing rules where applicable. The inventory and this review do not substitute for legal advice or independent technical assurance.
