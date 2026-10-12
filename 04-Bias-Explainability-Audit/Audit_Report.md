# LendWise AI-001 — Bias & Explainability Audit Report

**Document status:** Draft — For Governance Review  
**System ID:** AI-001 — Credit Scoring  
**Version:** 0.1  
**Audit type:** Exploratory model audit using a historical public dataset  
**Decision:** **Not Approved — Remediation Required**

---

## 1. Executive Summary

This audit evaluated an exploratory logistic-regression model using the UCI Statlog German Credit Data dataset to demonstrate model performance assessment, group-level error analysis, coefficient interpretation, individual prediction explanations, and feature-removal testing.

The baseline model achieved 77.5% accuracy on a held-out test set of 200 records. Group-level error rates varied across the age and housing categories examined. A comparison model trained without `foreign_worker` reduced the false-positive rate but increased the false-negative rate, demonstrating a trade-off rather than a clear overall improvement.

These results identify areas requiring governance review, including feature justification, potential proxy effects, group-level performance, explainability limitations, and independent validation.

The analysis is exploratory. It does not establish the performance or fairness of LendWise's actual production system, prove discrimination, or demonstrate legal compliance.

**Recommendation:** Maintain the decision that AI-001 is Not Approved — Remediation Required until the necessary evidence, controls, independent validation, and authorized approval are in place.

## 2. Scope and Methodology

### Scope

The audit examined:

- Dataset quality and target preparation.
- Baseline logistic-regression performance.
- False-positive and false-negative rates across selected groups.
- Logistic-regression coefficient interpretation.
- Contributions to one individual prediction.
- A feature-removal comparison for `foreign_worker`.
- Governance implications and outstanding evidence requirements.

### Dataset and model

The audit used 1,000 records from the historical UCI Statlog German Credit Data dataset. The target was derived as `bad_credit`, where 1 represented bad credit and 0 represented good credit.

An 80/20 stratified train/test split was used, producing 800 training records and 200 test records. Preprocessing was fitted on training data and applied to the held-out test data.

The baseline model used logistic regression. A second model excluded `foreign_worker` while retaining the same test records and model settings.

### Evidence classification

The reported results are evidence about this exploratory demonstration model. They are not operational test evidence, independent validation, or proof of the behavior of LendWise's production system.

## 3. Baseline Performance

| Metric | Result |
|---|---:|
| Accuracy | 77.50% |
| Precision — bad credit | 63.64% |
| Recall — bad credit | 58.33% |
| F1 — bad credit | 60.87% |
| False-positive rate | 14.29% |
| False-negative rate | 41.67% |

The confusion matrix contained 120 true negatives, 20 false positives, 25 false negatives, and 35 true positives.

The results indicate that the baseline model missed 25 of the 60 actual bad-credit cases in the test set. This error profile warrants further assessment of the intended decision context and the relative consequences of different error types.

The results are specific to this test sample and must not be treated as estimates of production performance.

## 4. Fairness and Group-Level Error Analysis

### 4.1 Age groups

The under-25 group had an observed FPR of 20.00%, compared with 13.33% for the group aged 25 and older. The FPR difference was 6.67 percentage points.

The reported Newcombe 95% confidence interval for the difference ranged from −7.29 to +28.83 percentage points. It includes zero and is wide. This analysis does not establish a statistically significant difference under the selected method, nor does it establish fairness or equivalence.

### 4.2 Housing groups

The rent category had the highest observed FPR at 36.36%. The own-housing category had the highest observed FNR at 50.00%.

The group sizes ranged from 22 to 143 test records. Estimates from the smaller groups are uncertain and should be treated as exploratory observations requiring further investigation.

These results raise questions about potential socioeconomic proxy effects and the distribution of errors. They do not establish causation or unlawful discrimination.

### 4.3 Foreign-worker category and feature-removal comparison

For the baseline model, category A201 had an FPR of 14.81% and an FNR of 42.37%. After removing `foreign_worker`, its FPR fell to 11.85%, while its FNR rose to 47.46%.

Category A202 contained only six test records: five actual good-credit cases and one actual bad-credit case. Both models produced zero observed errors for this group. This sample is too small to support a reliable fairness conclusion.

Removing the feature did not eliminate the need to assess correlated proxy information, feature justification, or potential group-level disparities.

## 5. Explainability Findings

The audit examined the coefficients of the fitted logistic-regression model and decomposed one test record's score into the intercept and transformed-feature contributions.

The selected record had an actual label of good credit, a predicted label of good credit, and an estimated bad-credit probability of 19.04%.

The contribution associated with `foreign_worker_A201` pushed the model's log-odds score toward the bad-credit class. Other features pushed the score both upward and downward.

