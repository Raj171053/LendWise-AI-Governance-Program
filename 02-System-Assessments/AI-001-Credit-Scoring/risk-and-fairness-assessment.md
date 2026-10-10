# AI-001 — Credit-Scoring Risk and Fairness Assessment

**Company:** LendWise Financial Services Ltd.  
**System ID:** AI-001  
**Assessment type:** AI risk, fairness and governance assessment  
**Version:** 0.1 — Initial working assessment  
**Status:** NOT APPROVED — REMEDIATION REQUIRED  
**Evidence basis:** Fictional scenario and synthetic training metrics  
**Geographic scope:** European Union and India

---

## 1. Executive Summary

LendWise uses AI-001 to generate credit-risk scores that support lending assessments for consumers and small businesses. Human decision-makers are intended to make the final lending decisions.

The system presents material risks involving discriminatory outcomes, proxy variables, unreliable or unrepresentative data, model errors, insufficient explainability and ineffective human oversight.

For EU AI Act purposes, the assessment identifies AI-001 as **high-risk under Annex III, Section 5(b)** insofar as it evaluates the creditworthiness of natural persons or establishes their credit score, subject to the provision's scope and applicable exceptions. Credit scoring of small-business legal entities must be assessed separately from scoring natural persons.

Illustrative training metrics show that approval-rate disparities narrowed after retraining. However, metric definitions, data representativeness, label reliability, subgroup sample sizes and uncertainty have not yet been established. The results therefore do not demonstrate that the model is fair, reliable or ready for production.

**Decision:** AI-001 remains NOT APPROVED — REMEDIATION REQUIRED pending documented remediation, independent validation and formal approval.

## 2. System Description and Intended Use

| Attribute | Assessment |
|---|---|
| System name | AI-001 Credit Scoring System |
| Business function | Credit risk and lending |
| Capability | Predictive modelling |
| Intended purpose | Generate a credit-risk score to support human lending assessments |
| Affected individuals | Consumer applicants and natural persons whose data is processed in relevant lending assessments |
| Additional affected parties | Small businesses and their relevant representatives, where applicable |
| Geography | EU and India |
| Decision model | AI-generated score; human final lending decision intended |
| Autonomous action | No autonomous lending decision is intended; automatic rejection, access gating and other downstream actions must be verified |
| Enterprise risk | HIGH |
| EU AI Act classification | HIGH-RISK for in-scope creditworthiness evaluation or credit scoring of natural persons |
| Current governance status | NOT APPROVED — REMEDIATION REQUIRED |

The assessment covers model outputs, the data used to produce them, downstream lending workflows, human oversight, fairness evaluation and post-deployment monitoring requirements.

## 3. Regulatory and Governance Rationale

### 3.1 EU AI Act

Annex III, Section 5(b) of Regulation (EU) 2024/1689 covers AI systems intended to evaluate the creditworthiness of natural persons or establish their credit score, except AI systems used for detecting financial fraud.

AI-001's stated purpose is credit scoring, not financial fraud detection. The system is therefore treated as high-risk for in-scope natural-person creditworthiness use.

Human involvement in the final decision does not, by itself, remove the high-risk classification.

The assessment must also determine which provider/deployer obligations apply, whether any statutory exception is genuinely available, and which requirements are applicable on the relevant dates and in each operating jurisdiction.

### 3.2 Data protection and automated decision-making

Where personal data is processed, the applicable data-protection framework must be assessed separately from AI Act classification.

For EU processing, relevant considerations include GDPR principles of lawfulness, fairness, transparency, data minimisation and accuracy, as well as profiling and Article 22 where its specific conditions are met. The presence of a human reviewer should not be assumed to settle Article 22 applicability without examining the actual decision workflow.

Financial data is not automatically special-category personal data under GDPR Article 9. The actual fields, inferences and purposes must be reviewed.

India-specific data-protection obligations must be assessed separately, including applicable commencement provisions and rules.

### 3.3 Governance frameworks

NIST AI RMF provides a voluntary framework for organising risk governance, mapping, measurement and management. ISO/IEC 42001 may provide additional management-system guidance.

These frameworks support governance practices; they do not independently establish legal compliance.

## 4. Principal Risk Scenarios

