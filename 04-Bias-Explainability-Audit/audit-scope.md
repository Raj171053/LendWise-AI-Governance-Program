# Project 04 — Bias & Explainability Audit

## 1. Objective
Assess model performance, fairness, explainability and validation evidence for LendWise AI-001 Credit Scoring. Identify evidence gaps and recommend whether the system is ready for governance approval.

## 2. System under review
AI-001 produces a credit-risk score to support human lending decisions for consumers and small businesses in the EU and India. Its production approval status remains **NOT APPROVED — REMEDIATION REQUIRED**.

## 3. Audit approach
Use a public dataset to demonstrate a reproducible model audit. Keep public-dataset results separate from LendWise's previously documented synthetic fairness results and actual system evidence.

## 4. Dataset
Proposed source: UCI Statlog (German Credit Data), https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data

The dataset contains 1,000 records and 20 features, with a good/bad credit-risk target. It is historical and geographically limited. It must not be treated as representative of current EU or Indian applicants.

## 5. Audit questions
- Are target labels and positive-class definitions explicit?
- Are performance metrics appropriate and reproducible?
- Do error rates or outcome rates differ across groups that can be validly assessed?
- Are proxy-variable and feature-necessity risks adequately investigated?
- Are model explanations understandable without being misrepresented as causal proof?
- What independent validation and operational evidence remain missing?

## 6. Limitations and safeguards
Document sample sizes, uncertainty, target and label limitations, group definitions and unavailable demographic attributes. Do not infer protected characteristics without a defensible basis. Do not claim that a public demonstration validates LendWise's production model.

## 7. Governance outcome
The notebook and report will recommend controls and further evidence required. They cannot independently authorize production deployment.

## 8. Existing findings to carry forward
Reuse the existing AI-001 remediation tracker and prior synthetic fairness analysis. Do not recreate previously completed calculations. Reassess a finding only when new evidence or a documented test justifies it.

## 9. Reference
Hofmann, H. (1994). Statlog (German Credit Data). UCI Machine Learning Repository. https://doi.org/10.24432/C5NC77
