# LendWise AI-001 — AI Impact Assessment

**Document status:** Initial working draft  
**System:** AI-001 Credit Scoring System  
**Assessment scope:** EU and India; consumers and small-business applicants  
**Assessment owner:** Head of Credit Risk (proposed; confirmation required)  
**Approval status:** Not Approved — Remediation Required

## 1. Purpose

This assessment identifies people who may be affected by LendWise AI-001, examines potential harms arising from its use in credit-scoring decisions, and establishes the safeguards and evidence required before approval.

## 2. System overview

AI-001 uses predictive modelling to generate a credit-risk score that supports lending assessments. A human decision-maker is intended to review the score before making the final lending decision.

The model's precise input fields, data provenance, review criteria, override arrangements, and any automated rejection or eligibility-gating mechanisms remain to be verified.

## 3. Assessment approach

The assessment will consider:

- Affected individuals and groups
- Potential benefits and harms
- Likelihood, severity and duration of harm
- Fairness, privacy, transparency and human oversight
- Existing controls and remaining gaps
- Mitigations, accountable owners and closure evidence
- Residual risk and approval conditions

**Evidence rule:** Distinguish documented facts from assumptions, proposed controls, synthetic examples and operational evidence. Do not treat a proposed control as implemented unless evidence supports that conclusion.

## 4. Affected Stakeholders and Potential Harms

### 4.1 Stakeholder register

| Stakeholder group | Potential impact | Key concern |
|---|---|---|
| Individual consumer applicants | May receive an inaccurate score or an unfair lending outcome | Discrimination, financial exclusion and inadequate explanations |
| Applicants from potentially disadvantaged groups | May experience systematically different approval rates or error rates | Group-level disparities and proxy-variable effects |
| Small-business applicants | May receive an inaccurate assessment of lending risk | Distinguish legal-entity applicants from natural persons and verify the model's intended scope |
| Credit decision-makers | May rely excessively on AI-generated scores | Automation bias, inadequate challenge and ineffective overrides |
| Credit Risk and Compliance teams | May lack sufficient evidence to validate or monitor the system | Incomplete validation, unclear accountability and weak auditability |
| LendWise | May face customer complaints, regulatory scrutiny and reputational harm | Inadequate governance, documentation and risk controls |

### 4.2 Potential-harm register

| ID | Potential harm | How it could arise | Existing evidence or limitation | Initial priority |
|---|---|---|---|---|
| H-01 | Unfair credit exclusion | Model scores or decision processes may disadvantage certain applicant groups | Synthetic results previously showed an approval-rate disparity; real-world impact is unverified | High |
| H-02 | Incorrect credit assessment | Inaccurate, incomplete or unrepresentative data may produce unreliable scores | Data quality, label reliability and representativeness require further evidence | High |
| H-03 | Proxy discrimination | Variables such as postcode or transaction patterns may indirectly encode sensitive social or economic differences | Proxy-variable assessment remains unresolved | High |
| H-04 | Inadequate human review | Reviewers may accept AI scores without meaningful scrutiny or may lack effective override authority | Human-oversight controls and operational evidence remain incomplete | High |
| H-05 | Insufficient explanation or contestability | Applicants may not receive an understandable explanation or an effective route to challenge an outcome | Explanation, communication and escalation arrangements require verification | Medium — provisional |
| H-06 | Privacy or data misuse | Excessive, inaccurate or improperly handled personal data may be used in scoring | Exact input fields, provenance, retention and applicable safeguards require confirmation | Medium — provisional |
| H-07 | Delayed detection of harm | Monitoring may fail to detect changing performance or emerging group disparities | Monitoring and change-triggered reassessment are not yet evidenced | High |

### 4.3 Assessment limitations

This register identifies plausible harms; it does not establish that every harm has occurred. Prior fairness figures are synthetic training data, not evidence of actual customer outcomes.

Priorities are preliminary and must be reviewed as evidence becomes available. A medium priority does not imply that a legal obligation is optional or that a potential harm is acceptable.

### 4.4 Initial conclusion

AI-001 could materially affect applicants' access to credit and financial opportunities. The combination of unresolved proxy-variable analysis, data-quality questions, fairness validation gaps and incomplete human-oversight evidence means that approval should remain withheld.

The next assessment stage will evaluate each harm's severity, likelihood, affected population, duration and reversibility, then map proportionate mitigations and evidence requirements.