These contributions are model-specific and depend on the preprocessing pipeline. They are not causal effects or direct percentage-point changes in probability. One individual explanation cannot establish overall model fairness or explain every lending outcome.

The association with foreign-worker status warrants review of the feature's purpose, necessity, proportionality, potential proxy effects, and impact on group-level outcomes. It is a review trigger, not proof of discrimination.

## 6. Key Findings

| Existing tracker reference(s) | Finding | Evidence | Governance implication |
|---|---|---|---|
| F-002, F-006 | Baseline error profile | 25 false negatives among 60 actual bad-credit records | Assess error consequences and appropriate operating thresholds; investigate group-level disparities. |
| F-002, F-006 | Age-group uncertainty | Observed FPR difference with a wide confidence interval | Do not draw definitive fairness conclusions from the current sample. |
| F-001, F-006 | Housing-group disparities | Different observed FPR and FNR across housing categories | Investigate feature justification and potential socioeconomic proxy effects. |
| F-001 | Foreign-worker feature justification | Foreign-worker status contributes to one examined prediction | Document feature necessity, proportionality, and applicable legal review. |
| F-001, F-002 | Feature-removal trade-off | FPR fell while FNR rose for A201 after feature removal | Feature removal alone is not a sufficient mitigation strategy. |
| F-005, F-006 | Limited subgroup evidence | A202 contains six test records | Obtain appropriately supported validation evidence before drawing conclusions. |
| F-003, F-005 | Methodology limitations | Historical dataset and preprocessing choices require further review | Validate label reliability, representativeness, feature semantics, and preprocessing design. |
| F-004, F-008, F-011 | Production evidence gap | Exploratory results do not validate the deployed LendWise system | Require verified controls, independent validation, and authorized risk approval before production approval. |

**Reference note:** Tracker IDs above refer to the existing enterprise remediation tracker. They are cross-references for audit reporting, not new findings or changes to tracker status. Confirm each mapping against the tracker before final approval. No remediation is considered closed solely because it is documented in this report.
## 7. Recommendations and Remediation

### Priority 1 — Before any production approval

1. Document the intended purpose and justification for each material input feature.
2. Conduct a structured proxy-variable assessment, including foreign-worker status, age, housing, and financial circumstances.
3. Define a defensible fairness evaluation plan, including relevant groups, error metrics, sample-size requirements, uncertainty, and decision criteria.
4. Independently validate data quality, representativeness, label reliability, model performance, and preprocessing.
5. Validate the actual LendWise system using appropriate evidence rather than relying on this public-dataset demonstration.
6. Verify implementation and operational effectiveness of human oversight, reviewer authority, escalation, evidence access, audit logging, and monitoring controls.
7. Document residual-risk decisions and obtain authorized independent review and sign-off.

### Priority 2 — Before ongoing operation

1. Establish performance and fairness monitoring with documented thresholds and escalation.
2. Define reassessment triggers for data, model, feature, threshold, and intended-purpose changes.
3. Maintain reviewer training, competency evidence, and procedures for challenging or overriding model outputs.
4. Establish version control, evidence retention, and periodic governance review.

These recommendations identify required work; they do not imply that the controls have already been implemented.

## 8. Limitations

- The dataset is historical and geographically limited.
- The test set contains only 200 records.
- Some groups are too small to support reliable conclusions.
- The audit does not validate LendWise's actual production model.
- Coefficients and individual contributions do not establish causation.
- Removing one feature does not prove that proxy information has been eliminated.
- The reported analysis does not establish legal compliance, production readiness, or an absence of discrimination.

## 9. Governance Decision

**Decision: Not Approved — Remediation Required.**

The exploratory audit identifies unresolved questions about model errors, feature justification, potential proxy effects, fairness evidence, explainability, and independent validation.

This decision should not be interpreted as a finding that LendWise's production system has been independently tested and found defective. Rather, the available evidence is insufficient to support production approval.

AI-001 must remain unapproved for production until the required controls and evidence have been implemented, independently assessed, and reviewed by authorized decision-makers.

## 10. Closure Criteria

The audit should not be closed solely because this report has been written. Closure requires:

- Documented feature justification and proxy assessment.
- A defensible fairness evaluation with appropriate uncertainty analysis.
- Independent validation of the relevant system and data.
- Verified evidence of implemented and tested controls.
- Documented residual-risk decisions and authorized approval.
- Traceable evidence linked to the relevant remediation findings.

**Report owner:** AI Governance  
**Status:** Draft — For Governance Review  
**Final approval:** Pending authorized review and required remediation evidence.
