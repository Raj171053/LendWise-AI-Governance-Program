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

## 5. Impact Severity and Likelihood Assessment

### 5.1 Rating methodology

**Severity**
- **High:** Potential for substantial financial exclusion, discriminatory outcomes, or consequential harm that may be difficult to reverse.
- **Medium:** Meaningful but potentially more limited harm, with a realistic opportunity for correction or remediation.
- **Low:** Limited impact that is generally straightforward to correct.

**Likelihood**
- **High:** Credible exposure supported by identified design weaknesses or recurring evidence.
- **Medium:** Plausible exposure, but important facts or control evidence remain uncertain.
- **Low:** Limited expected exposure supported by adequate evidence of effective safeguards.

These ratings are qualitative. They must not be interpreted as statistically estimated probabilities. Missing evidence must not be treated as proof that a control is ineffective or effective.

### 5.2 Preliminary impact ratings

| Harm ID | Potential harm | Severity | Likelihood | Overall priority | Rationale and uncertainty |
|---|---|---|---|---|---|
| H-01 | Unfair credit exclusion | High | Medium | High | Credit outcomes can materially affect financial opportunities. Synthetic results indicated group disparities, but actual customer-level impact is unverified. |
| H-02 | Incorrect credit assessment | High | Medium | High | Incorrect scores may influence lending outcomes. Data quality, label reliability and representativeness remain unresolved. |
| H-03 | Proxy discrimination | High | Medium | High | Proxy variables could produce unequal outcomes. The proxy-variable assessment has not been completed. |
| H-04 | Inadequate human review | High | Medium | High | Human review is intended, but effective challenge, authority and operational implementation require evidence. |
| H-05 | Insufficient explanation or contestability | Medium | Medium | Medium | Applicants may struggle to understand or challenge outcomes. Current explanation and escalation arrangements need verification. |
| H-06 | Privacy or data misuse | High | Medium | High | Financial and personal data may be involved. Exact fields, data provenance and handling controls remain to be confirmed. |
| H-07 | Delayed detection of harm | High | Medium | High | Without evidenced monitoring and reassessment triggers, emerging disparities or model deterioration may go undetected. |

### 5.3 Interpretation and limitations

The ratings above are initial, precautionary assessments based on the documented scenario and unresolved evidence gaps. They are not the results of a completed quantitative risk model.

The likelihood ratings remain provisional because production exposure, control effectiveness, affected-population size and historical incident data have not been independently verified.

The assessment should be updated when reliable evidence becomes available. Severity and likelihood should also be reconsidered separately for different applicant groups and for consumer versus legal-entity small-business applications.

### 5.4 Risk treatment decision

Until the material uncertainties are resolved, AI-001 must remain **Not Approved — Remediation Required**.

Required next steps include:
1. Complete proxy-variable and data-quality assessments.
2. Validate fairness metrics using defined outcome labels, denominators, sample sizes and reliable reference outcomes.
3. Verify that human reviewers can meaningfully challenge and override scores.
4. Define applicant explanations, complaints and escalation routes.
5. Establish monitoring, incident response and change-triggered reassessment.
6. Document residual risks and obtain an authorised, independent approval decision before production use.

## 6. Mitigation and Evidence Plan

### 6.1 Control mapping

| Harm ID | Required safeguard | Accountable function (proposed) | Evidence required | Related existing finding |
|---|---|---|---|---|
| H-01 — Unfair credit exclusion | Test approval outcomes across relevant groups and investigate unexplained disparities | Head of Credit Risk | Defined fairness metrics, group-level results, sample sizes, investigation records and independent validation | F-001, F-002, F-006 |
| H-02 — Incorrect credit assessment | Validate input quality, target labels, representativeness and model performance | Model Risk / Data Science | Data-quality report, label definition, validation results, limitations and remediation records | F-003, F-005 |
| H-03 — Proxy discrimination | Assess proxy variables, feature necessity and potential indirect discrimination | Model Risk / Fairness Review | Feature-level proxy assessment, rationale for retaining variables, group-level testing and reviewer sign-off | F-001, F-002 |
| H-04 — Inadequate human review | Establish reviewer authority, competency, escalation, evidence access and audit logging | Head of Credit Risk, with Compliance and Technology | Approved oversight procedure, competency records, access-control evidence, escalation tests and audit-log tests | F-004, F-010 |
| H-05 — Insufficient explanation or contestability | Define appropriate explanations, complaints handling and routes to challenge lending outcomes | Credit Operations / Compliance | Approved customer communications, complaint workflow, escalation ownership and sample-case evidence | F-009 |
| H-06 — Privacy or data misuse | Document data sources, lawful processing, data minimisation, access, retention and applicable rights processes | Data Protection / Privacy function | Data-flow documentation, data inventory, privacy assessment, access records and retention rules | Assessment gap; confirm relevant tracker mapping |
| H-07 — Delayed detection of harm | Establish ongoing performance and fairness monitoring, incident handling and reassessment triggers | Model Risk / AI Governance | Monitoring specification, thresholds, alert ownership, incident records and reassessment procedure | F-008, F-009 |

