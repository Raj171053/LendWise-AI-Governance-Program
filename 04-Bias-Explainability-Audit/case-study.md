# Case Study: Bias and Explainability Audit of LendWise AI-001

## Business Context

LendWise is a fictional financial-services company operating in the EU and India. Its AI-001 credit-scoring system is intended to generate risk scores that support human lending decisions.

The objective of this project was to demonstrate how an AI Governance Manager can examine model performance, investigate potential group-level disparities, assess explainability, and document conditions for responsible deployment.

## Objective

Conduct an exploratory audit of a credit-scoring model to:

- Measure baseline classification performance.
- Compare false-positive and false-negative rates across selected groups.
- Examine model coefficients and an individual prediction.
- Test the effect of removing a potentially sensitive feature.
- Translate technical results into governance findings and remediation recommendations.

## Methodology

A logistic-regression model was trained using the public UCI Statlog German Credit Data dataset, containing 1,000 historical records. The target was encoded as `bad_credit`, with 1 representing bad credit and 0 representing good credit.

The data was divided into 800 training records and 200 held-out test records. The audit included baseline metrics, age-group and housing-group error-rate analysis, an individual prediction explanation, and a comparison model without `foreign_worker`.

## Key Findings

The baseline model achieved 77.5% accuracy, 63.64% precision, 58.33% recall, and 60.87% F1 for the bad-credit class. Its false-positive rate was 14.29% and its false-negative rate was 41.67%.

Observed error rates varied across age and housing categories. The age-group comparison had a wide confidence interval, and some groups had small sample sizes. These findings warranted further investigation but did not establish discrimination.

The individual prediction analysis showed how transformed features contributed to the model's log-odds score. The contribution associated with `foreign_worker` prompted a review of feature justification and potential proxy effects.

Removing `foreign_worker` increased accuracy from 77.5% to 78.0% and reduced FPR from 14.29% to 11.43%, but reduced recall from 58.33% to 53.33% and increased FNR from 41.67% to 46.67%. This demonstrated a trade-off rather than a clear overall improvement.

## Governance Recommendations

The audit recommended documented feature justification, proxy-variable assessment, better-supported fairness evaluation, independent validation, explainability controls, verified human oversight, and ongoing performance and fairness monitoring.

The analysis also emphasized that removing a single feature does not prove that correlated proxy information has been eliminated.

## Outcome and Decision

**Governance decision: Not Approved — Remediation Required.**

The project produced an exploratory model audit, a model-card draft, an audit-report draft, and documented validation findings. The results do not establish the performance, fairness, or legal compliance of LendWise's actual production system.

Production approval remains contingent on appropriate evidence, implemented and tested controls, independent validation, documented residual-risk decisions, and authorized governance sign-off.

## Limitations and Learning

The historical public dataset is not demonstrated to represent current EU or Indian lending populations. The test set and some subgroups are small, and the model is a demonstration rather than a validated LendWise production system.

The main lesson is that model governance requires more than accuracy metrics: it requires careful interpretation, uncertainty awareness, feature justification, traceable evidence, and a clear decision-making process.
