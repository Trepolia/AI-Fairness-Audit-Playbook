# Fairness Audit Playbook: Bias Source Identification Tool (Phase 3)

## 1. Project Overview

| Field                         | Value                                                 |
| ----------------------------- | ----------------------------------------------------- |
| **Project Name/System Title** | [Enter Name]                                          |
| **Project Domain**            | [Enter Application Domain, e.g., Lending, Healthcare] |
| **Project Phase**             | Phase 3: Bias Source Identification                   |
| **Date of Assessment**        | [Enter Date]                                          |
| **Assessor(s)**               | [Enter Names]                                         |

## 2. Assessment Context & Scope

| Field                   | Value                                                                                                                                                                                     |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Assessment Trigger**  | [Describe the specific condition, e.g., "Completion of Fairness Definition Selection (Phase 2); requirement to map selected metrics to specific lifecycle stages for targeted detection"] |
| **Foundational Inputs** | [Reference prioritized risks from HCAT (Phase 1) and selected Definitions (Phase 2) to guide investigation]                                                                               |
| **Lifecycle Scope**     | [Specify stages under review, e.g., Data Collection, Feature Engineering, Model Architecture, Deployment Feedback Loops]                                                                  |

## 3. Bias Detection Team

| Role                           | Name/Role                                     | Responsibilities/Notes                                               |
| ------------------------------ | --------------------------------------------- | -------------------------------------------------------------------- |
| **Technical Lead**             | [Name/Role, e.g., Data Scientist/ML Engineer] | Responsible for quantitative detection techniques                    |
| **Domain Expert**              | [Name/Role]                                   | Required to identify proxy variables and measurement biases          |
| **Social Scientist/Historian** | [Name/Role]                                   | Verifies whether technical patterns align with historical inequities |

---

## 4. Bias Detection Team
Establishing a cross-functional team ensures a sociotechnical evaluation that accounts for both technical patterns and societal context.

| Role                 | Name/Personnel | Responsibilities                                                                                  |
| :------------------- | :------------- | :------------------------------------------------------------------------------------------------ |
| **Technical Lead**   | [Name/Role]    | Responsible for implementing quantitative detection techniques across the ML pipeline.            |
| **Domain Expert**    | [Name/Role]    | Required to identify proxy variables and specific measurement biases within the application area. |
| **Social Scientist** | [Name/Role]    | Verifies whether technical patterns align with historical inequities documented in Phase 1.       |

## 5. Bias Type Taxonomy & Initial Findings
Identify which bias types are relevant to the system based on the following taxonomic indicators.

| Bias Type               | Definition & Indicators                                                                           | Evidence/Findings |
| :---------------------- | :------------------------------------------------------------------------------------------------ | :---------------- |
| **Historical Bias**     | Bias from pre-existing social inequities (e.g., target variables reflecting past discrimination). | [Enter Evidence]  |
| **Representation Bias** | Bias in sampling/measurement (e.g., demographic imbalances vs. target population).                | [Enter Evidence]  |
| **Measurement Bias**    | Bias in how attributes are proxied or operationalized (e.g., inconsistent label quality).         | [Enter Evidence]  |
| **Aggregation Bias**    | Bias from combining distinct populations with different feature-outcome relationships.            | [Enter Evidence]  |
| **Learning Bias**       | Bias from modeling choices (e.g., regularization penalizing minority patterns).                   | [Enter Evidence]  |
| **Evaluation Bias**     | Bias in testing procedures (e.g., test sets not representing deployment contexts).                | [Enter Evidence]  |
| **Deployment Bias**     | Bias in implementation (e.g., feedback loops amplifying initial disparities).                     | [Enter Evidence]  |

## 5. Detection Methodology (Technical Steps)
For each identified bias, specify the quantitative and qualitative techniques used.

*   **HCAT Alignment:** Extract mechanisms from the HCAT to compare current outcome distributions across high-risk groups.
*   **FDST Alignment:** Analyze model behavior specifically for violations of selected fairness metrics (e.g., False Negative Rate disparities for an "Equal Opportunity" goal).
*   **Intersectional Audit:** Explicitly identify demographic intersections (e.g., race *and* gender) at risk for **Simpson’s Paradox**—where aggregate fairness masks hidden disparities.

## 6. Prioritization Framework
Use the following formula to calculate the **Priority Score** for each identified bias source:
**Score = (Severity × 0.3) + (Scope × 0.2) + (Persistence × 0.2) + (Historical Alignment × 0.2) + (Intervention Feasibility × 0.1)**

| Bias Source | Severity (1-5) | Scope (1-5) | Persistence (1-5) | Historical Alignment (1-5) | Feasibility (1-5) | Priority Score |
| :---------- | :------------- | :---------- | :---------------- | :------------------------- | :---------------- | :------------- |
| [Bias Name] |                |             |                   |                            |                   | [Result]       |

**Priority Categories:**
*   **High Priority (≥ 4.0):** Immediate mitigation required.
*   **Medium Priority (3.0–3.9):** Requires monitoring and mitigation post-launch.
*   **Low Priority (< 3.0):** No immediate action needed.

## 7. Governance & Sign-off
*   **Mitigation Strategy:** [Briefly describe the planned intervention for High Priority items.]
*   **Review Cadence:** [e.g., Quarterly or upon data source changes.]
*   **Technical Lead Sign-off:** __________________________
*   **Compliance Lead Sign-off:** __________________________

---