# AI System Inventory — LendWise Financial Services Ltd.

## 1. Purpose

This directory contains the AI System Inventory for LendWise Financial Services Ltd., a fictional financial-services organisation operating in selected European Union markets and India.

The inventory establishes a documented baseline of AI systems, their intended purposes, affected individuals, data categories, geographic scope, human oversight, autonomous actions, enterprise risk ratings, EU AI Act classifications and governance status.

It is the starting point for subsequent AI risk assessments, impact assessments, control design, assurance activities and governance decisions.

## 2. Scope

The inventory covers the following 11 system entries:

- AI-001 — Credit Scoring
- AI-002 — Customer Support AI
- AI-003 — Fraud Detection
- AI-004 — KYC Document AI
- AI-005 — CV Screening
- AI-006A — Customer Emotion/Vulnerability AI
- AI-006B — Employee Emotion Analysis AI
- AI-007 — Marketing Recommendation AI
- AI-008 — Loan Document Summarisation AI
- AI-009 — Collections Prioritisation AI
- AI-010 — Autonomous Operations Agent

AI-006A and AI-006B are maintained as separate entries because their affected populations, intended uses, potential harms and regulatory considerations differ.

## 3. Inventory Structure

The register uses 19 fields, organised as follows:

| Fields | Purpose |
|---|---|
| A–E | System identity, business function, intended purpose and AI capability |
| F–I | Accountability, provider, provider/deployer role and internal or third-party status |
| J–O | Affected individuals, data categories, geographic scope, human oversight, outputs and autonomous actions |
| P–R | Initial enterprise risk, EU AI Act classification and regulatory rationale |
| S | Current governance status |

The intended purpose and actual capabilities should be documented separately where they differ. Unknown information must not be presented as confirmed fact.

## 4. Risk and Classification Methodology

### Enterprise AI risk

Enterprise risk considers the potential for harm arising from the system's purpose, affected individuals, data, model limitations, autonomy, scale, security exposure and operational consequences.

The inventory uses initial risk ratings such as Medium, High and Critical where supported by the documented training scenario. These ratings are preliminary governance assessments, not statutory EU AI Act categories.

Detailed assessments may revise an initial rating when new evidence becomes available.

### EU AI Act classification

The EU AI Act classification is assessed separately from enterprise risk.

The review considers the system's intended purpose, actual functionality, relevant provisions of Regulation (EU) 2024/1689, applicable Annex III use cases, prohibited practices and relevant exceptions or conditions.

A system must not be labelled high-risk solely because its enterprise risk is high. Similarly, a system with a lower enterprise risk rating may still fall within a statutory high-risk category.

Autonomy or human involvement alone does not determine the legal classification.

### Governance status

Governance status records the current decision or assessment state. It is not a substitute for the enterprise risk rating or legal classification.

A system marked as not approved must not be interpreted as authorised for unrestricted production use. Any restricted testing must follow its documented safeguards and approval conditions.

## 5. Handling Unknown Information

Use `TBD` when evidence is not yet available.

For material unknowns, the governance process should identify:

- The missing information or evidence.
- The person or function accountable for obtaining it.
- The action required to resolve the gap.
- The effect of the uncertainty on risk, classification or deployment.
- The evidence needed before the finding can be closed.

Blank fields should not be used to represent unknown information when the distinction matters to a governance decision.

## 6. Review and Change Management

The inventory should be reviewed when:

- A new AI system is proposed or acquired.
- An intended purpose or affected population changes.
- New data categories or integrations are introduced.
- Autonomous permissions or decision authority expand.
- Material model, provider or deployment changes occur.
- Monitoring, incidents, audits or regulatory developments reveal new risks.

Material changes should trigger reassessment of the affected system rather than automatic reuse of the previous classification.

## 7. Evidence and Limitations

LendWise is a fictional training case. System descriptions, performance figures and group-level metrics are synthetic unless explicitly identified otherwise.

Inventory entries are based on the documented scenario and may contain unresolved assumptions. They do not establish that controls have been implemented, independently tested or found effective.

Legal classifications and obligations must be validated against authoritative sources and the applicable facts before being relied upon in a real deployment.

## 8. Related Artifacts

- `ai-system-register.csv` — the system register.
- `inventory-quality-review.md` — findings and review decisions.
- `../sources/regulatory-source-register.md` — regulatory sources and references.

## 9. Document Status

**Status:** Inventory baseline for the LendWise training programme.

**Next step:** Maintain the register, document remaining evidence gaps, and use it as the input to detailed system-level risk assessments.