**Ownership note:** Functions listed above are proposed. Confirm named accountable owners and approval authority before treating assignments as operational.

### 6.2 Evidence principles

For each safeguard, distinguish between:

1. **Design evidence:** A policy, procedure, control specification or approved plan exists.
2. **Implementation evidence:** The safeguard is deployed and configured in the relevant environment.
3. **Test evidence:** An appropriately authorised test has been executed, with recorded results and defects.
4. **Effectiveness evidence:** Results show that the safeguard works as intended over a suitable period and scope.
5. **Closure evidence:** The authorised independent reviewer has accepted the evidence and recorded a closure decision.

A drafted procedure or planned test alone does not demonstrate implementation or effectiveness.

### 6.3 Residual-risk treatment

The assessment must record the risk remaining after each safeguard is implemented and validated. Residual risk must not be marked acceptable solely because an action has been assigned or a document has been created.

Any proposed acceptance of material residual risk requires a documented rationale, an authorised decision-maker, applicable legal and regulatory review, and evidence that the decision is within that person's authority. A risk acceptance decision cannot override a legal prohibition or mandatory requirement.

### 6.4 Approval conditions

AI-001 remains **Not Approved — Remediation Required** until the applicable high-priority gaps are resolved, controls are implemented and tested, required evidence is retained, and authorised independent review supports a production decision.

## 7. Privacy and Individual Rights

### 7.1 Scope and legal framework

AI-001 may process personal and financial information to generate credit-risk scores. LendWise must confirm the applicable legal requirements based on the applicant's location, the relevant entity, the processing activity and the law in force at the time.

For EU processing, assess the General Data Protection Regulation (GDPR), including transparency, data minimisation, accuracy, access and rectification rights, applicable erasure rights, and protections relating to solely automated decisions.

For Indian processing, assess the Digital Personal Data Protection Act, 2023, and the Digital Personal Data Protection Rules, 2025, including their applicable commencement provisions. Confirm which provisions are in force before assigning legal deadlines or declaring a control mandatory.

This section is a governance assessment, not a substitute for jurisdiction-specific legal advice.

### 7.2 Rights and request-handling register

| Request or right | AI-001 scenario | Required governance response |
|---|---|---|
| Access to personal data | An applicant asks what personal data LendWise holds or uses for credit scoring | Identify relevant data sources, retrieve the applicant's records, verify identity appropriately, and respond under the applicable legal framework |
| Rectification | An applicant disputes an incorrect income, repayment or credit-history field | Investigate the source, correct inaccurate data where required, propagate corrections to relevant downstream systems, and reassess affected scores where appropriate |
| Erasure | An applicant requests deletion of personal data | Assess the applicable legal basis, retention obligations and exceptions; do not automatically erase or refuse all records |
| Explanation and transparency | An applicant asks how AI contributed to a lending outcome | Provide appropriate information about the processing, the AI's role and relevant decision factors, subject to applicable law and protection of other people's rights |
| Challenge to lending outcome | An applicant disputes an adverse outcome | Provide a defined complaint and review route, identify the responsible decision-maker, and document the review and outcome |
| Automated-decision safeguards | A score influences a decision that may significantly affect an individual | Determine whether the decision is solely automated in practice, including whether human review is meaningful; assess applicable legal restrictions and safeguards |
| Data security and confidentiality | A request or investigation exposes sensitive financial information | Use appropriate identity verification, access controls, secure delivery and audit records without collecting excessive identity information |

### 7.3 Human review and contestability

