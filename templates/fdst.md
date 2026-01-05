# Fairness Audit Playbook: Fairness Definition Selection Tool (Phase 2)

## Project Overview

| Field                      | Value                                                    |
|----------------------------|----------------------------------------------------------|
| **Project Name/System Title** | [Enter Name]                                           |
| **Project Domain**            | [Enter Domain, e.g., Lending, Healthcare]              |
| **Project Phase**             | Phase 2: Fairness Definition Selection                 |
| **Date of Assessment**        | [Enter Date]                                           |
| **Assessor(s)**               | [Enter Names]                                          |

## Assessment Context & Scope

| Field                  | Value                                                                                                                             |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| **Assessment Trigger**         | [Describe condition, e.g., "Completion of Historical Context Assessment (Phase 1) and identification of critical risks"] |
| **Primary System Objective**   | [Describe objective and intended beneficiaries]                                                                           |
| **Historical Foundation**      | [Reference specific high-risk pattern(s) identified in Phase 1, e.g., "History of redlining..."]                         |

## Decision-Making Team

| Role                          | Name/Role                  | Responsibilities/Notes                                                        |
|-------------------------------|----------------------------|-------------------------------------------------------------------------------|
| **Lead Assessor**             | [Enter Name/Role]          |                                                                               |
| **Technical Lead/ML Engineer**| [Enter Name/Role]          | Implements mathematical fairness formulations                                  |
| **Legal & Compliance Counsel**| [Enter Name/Role]          | Ensures legal alignment (e.g., Disparate Impact/Treatment standards)           |
| **Ethical/Stakeholder Rep.**  | [Enter Name/Role]          | Represents philosophical priorities (e.g., Egalitarianism, Libertarianism)     |

## Ethical and Legal Parameters

| Parameter                    | Value/Selection                                      |
|------------------------------|-----------------------------------------------------|
| **Primary Ethical Lens**     | [e.g., Egalitarian (outcomes) or Libertarian (process)]         |
| **Mandatory Legal Frameworks**   | [e.g., GDPR, EU AI Act, ECOA]                        |
| **Theory of Discrimination**     | [e.g., Disparate Treatment (intent), Disparate Impact (outcome)] |
| **Protected Attributes for Measurement** | [List from Phase 1]                            |

---

## 1. HCAT Ingestion (Contextual Baseline)

Referencing Historical Context Analysis findings.

- **[Documented Historical Harm:](/templates/hcat.md)** (e.g., "History of gender-based salary disparities in the technology sector.")
- **Identified Proxies:** (e.g., "Years of Experience" may act as a proxy for age/parental leave.)
- **Mandatory Requirement:** (e.g., "Must achieve 0.8 Disparity Ratio for Gender.")

## 2. Metric Selection Logic

Based on the [FDST Decision Tree](/components/fairness-definition-selection.md).

- **Primary Fairness Metric:** [Insert Selected Metric]
- **Formula:** $[Insert LaTeX Math]$
- **Selection Rationale:** (e.g., "We chose Equal Opportunity because the primary risk in this recruitment tool is a False Negative—wrongfully filtering out a qualified candidate from a marginalized group.")

### Secondary/Monitoring Metrics

- **Metric:** Demographic Parity
- **Formula:** $[Insert LaTeX Math]$
- **Purpose:** To be monitored for "Representation Drift" without being a hard constraint on the model.

## 3. The "Impossibility" Disclosure & Trade-offs

Acknowledging the fundamental mathematical constraints.

According to Kleinberg's Impossibility Theorem, we acknowledge that:

Achieving [Primary Metric] while maintaining [Incompatible Metric] is mathematically impossible given the unequal base rates in the training data.

- **Sacrificed Metric:** (e.g., Predictive Parity)
- **Risk Mitigation for Sacrifice:** (e.g., "While we cannot guarantee Predictive Parity, we will provide a 'Human-in-the-Loop' review for all scores within the 0.4–0.6 probability range to ensure consistent meaning.")

## 4. Governance & Sign-off

Establishing accountability.

- **Review Cadence:** Quarterly (Next Review: April 2026)
- **Trigger for Re-selection:** Any change in training data source or a change in local employment law.
- **Lead Architect Sign-off:** __________________________
- **Compliance Lead Sign-off:** __________________________

---

*This template is based on the Fairness Definition Selection Tool (FDST) from the AI Fairness Audit Playbook. For detailed guidance, refer to the component documentation.*
