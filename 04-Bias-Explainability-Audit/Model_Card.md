# LendWise AI-001 — Credit Scoring Model Card

**Document status:** Draft — For Governance Review  
**System ID:** AI-001  
**Version:** 0.1  
**Assessment type:** Exploratory model audit using a public historical dataset  
**Production approval:** **Not Approved — Remediation Required**

---

## 1. Model Overview

### System purpose

AI-001 is a credit-scoring system intended to generate a risk score that supports lending decisions for consumers and small businesses. Under the LendWise scenario, human reviewers make the final lending decisions.

This audit uses a logistic-regression model trained on a public historical credit dataset as an exploratory demonstration. It does not validate the actual LendWise production model.

### Intended use

The demonstration model is intended for:

- Learning and demonstrating model evaluation and explainability methods.
- Exploring classification errors and potential group-level disparities.
- Identifying questions that a governance reviewer should investigate.
- Demonstrating how model evidence can inform a risk assessment.

### Out-of-scope uses

The demonstration model must not be used to:

- Approve or reject real loan applications.
- Estimate the actual performance of LendWise's production system.
- Establish legal compliance or certify fairness.
- Make claims about current EU or Indian lending populations based on this historical dataset.

## 2. Dataset and Target

**Dataset:** UCI Statlog (German Credit Data)

**Source:** https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data

**Dataset size:** 1,000 records and 20 input features, plus the original target column.

**Original target distribution:**
- Good credit: 700 records.
- Bad credit: 300 records.

**Derived target:** `bad_credit`, where 1 represents the original bad-credit label and 0 represents the original good-credit label.

**Data preparation reported:**
- Missing cells: 0.
- Duplicate rows: 0.
- Training set: 800 records.
- Test set: 200 records.
- Stratified train/test split with `random_state=42`.
- Preprocessing fitted on training data and applied to the held-out test data.

The dataset is historical and geographically limited. Its sample size and feature definitions do not establish representativeness for current lending decisions in the EU or India.

## 3. Model Methodology

**Algorithm:** Logistic regression.

**Preprocessing:** Median imputation for numerical inputs; most-frequent imputation and one-hot encoding for categorical inputs; scaling with `StandardScaler(with_mean=False)`.

**Training configuration:** `max_iter=5000`, `random_state=42`.

**Evaluation approach:** Predictions were evaluated on the same held-out test set.

A convergence warning was reported during an earlier unscaled model fit. A subsequent scaled fit completed with 74 iterations and no reported convergence warning.

**Methodological limitation:** The preprocessing classified columns by data type. Some numerically encoded features may represent categories or ordinal values, so their treatment requires semantic review. The current approach also scales one-hot encoded features. A more rigorous, column-specific preprocessing pipeline should be considered before treating these results as a validated model assessment.

## 4. Baseline Performance

The reported baseline test-set metrics are:

| Metric | Result |
|---|---:|
| Accuracy | 77.50% |
| Precision — bad credit | 63.64% |
| Recall — bad credit | 58.33% |
| F1 — bad credit | 60.87% |
| False-positive rate | 14.29% |
| False-negative rate | 41.67% |

The reported confusion matrix is:

| | Predicted good credit | Predicted bad credit |
|---|---:|---:|
| Actual good credit | 120 | 20 |
| Actual bad credit | 25 | 35 |

Here, a false positive means an actual good-credit record was classified as bad credit. A false negative means an actual bad-credit record was classified as good credit.

These metrics describe the exploratory model on this particular test set. They do not establish expected performance on real LendWise applicants.

## 5. Group-Level Error Analysis

### Age groups

| Group | Test records | FPR | FNR |
|---|---:|---:|---:|
| Age 25 and older | 161 | 13.33% | 41.46% |
| Under age 25 | 39 | 20.00% | 42.11% |

The observed FPR difference was 6.67 percentage points, with a reported Newcombe 95% confidence interval from −7.29 to +28.83 percentage points.

The interval includes zero and is wide. The analysis does not establish a statistically significant difference under this method, nor does it establish equivalence or fairness.

### Housing groups

| Housing category | Test records | FPR | FNR |
|---|---:|---:|---:|
| Rent (`A151`) | 35 | 36.36% | 23.08% |
| Own housing (`A152`) | 143 | 9.52% | 50.00% |
| Free housing (`A153`) | 22 | 15.38% | 33.33% |

