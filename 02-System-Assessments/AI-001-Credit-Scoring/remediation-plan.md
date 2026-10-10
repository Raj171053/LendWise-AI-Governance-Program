# AI-001 — Credit-Scoring Remediation Plan

**Company:** LendWise Financial Services Ltd.  
**System ID:** AI-001  
**Version:** 0.1 — Initial working plan  
**Linked assessment:** `risk-and-fairness-assessment.md`  
**Current status:** NOT APPROVED — REMEDIATION REQUIRED  
**Evidence basis:** Fictional scenario and synthetic training metrics

---

## 1. Purpose

This remediation plan converts the findings identified in the AI-001 Risk and Fairness Assessment into specific actions, proposed owners, closure evidence and approval gates.

The objective is to ensure that material fairness, data-quality, validation and human-oversight risks are investigated and appropriately addressed before production approval is considered.

All assignments and target timelines below are proposed for the fictional LendWise scenario.

## 2. Remediation Register

| Finding | Priority | Required action | Proposed accountable owner | Target |
|---|---|---|---|---|
| F-001: Proxy-variable risk | High | Review features for potential proxy effects, justify feature necessity and document mitigations | Head of Model Risk | Week 2 |
| F-002: Fairness metrics insufficiently defined | High | Define target, positive class, error-rate formulas, denominators, evaluation population and uncertainty methodology | Model Validation Lead | Week 1 |
| F-003: Label reliability and selection bias uncertain | High | Review label provenance, outcome maturity, rejected-applicant limitations and selection effects | Data Science Lead | Week 2 |
| F-004: Human oversight requirements incomplete | High | Define reviewer authority, override rules, escalation, audit logging and decision workflow | Head of Credit Risk | Week 2 |
| F-005: Data representativeness unverified | Medium — provisional | Analyse coverage, missingness, subgroup representation and data quality | Data Governance Lead | Week 2 |
| F-006: Residual group disparities require investigation | Medium — provisional | Investigate observed disparities using validated metrics and predefined criteria | Fairness Assessment Lead | Week 3 |
| F-007: Automatic rejection or gating unverified | High | Inspect the actual workflow and test that automatic actions cannot bypass the approved human decision process | Credit Platform Engineering Lead | Week 1 |

**Timeline note:** Week numbers are proposed planning targets, not completed work or guaranteed deadlines. Reassess priorities if investigation reveals more severe risks.

## 3. Detailed Actions and Closure Evidence

### F-001 — Proxy-Variable Risk

**Objective:** Determine whether model features act as inappropriate proxies for protected or otherwise sensitive characteristics.

**Actions**
1. Inventory model features and document each feature's business purpose and provenance.
2. Investigate relationships between relevant features and protected or sensitive characteristics where lawful and appropriate.
3. Assess whether each feature is necessary and proportionate for the intended prediction.
4. Evaluate alternative features or model configurations where material proxy risks are identified.
5. Document findings, limitations, mitigations and residual risk.

**Closure evidence**
- Feature inventory and justification.
- Documented proxy analysis and methodology.
- Results of alternative-feature or mitigation testing, where applicable.
- Approved residual-risk decision.

**Exit criterion:** Material proxy risks have been investigated, appropriate mitigations are supported by evidence, and unresolved risks have been escalated to the accountable authority.

### F-002 — Fairness Metric Definitions

**Objective:** Ensure that fairness and error-rate results are interpretable and reproducible.

**Actions**
1. Specify the model target and prediction horizon.
2. Define the positive class.
3. Define false positives and false negatives relative to the target and reference outcomes.
4. Document each metric's denominator and evaluation population.
5. Record subgroup sample sizes, uncertainty estimates and limitations.
6. Establish evaluation criteria before reviewing final results.
7. Recalculate metrics using the approved methodology.

**Closure evidence**
- Approved metric specification.
- Reproducible evaluation methodology.
- Documented data population and subgroup counts.
- Results with uncertainty and limitations.
- Independent review of the methodology.

**Exit criterion:** Metrics can be independently reproduced and interpreted without ambiguity about labels, denominators or evaluation scope.

### F-003 — Label Reliability and Selection Bias

**Objective:** Determine whether historical outcomes provide a reliable basis for evaluating credit risk and fairness.

**Actions**
1. Document the source and construction of each target label.
2. Assess whether repayment/default outcomes are sufficiently mature and reliable.
3. Investigate the effect of previously approved applicants being more likely to have observable repayment outcomes.
4. Identify possible selection bias and historical decision effects.
5. Document the limits of conclusions about applicants without observed outcomes.
6. Obtain independent review of the proposed evaluation approach.

**Closure evidence**
- Label provenance and quality report.
- Selection-bias analysis.
- Documented limitations and assumptions.
- Independently reviewed evaluation methodology.

**Exit criterion:** Label limitations and selection effects are understood, and the evaluation method is justified for the intended use. Unresolved limitations remain visible in the risk decision.

### F-004 — Human Oversight

**Objective:** Establish effective human control over lending decisions.

**Actions**
1. Define the roles and responsibilities of reviewers.
2. Specify the information reviewers receive when evaluating a score.
3. Confirm reviewers can challenge and override model recommendations.
4. Define escalation and second-review conditions.
5. Record reviewer actions, overrides and reasons.
6. Train reviewers on limitations, appropriate use and automation bias.
7. Test the workflow using synthetic scenarios, including incorrect or conflicting recommendations.

**Closure evidence**
- Approved Human Oversight Matrix.
- Documented review and escalation procedure.
- Training records.
- Test results demonstrating meaningful challenge and override capability.
- Sample audit-log evidence using synthetic data.

**Exit criterion:** Oversight is operationally defined and tested, with clear authority and accountability.

### F-005 — Data Representativeness

**Objective:** Assess whether data quality and population coverage are adequate for the intended use.

**Actions**
1. Document source systems, collection periods, markets and applicant populations