| Risk ID | Risk scenario | Potential impact | Initial priority |
|---|---|---|---|
| R-001 | Protected characteristics or proxy variables influence scores or outcomes | Unfair differences in access to credit | High |
| R-002 | Historical lending outcomes produce biased or incomplete training labels | Misleading predictions and unreliable fairness conclusions | High |
| R-003 | Inaccurate, missing or unrepresentative data affects particular applicant groups | Unequal error rates or inappropriate assessments | Medium — provisional |
| R-004 | False-positive or false-negative errors differ materially across groups | Unfair assessments and financial harm | High |
| R-005 | Human reviewers over-rely on model scores or cannot meaningfully challenge them | Incorrect decisions despite nominal human oversight | High |
| R-006 | Automatic rejection or access gating occurs despite the stated human-decision design | Applicants may be denied meaningful review | High |
| R-007 | Model performance or group disparities deteriorate after deployment | Undetected harm and inconsistent lending outcomes | High |
| R-008 | Applicants and reviewers cannot understand or appropriately challenge relevant outputs | Reduced accountability and ineffective redress | Medium — provisional |

Priorities are initial governance judgments. They must be revisited using evidence about likelihood, severity, affected populations and existing controls.

## 5. Fairness Evaluation

### 5.1 Illustrative results

The following figures are synthetic training data. They are not measurements from a deployed LendWise model.

| Metric | Initial model | Retrained model |
|---|---:|---:|
| Group A approval rate | 60% | 58% |
| Group B approval rate | 40% | 54% |
| Group B/A approval-rate ratio | 0.667 | 0.931 |
| Group A false-positive rate | 8% | 9% |
| Group B false-positive rate | 15% | 10% |
| Group A false-negative rate | 12% | 14% |
| Group B false-negative rate | 25% | 16% |
| Overall accuracy | 82% | 86% |

### 5.2 Interpretation

The observed approval-rate ratio increased from 0.667 to 0.931. The approval-rate difference between the groups narrowed from 20 to 4 percentage points.

The displayed false-positive-rate gap narrowed from 7 to 1 percentage point, while the false-negative-rate gap narrowed from 13 to 2 percentage points. Overall accuracy increased by 4 percentage points.

These changes are encouraging within the illustrative scenario, but they are not sufficient to conclude that the retrained model is fair or suitable for production. Group A's displayed false-positive and false-negative rates also increased.

The four-fifths rule may be used as a screening indicator where appropriate, but it is not a universal legal test or proof of fairness. Approval-rate parity alone does not establish equal treatment, predictive validity or the absence of discrimination.

### 5.3 Measurement limitations

Before these metrics can support a governance decision, the evaluation methodology must document:

1. **Target definition:** Specify what the model predicts, including the default or repayment outcome and its time horizon, if applicable.
2. **Positive class:** Define whether the positive class means default, high credit risk or another outcome.
3. **Error definitions:** Define false positives and false negatives relative to the selected target and explain their operational consequences.
4. **Denominators:** Document the population used to calculate each rate and the reference outcome required.
5. **Population coverage:** Specify evaluation dates, geography, applicant types, exclusions and subgroup sample sizes.
6. **Label quality:** Explain how outcomes were established, whether outcomes are mature and reliable, and whether historical lending decisions introduce selection bias.
7. **Uncertainty:** Report confidence intervals or other appropriate uncertainty estimates and assess whether observed differences are stable.
8. **Reproducibility:** Retain metric definitions, evaluation code or methodology, data versions, model versions and test records.

Until these conditions are satisfied, the error-rate comparisons remain illustrative and cannot be treated as validated fairness evidence.

## 6. Root-Cause Investigation

The following investigations are required before the fairness findings can be closed.

### 6.1 Proxy-variable analysis

Identify features that may act as proxies for protected or otherwise sensitive characteristics, including variables related to geography, economic circumstances or historical access to credit.

For each material feature, document its purpose, provenance, necessity, relationship to the target and potential effect on outcomes across relevant groups. Removing an explicit sensitive attribute is not sufficient if other variables preserve similar discriminatory effects.

### 6.2 Data quality and representativeness

Assess missingness, inconsistent records, duplicate data, measurement error, label quality and coverage across relevant populations, markets and time periods.

Investigate whether the available repayment outcomes disproportionately represent previously approved applicants. Document limitations in evaluating applicants whose outcomes are not observed and explain how those limitations affect the validity of the findings.

### 6.3 Model validation