The rent group had the highest observed FPR, while the own-housing group had the highest observed FNR. The smaller groups produce uncertain estimates. These observations warrant further investigation but do not establish discrimination or causation.

### Foreign-worker category comparison

The original dataset's `foreign_worker` feature was evaluated using categories `A201` and `A202`.

| Model | Group | Test records | FPR | FNR |
|---|---|---:|---:|---:|
| Baseline | A201 | 194 | 14.81% | 42.37% |
| Baseline | A202 | 6 | 0.00% | 0.00% |
| Without `foreign_worker` | A201 | 194 | 11.85% | 47.46% |
| Without `foreign_worker` | A202 | 6 | 0.00% | 0.00% |

The A202 group contains only six test records, including one actual bad-credit record. Its zero observed error rates cannot support a reliable fairness conclusion.

## 6. Explainability Assessment

The audit examined logistic-regression coefficients and the contribution of transformed features to one individual prediction.

For the selected test record:

- Actual label: good credit (0).
- Predicted label: good credit (0).
- Estimated probability of bad credit: 19.04%.
- Total log-odds score: approximately −1.4472.

The largest positive contributions included installment rate, `foreign_worker_A201`, loan duration, `other_installment_plans_A141`, and dependents.

The largest negative contributions included `savings_account_A64`, `property_A121`, age, `purpose_A49`, and `telephone_A192`.

These are model-specific contributions to the log-odds score. They are not causal effects or direct percentage-point changes in probability. Their interpretation depends on the fitted model and preprocessing pipeline.

The contribution associated with `foreign_worker_A201` is a review trigger for feature justification, potential proxy effects, and group-level outcome analysis. It is not proof of unlawful discrimination.

## 7. Feature-Removal Experiment

A comparison model was trained without `foreign_worker`, using the same train/test split and model settings.

| Metric | Baseline | Without `foreign_worker` |
|---|---:|---:|
| Accuracy | 77.50% | 78.00% |
| Precision — bad credit | 63.64% | 66.67% |
| Recall — bad credit | 58.33% | 53.33% |
| F1 — bad credit | 60.87% | 59.26% |
| FPR | 14.29% | 11.43% |
| FNR | 41.67% | 46.67% |

Removing the feature slightly improved accuracy and precision and reduced FPR, but lowered recall and increased FNR. F1 also declined.

The results demonstrate a trade-off rather than a clear overall improvement. Removing one feature does not establish that correlated proxy information has been eliminated.

## 8. Known Limitations

1. The dataset is historical, geographically limited, and not demonstrated to be representative of current EU or Indian applicants.
2. The test set contains only 200 records, and some groups have very small sample sizes.
3. Group-level estimates have uncertainty; not all comparisons have been assessed using confidence intervals.
4. The audit has not established that the demonstration model represents LendWise's production system.
5. The current preprocessing approach requires further methodological review.
6. The coefficient and local-contribution analyses do not establish causality.
7. The feature-removal experiment does not establish the absence of proxy effects.
8. Independent validation, production-data assessment, and evidence of operational controls have not been established by these experiments.

## 9. Governance Findings and Required Actions

| Area | Required follow-up |
|---|---|
| Feature justification | Document why each material feature is necessary and proportionate for the intended purpose. |
| Proxy risk | Investigate potentially sensitive or socioeconomic proxies, including foreign-worker status, age, housing, and financial circumstances. |
| Fairness | Perform appropriately powered group-level assessments using suitable data and documented uncertainty. |
| Data quality | Validate data provenance, representativeness, label reliability, and feature semantics. |
| Methodology | Review feature encoding, scaling, calibration, and validation design. |
| Explainability | Establish appropriate explanations for reviewers and affected applicants, with documented limitations. |
| Independent validation | Obtain independent model and fairness validation before production approval. |
| Human oversight | Verify reviewer authority, escalation, evidence access, logging, and operational controls. |
| Monitoring | Define ongoing performance, fairness, drift, and change-triggered reassessment requirements. |

## 10. Approval Status

**Decision: Not Approved — Remediation Required.**

The exploratory analysis identifies performance, fairness, feature-justification, and validation questions that require further investigation. It does not demonstrate that the LendWise production system is compliant, fair, or ready for deployment.

Production approval requires appropriate evidence of implemented controls, independent validation, documented residual-risk decisions, and authorized governance sign-off.

---

**Document owner:** AI Governance  
**Review status:** Draft  
**Next review:** After remediation evidence and independent validation become available.
