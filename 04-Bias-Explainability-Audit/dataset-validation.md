## Initial structural quality checks

- Dataset dimensions: 1,000 rows and 21 original columns.
- Original target labels: 700 good-credit records and 300 bad-credit records.
- Missing cells: 0, as observed in the initial check.
- Exact duplicate rows: 0, as observed in the initial check.
- Numerical range review: pending.
- Categorical value review: pending.
- Assessment limitation: these checks do not establish label validity, fairness, representativeness or suitability for production lending decisions.

## Numerical and categorical inspection

### Numerical ranges
- Duration: 4–72 months.
- Credit amount: 250–18,424.
- Installment rate: 1–4.
- Residence-since code: 1–4.
- Age: 19–75 years.
- Existing credits: 1–4.
- Dependents: 1–2.

No immediately invalid values were identified from these minimum and maximum summaries. Extreme-value review and codebook verification remain necessary.

### Categorical distributions
Inspected checking account, credit history, purpose, personal status/sex, housing and job. The categories are represented by codes such as A14 and A32. Category meanings must be verified against the dataset documentation before interpretation.

### Governance limitations
Category imbalance is not proof of unfairness. Protected-group analysis, proxy-variable review, target validity and dataset representativeness require separate assessment.

## Feature and target preparation

- Target: `bad_credit`.
- Positive class: 1 = bad credit.
- Negative class: 0 = good credit.
- Features: the 20 original input columns, excluding both `credit_risk` and `bad_credit`.
- Expected feature matrix: 1,000 rows × 20 columns.
- Expected target length: 1,000.
- Leakage safeguard: both original and derived target columns are excluded from model inputs.

This step validates the structure of the prepared inputs; it does not establish model performance or fairness.

## Exploratory age-group error-rate audit

### Method
Compared false-positive and false-negative rates on the held-out test set between applicants under 25 and applicants aged 25 or older. Reported 95% Wilson confidence intervals for each proportion.

### Results

| Group | Test records | FPR (95% CI) | FNR (95% CI) |
|---|---:|---|---|
| 25 and older | 161 | 13.33% (8.38%–20.56%) | 41.46% (27.76%–56.63%) |
| Under 25 | 39 | 20.00% (8.07%–41.60%) | 42.11% (23.14%–63.72%) |

### Preliminary interpretation
The under-25 group has a higher observed false-positive rate, while the false-negative point estimates are similar. The under-25 estimates have wider confidence intervals, reflecting smaller denominators.

### Limitations
This is an exploratory analysis of a historical German dataset using a chosen age threshold. Confidence intervals quantify sampling uncertainty for individual rates; they do not establish fairness, equivalence or causation. Further validation and a direct statistical comparison would be needed before making stronger claims. Results do not establish fairness for LendWise's production system.

## Direct comparison of age-group false-positive rates

**Comparison:** Under 25 minus age 25 and older.

- Under-25 FPR: 20.00% (4/20)
- Age-25-and-older FPR: 13.33% (16/120)
- Observed difference: +6.67 percentage points
- 95% Newcombe confidence interval for the difference: −7.29 to +28.83 percentage points

### Preliminary interpretation
The observed FPR is higher for the under-25 group, but the confidence interval includes zero and is wide. This analysis does not establish a statistically distinguishable difference at the two-sided 5% level. It also does not establish fairness or equivalence.

### Limitations
The comparison is exploratory, uses a historical German credit dataset and an analyst-selected age threshold, and is based on a small under-25 test subgroup. Statistical uncertainty, label validity, group definition and external validity remain relevant limitations. These findings do not validate LendWise's production model.


### Preliminary coefficient interpretation

The logistic-regression baseline assigns positive coefficients to features including installment rate, credit amount, loan duration, the `A124` property category, and the `A11` checking-account category. Negative coefficients include `A14` (no checking account), `A34` (critical credit history or other credits at another institution), and `A153` (housing provided free of charge).

These coefficients describe associations with the model's predicted bad-credit score, conditional on other model inputs. They do not establish causality, justify a lending policy, or independently demonstrate discrimination. The coefficients were estimated after preprocessing and scaling; their magnitudes should not be interpreted as raw-unit effects or directly comparable measures of feature importance.

**Governance concerns:** The use of financial circumstances, property ownership, and housing circumstances warrants documented purpose and proportionality review. Reviewers should investigate whether these features are justified, whether they act as proxies for protected or vulnerable groups, and how their inclusion affects group-level error rates and individual explanations.

**Limitations:** This is an exploratory model trained on the historical UCI German Credit dataset, not LendWise production data. Findings require further validation and cannot establish the performance, fairness, or legal compliance of LendWise's actual system.

### Housing-group error-rate analysis

**Method:** Evaluated the logistic-regression baseline on the existing held-out test set of 200 records. Group-specific confusion matrices were used to calculate false-positive rates (FPR) and false-negative rates (FNR).

**Results:**

- `A151` (rent): 35 records; FPR 36.4% (8/22 actual good-credit cases); FNR 23.1% (3/13 actual bad-credit cases).
- `A152` (own housing): 143 records; FPR 9.5% (10/105 actual good-credit cases); FNR 50.0% (19/38 actual bad-credit cases).
- `A153` (free housing): 22 records; FPR 15.4% (2/13 actual good-credit cases); FNR 33.3% (3/9 actual bad-credit cases).

**Preliminary observation:** Error rates differ across housing categories. The rent category has the highest FPR, while the own-housing category has the highest FNR. These differences warrant further investigation into model behavior, feature justification, and potential socioeconomic proxy effects.

**Limitations:** The test-set groups are small and the estimates are uncertain. These results do not establish statistical significance, causation, unlawful discrimination, or a confirmed production-system defect. The analysis uses a historical public dataset and must not be presented as evidence of LendWise production performance.

**Recommended follow-up:** Examine uncertainty intervals, assess whether housing information is justified for the intended lending purpose, review interactions with other features, and conduct independent validation before any production approval decision.

### Individual prediction explanation — exploratory case

**Method:** Decomposed one held-out logistic-regression prediction into the model intercept and transformed-feature contributions.

**Selected record:** Actual label 0 (good credit); predicted label 0 (good credit); estimated bad-credit probability 19.04%. The model's total log-odds score was approximately −1.4472, calculated from an intercept of −4.3034 and summed feature contributions of +2.8562.

**Largest positive contributions:** Installment rate (+1.0584), `foreign_worker_A201` (+0.7170), loan duration (+0.5054), `other_installment_plans_A141` (+0.4897), and dependents (+0.3598).

**Largest negative contributions:** `savings_account_A64` (−1.0058), `property_A121` (−0.3328), age (−0.1784), `purpose_A49` (−0.1655), and `telephone_A192` (−0.1620).

**Governance observation:** The positive contribution associated with `foreign_worker_A201` warrants review of feature justification, potential proxy effects, group-level performance, and applicable legal requirements. This observation is a review trigger, not evidence of unlawful discrimination.

**Limitations:** This is one explanation for one record from a historical public dataset. Contributions are specific to the fitted model and preprocessing pipeline; they are not causal effects or direct changes in probability. The example does not establish LendWise production behavior, overall fairness, or legal compliance.

**Recommended follow-up:** Verify the category code's meaning against the dataset codebook; evaluate relevant group-level outcomes; assess the necessity and proportionality of the feature; and test a documented alternative model without it before making a governance recommendation.