Evaluate performance and calibration where appropriate, robustness, stability over time, sensitivity to data changes and relevant subgroup outcomes. Compare alternative approaches using predefined criteria and documented trade-offs.

Do not select a model solely because it has higher overall accuracy or a better approval-rate ratio.

## 7. Human Oversight and Operational Controls

Before approval, LendWise must document and test the following controls:

- **Decision authority:** Confirm that no automatic rejection, lending decision or equivalent access gate bypasses the intended human decision process.
- **Meaningful review:** Give reviewers sufficient information, competence, time and authority to challenge the score.
- **Override and escalation:** Define when a reviewer must seek a second opinion, how overrides are authorised and how disagreements are resolved.
- **Traceability:** Record relevant model version, score, input-data references, reviewer action, override reason and final decision, subject to appropriate data-protection safeguards.
- **Applicant review and redress:** Define applicable explanation, correction, complaint and reconsideration processes.
- **Monitoring:** Track model performance, data quality, subgroup outcomes, overrides and complaints against approved criteria.
- **Incident response:** Define escalation, suspension, rollback and reassessment when material harm or performance deterioration is detected.

The existence of a human reviewer is not enough: the organisation must establish that oversight is effective in practice.

## 8. Findings and Remediation Register

| Finding | Priority | Required action | Closure evidence |
|---|---|---|---|
| F-001: Proxy-variable risk is unresolved | High | Conduct documented feature and proxy analysis | Approved analysis, feature justifications and mitigations |
| F-002: Fairness metrics are not fully defined | High | Finalise target, positive class, denominators and evaluation methodology | Reproducible metric specification and validated results |
| F-003: Label reliability and selection bias are uncertain | High | Assess label provenance, outcome maturity and selection effects | Data and label-quality report with limitations documented |
| F-004: Human oversight requirements are incomplete | High | Define reviewer authority, escalation, overrides and logs | Approved oversight matrix and workflow test evidence |
| F-005: Data representativeness is unverified | Medium — provisional | Assess coverage, missingness and subgroup representation | Documented data-quality and representativeness assessment |
| F-006: Residual group disparities require investigation | Medium — provisional | Investigate causes and evaluate against predefined criteria | Root-cause analysis and independent evaluation |
| F-007: Downstream automatic rejection or gating is unverified | High | Inspect and test the actual decision workflow | Evidence that system behaviour matches approved design |

Finding priorities must be reassessed as evidence becomes available. Each finding must have a named accountable owner, due date, current status and approval authority for closure.

## 9. Production Approval Criteria

AI-001 must not be approved for production until the accountable governance authority has reviewed evidence that:

1. The intended purpose, regulatory classification and actual decision workflow are documented.
2. Material proxy, data-quality and fairness findings have been investigated and adequately addressed or explicitly handled through an authorised risk decision where permitted.
3. Fairness metrics are well-defined, reproducible and supported by suitable evaluation data and uncertainty analysis.
4. Independent model validation has been completed and residual risks documented.
5. Human oversight, override, escalation, logging and applicant redress controls have been tested.
6. Monitoring thresholds, incident procedures, suspension and rollback arrangements have been approved.
7. Required regulatory, legal, privacy, model-risk and business approvals have been obtained.

Acceptance criteria must be justified and set before final validation. A single ratio or accuracy threshold must not substitute for the overall assessment.

## 10. Final Assessment Decision

**Decision: NOT APPROVED — REMEDIATION REQUIRED**

The illustrative retraining results show narrower observed disparities, but material evidence gaps remain regarding metric definitions, data and label quality, proxy effects, subgroup reliability and operational human oversight.

The model may be reconsidered only after the required remediation and validation evidence has been reviewed by the designated accountable authority. This assessment is a training artifact, not a production certification or legal opinion.

### Assessment limitations

All company and model details are fictional. The quantitative results are synthetic. No real applicant data, production testing, independent audit or legal determination is represented by this document.

### References

- EU AI Act, Regulation (EU) 2024/1689, including Article 6 and Annex III, Section 5(b).
- General Data Protection Regulation (EU) 2016/679, including Articles 5, 6, 13–15 and 22 where applicable.
- NIST AI Risk Management Framework 1.0.
- LendWise regulatory source register: `sources/regulatory-source-register.md`.

Applicable legal requirements and commencement dates must be verified for the relevant jurisdiction and use case.