A human reviewer must not be treated as meaningful oversight merely because a person clicks an approval button. The process should establish that the reviewer can access relevant evidence, understand the score's limitations, challenge the recommendation, override it where justified, record reasons and escalate uncertain or disputed cases.

The current AI-001 documentation describes intended human review, but operational effectiveness remains unverified. This assessment therefore does not conclude that the system satisfies applicable automated-decision requirements.

### 7.4 DSAR-for-AI workflow requirements

The proposed workflow should include:

1. Receive and categorise the request.
2. Verify identity proportionately and securely.
3. Determine the applicable jurisdiction, law and response deadline.
4. Identify relevant systems, data sources, model outputs and decision records.
5. Assess applicable rights, exemptions, retention duties and third-party considerations.
6. Obtain review from Privacy, Legal, Credit Risk or other relevant owners as needed.
7. Respond clearly and securely within the applicable deadline.
8. Record the response, rationale, actions, escalations and any refusal or partial refusal.
9. Correct relevant data or reassess an affected outcome where required.
10. Track completion and investigate recurring issues.

This is a proposed process. It must be implemented, legally reviewed and tested before it is described as operational.

### 7.5 Open questions and evidence gaps

- Which legal entity acts as controller or data fiduciary for each relevant processing activity?
- Which exact personal-data fields and external sources are used by AI-001?
- What notices explain the processing and the AI's role?
- How are access, correction, erasure and challenge requests routed and tracked?
- What retention rules apply to source data, scores, decisions and audit logs?
- Can a correction trigger reassessment of an earlier score or lending outcome?
- How is meaningful human review demonstrated in practice?
- Which legal deadlines and exceptions apply in the EU and India at the relevant time?

### 7.6 Initial conclusion

Privacy and individual-rights safeguards are not yet sufficiently evidenced to support approval of AI-001. LendWise must document the applicable legal framework, implement an auditable request-handling process, validate access and correction workflows, and establish an effective route to challenge AI-influenced lending outcomes.

**Approval status remains: NOT APPROVED — REMEDIATION REQUIRED.**

## 8. Benefits, Alternatives and Proportionality

### 8.1 Intended benefits

AI-001 is intended to generate credit-risk scores that support human lending assessments.

Potential benefits include:
- More consistent assessment of relevant credit information.
- Faster processing of applications.
- Better identification of repayment-risk patterns.
- More structured decision support for credit reviewers.

These are intended benefits, not demonstrated outcomes. LendWise must validate them against a documented baseline before claiming that the system improves decision quality, efficiency or fairness.

### 8.2 Potential adverse effects

The system may also:
- Reproduce biases in historical lending data.
- Use proxy variables that create unjustified disparities.
- Produce inaccurate scores for underrepresented applicants.
- Encourage reviewers to rely excessively on automated recommendations.
- Make it difficult for applicants to understand or challenge outcomes.
- Create operational dependence on a model whose performance may deteriorate over time.

### 8.3 Alternatives to assess

| Alternative | Potential benefit | Limitation or safeguard required |
|---|---|---|
| Human-led assessment without AI scoring | Reduces dependence on the model | May be slower and can still involve inconsistent or biased decisions |
| AI score used only as supplementary information | Limits the model's influence | Requires evidence that reviewers do not treat the score as determinative |
| Restricted pilot with enhanced review | Enables controlled evaluation before wider deployment | Must use authorised testing, defined boundaries and effective monitoring |
| Alternative model or feature set | May reduce unjustified disparities or improve reliability | Requires independent validation; improvement cannot be assumed |
| Do not deploy until material gaps are resolved | Avoids introducing unvalidated AI-related risk | Delays the intended operational benefits |

### 8.4 Proportionality assessment

The use of AI-001 should be proportionate to its intended purpose and the risks to applicants. LendWise must demonstrate that the model provides a defensible benefit, uses necessary and appropriate data, performs adequately for relevant groups, and does not impose unjustified harm.

A less risky alternative should be considered where it can achieve the legitimate objective effectively. Convenience, speed or a higher aggregate accuracy score alone is not sufficient to justify material disparities or ineffective human oversight.

### 8.5 Initial conclusion

The potential benefits of AI-assisted credit assessment remain unverified. Given the unresolved fairness, data-quality and oversight findings, LendWise should not proceed to production deployment at this stage. Alternative approaches and restricted testing may be evaluated only within an authorised governance process.
