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
