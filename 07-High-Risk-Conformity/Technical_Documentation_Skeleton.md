# LendWise AI-001 — Technical Documentation Skeleton

**Document status:** Draft template — evidence incomplete  
**Version:** 0.1  
**System ID:** AI-001 — Credit Scoring  
**Organization:** LendWise Financial Services Ltd. (fictional)  
**Related artifact:** `Gap_Assessment.csv`

## Document Control

| Field | Value |
|---|---|
| System name | LendWise AI-001 Credit Scoring |
| Provider identity | To be confirmed |
| System version | To be documented |
| Intended deployment | European Union and India — exact deployment scope to be confirmed |
| Intended purpose | Generate a credit-risk score to support human lending decisions |
| Document owner | Technical Owner — role holder to be assigned |
| Review status | Draft; not approved |
| Last reviewed | To be recorded |

## 1. System Description and Intended Purpose

Describe the system's purpose, architecture, interfaces, model version, intended users, affected persons, deployment environment, and interactions with other systems.

**Known scenario facts:** AI-001 generates a credit-risk score. Humans are intended to make lending decisions.

**Evidence required:** Approved system description, architecture diagram, interface inventory, version history, intended-purpose statement, and documented exclusions.

**Open gaps:** Actual production architecture, version, provider identity, and deployment configuration have not been independently verified.

## 2. Provider and Responsible Parties

Record the legal entity responsible for the system and the applicable roles of provider, deployer, importer, distributor, or other relevant operators.

**Evidence required:** Legal-entity details, system ownership record, contracts, responsibility allocation, and relevant registration details.

**Open gaps:** The applicable legal roles and formal ownership arrangements require confirmation.

## 3. System Design and Development

Document the development process, model architecture, key design choices, training methodology, software dependencies, infrastructure, and version-control arrangements.

**Evidence required:** Technical design, model configuration, development records, software and dependency inventory, and change history.

**Open gaps:** Complete system-level technical documentation has not been verified.

## 4. Data Requirements and Data Governance

Describe training, validation, and testing data as applicable; data sources and provenance; collection and preparation; quality criteria; representativeness; known limitations; and relevant bias-mitigation measures.

**Existing evidence reported:** Dataset-validation notes and the model audit notebook using the public UCI German Credit dataset.

**Evidence required:** Dataset documentation, lineage, suitability assessment, quality checks, label definitions, and documented bias analysis.

**Open gaps:** Proxy-variable risks, label reliability, representativeness, and other data-suitability questions remain under review.

**Important limitation:** The public UCI dataset is a training and portfolio dataset. Its analysis does not establish the quality or representativeness of any real LendWise production dataset.

## 5. Risk Management

Describe the risk-management process across the AI lifecycle, including identification, estimation, mitigation, monitoring, and residual-risk review.

**Existing evidence reported:** NIST AI RMF assessment, AI impact assessment, and consolidated AI-001 remediation tracker.

**Evidence required:** Traceable risk register, control mappings, risk-treatment decisions, monitoring criteria, and authorized residual-risk decisions.

**Open gaps:** Outstanding remediation and operational control evidence must be resolved as applicable.

## 6. Model Performance and Validation

Document intended performance measures, validation methodology, test datasets, baseline results, acceptance criteria, limitations, and independent validation.

**Existing evidence reported:** Model card, audit report, and notebook documenting the baseline logistic regression model.

**Reported baseline results:** Accuracy 0.775; precision for the bad-credit class 0.6364; recall 0.5833; F1 score 0.6087.

**Evidence required:** Reproducible validation records, approved acceptance criteria, documented limitations, and appropriate independent review.

**Open gaps:** The reported baseline is an educational experiment and does not demonstrate production performance or regulatory conformity.

## 7. Fairness and Bias Assessment

Document relevant group-level analyses, proxy-variable risks, limitations in subgroup sample sizes, and remediation decisions.

**Existing evidence reported:** Age-group and housing-group analyses, foreign-worker feature-removal comparison, and associated notes.

