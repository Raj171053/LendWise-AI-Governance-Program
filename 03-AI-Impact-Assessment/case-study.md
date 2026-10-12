# Case Study: AI Impact Assessment for LendWise Credit Scoring

## Project overview

**Organisation:** LendWise Financial Services Ltd.  
**System:** AI-001 — Credit Scoring System  
**Frameworks considered:** EU AI Act, applicable data-protection requirements, and AI risk-management practices  
**Assessment status:** Initial assessment completed as a draft  
**Recommendation:** Not Approved — Remediation Required

## Business problem

LendWise uses a predictive model to generate credit-risk scores that support lending assessments for consumers and small businesses. Although a human decision-maker is intended to make the final lending decision, unresolved fairness, data-quality and oversight questions create material governance concerns.

## Assessment performed

The assessment identified affected stakeholder groups, documented potential harms, assigned preliminary severity and likelihood ratings, mapped proposed mitigations to existing remediation findings, and considered privacy rights, alternative approaches, proportionality, consultation and approval conditions.

## Key risks identified

- Unfair credit exclusion and potentially unequal group outcomes.
- Inaccurate assessments caused by unreliable or unrepresentative data.
- Proxy-variable effects that may contribute to indirect discrimination.
- Human reviewers relying excessively on AI-generated scores.
- Inadequate explanations, contestability and individual-rights processes.
- Privacy risks and insufficient monitoring of emerging harms.

## Governance approach

The assessment links potential harms to proposed controls, accountable functions and evidence requirements. It distinguishes control design from implementation, operational testing, effectiveness and independent closure review.

A standalone `DSAR_for_AI.md` procedure was also drafted to describe request handling, individual-rights workflows, escalation and assurance requirements.

## Outcome

The initial assessment recommends withholding production approval until material risks are addressed, required controls are implemented and tested, and the evidence receives appropriate independent review.

## Limitations

This is a synthetic portfolio case study. The assessment does not establish that the identified harms occurred in production, that proposed safeguards are operational, or that LendWise complies with applicable law. Quantitative fairness examples used elsewhere in the project are synthetic and must not be represented as actual customer results.

## Lessons learned

An AI impact assessment must connect affected people and potential harms to concrete safeguards, evidence, accountable owners and approval decisions. Completing documentation is necessary, but it does not substitute for implementation, validation or independent review.