**Evidence required:** Justified group selection, appropriate metrics, uncertainty analysis, proxy-variable assessment, and documented mitigation decisions.

**Open gaps:** The existing audit identified unresolved fairness and data-quality questions. Small subgroup sizes limit reliable conclusions.

## 8. Human Oversight

Describe how human decision-makers interpret model outputs, exercise authority, override recommendations, escalate concerns, and avoid overreliance.

**Existing evidence reported:** Human oversight matrix and F-004 control-evidence and closure matrix.

**Evidence required:** Approved oversight procedures, assigned decision rights, competency records, operational test evidence, and review logs.

**Open gaps:** Implementation, operational effectiveness, and independent closure evidence remain outstanding.

## 9. Logging and Record-Keeping

Document required events, log content, timestamps, retention, integrity, access controls, monitoring, and retrieval arrangements.

**Existing evidence reported:** F-004 audit logging test plan and closure matrix.

**Evidence required:** Implemented logging design, retention requirements, access-control evidence, operational test results, and sample records.

**Open gaps:** Operational implementation and successful test results have not been verified.

## 10. Transparency and Instructions for Deployers

Document system capabilities, limitations, intended purpose, performance information, foreseeable risks, and instructions required by relevant users and deployers.

**Existing evidence reported:** Model card, audit report, and governance artifacts.

**Evidence required:** A completed review against applicable transparency and deployer-information requirements, supported by approved documentation.

**Open gaps:** Existing artifacts have not been demonstrated to cover every applicable requirement.

## 11. Accuracy, Robustness, and Cybersecurity

Describe applicable accuracy targets, robustness measures, resilience requirements, cybersecurity controls, and testing methods.

**Existing evidence reported:** Baseline model evaluation and AI-001 remediation documentation.

**Evidence required:** Defined acceptance criteria, robustness and security test results, monitoring procedures, and documented remediation.

**Open gaps:** Baseline performance metrics alone do not demonstrate comprehensive robustness or cybersecurity.

## 12. Quality Management and Change Control

Document applicable quality-management arrangements, version control, release approval, change assessment, supplier dependencies, and post-deployment review.

**Existing evidence reported:** Governance charter, RACI draft, intake form, and remediation tracker.

**Evidence required:** Approved procedures, formal role assignments, release records, change history, and evidence of operation.

**Open gaps:** Formal approval and implementation of the operating model remain unverified.

## 13. Conformity Assessment and Registration

Record the applicable conformity-assessment route, supporting evidence, required declarations, registration obligations, and responsible parties, where applicable.

**Evidence required:** Documented legal analysis, completed applicable assessment records, and registration or declaration evidence as required.

**Open gaps:** The conformity route and completion status have not been established.

**Important:** This skeleton is not a declaration of conformity and does not establish that registration or assessment has been completed.

## 14. Post-Market Monitoring and Corrective Action

Describe applicable monitoring, incident handling, complaints, corrective action, escalation, and relevant reporting arrangements.

**Existing evidence reported:** AI-001 remediation tracker and governance documentation.

**Evidence required:** Approved monitoring plan, escalation and corrective-action procedures, assigned owners, and operating evidence.

**Open gaps:** Operational monitoring and the required supporting evidence remain to be established or verified.

## 15. Evidence Index

For every requirement, record:

- Evidence ID.
- Document or record name.
- Version and date.
- Requirement or finding addressed.
- Evidence owner.
- Repository location.
- Review status.
- Limitations or outstanding actions.

A document's existence does not by itself demonstrate that the associated requirement has been satisfied.

## 16. Open Issues and Approval Status

The following remain outstanding as applicable:

- Final legal classification and scope review.
- Completion of the conformity gap assessment.
- Resolution and validation of required remediation.
- Complete technical documentation and evidence index.
- Implementation and testing evidence for required controls.
- Independent review and authorized approval.

**Current decision:** AI-001 remains Not Approved — Remediation Required.

**Document status:** Draft template; incomplete evidence; not approved for production.

## 17. Change History

| Version | Change | Status |
|---|---|---|
| 0.1 | Initial technical documentation skeleton | Draft |
