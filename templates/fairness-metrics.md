# Fairness Audit Playbook: Fairness Metrics Tool (Phase 4)

## Project Overview

| Field                        | Value                                                      |
|------------------------------|------------------------------------------------------------|
| **Project Name/System Title**| [Enter Name]                                               |
| **Project Domain**           | [Enter Application Domain, e.g., Lending, Healthcare]      |
| **Project Phase**            | Phase 4: Fairness Metrics & Evaluation                     |
| **Date of Assessment**       | [Enter Date]                                               |
| **Assessor(s)**              | [Enter Names]                                              |

## Assessment Context & Scope

| Field                        | Value                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| **Assessment Trigger**       | [Describe the condition, e.g., "Quantitative verification phase; requirement to translate Phase 2 definitions into measurable KPIs and validate results against Phase 3 bias sources"] |
| **Measurement Baseline**     | [List the primary fairness definitions selected in Phase 2 that require statistical calculation, e.g., Equal Opportunity Difference]               |
| **Problem Type**             | [Classification, Regression, or Ranking] (This determines the metric selection logic)                                                              |

## Evaluation & Validation Team

| Role                        | Name/Role                        | Responsibilities/Notes                                                         |
|-----------------------------|-----------------------------------|--------------------------------------------------------------------------------|
| **Lead Auditor**            | [Name/Role]                      | Oversees final fairness reporting and threshold compliance                      |
| **Statistical Specialist**  | [Name/Role]                      | Responsible for confidence intervals, bootstrapping, and Bayesian small-sample handling |
| **Stakeholder Representative** | [Name/Role]                   | Interprets the "Fairness-Performance Trade-off" and approves thresholds         |

## Statistical Parameters

| Parameter                  | Value/Requirement                                                                 |
|----------------------------|-----------------------------------------------------------------------------------|
| **Confidence Level**       | [e.g., 95% Confidence Interval requirement]                                       |
| **Significance Thresholds**| [Identify the p-value or effect size required for an "actionable" disparity, e.g., p < 0.01] |
| **Small Sample Protocol**  | [Define approach for minority subgroups with <100 samples, e.g., Bayesian credible intervals] |

---

Based on the "Fairness Metrics Tool" documentation provided in the sources, the following template documentation is structured to guide auditors through **Fairness Metrics Tool of the Fairness Audit Playbook**.

## 1. Metric Selection Strategy

The documentation requires a rigorous alignment between the technical model output and the ethical goals identified in earlier assessment stages.

- **Problem Type Identification:** Auditors must categorize the model as **Classification** (binary outcomes), **Regression** (continuous numbers), or **Ranking** (ordered lists) to determine the appropriate math.
- **Fairness Definition Alignment:**
    - **Statistical Parity:** Recommended when the goal is **equal representation** to correct for historical exclusion.
    - **Equal Opportunity:** Used to ensure **qualified individuals** from all groups are treated equally, focusing on True Positive Rates.
    - **Predictive Parity:** Necessary when the "meaning" of a score (like a risk assessment) must be consistent across groups.
- **Error Prioritization:** The template requires teams to document which error is more damaging: **False Negatives** (missing qualified people) or **False Positives** (wrongly flagging innocent parties).

## 2. Statistical Validation Protocols

To avoid misleading results caused by data noise, the documentation mandates a specific **Statistical Validation** process.

- **The Bootstrap Protocol:** Auditors must generate **1,000 "virtual" datasets** through resampling with replacement, calculating the mean and **95% Confidence Intervals (CI)** for every metric.
- **Small Sample Protocol (N < 100):** For minority subgroups with insufficient data, the template replaces standard confidence intervals with **Bayesian Credible Intervals** using weakly informative priors. These results must be explicitly labeled as **"Low Confidence"** to prevent over-interpretation.
- **Significance Thresholds:** Teams must define the **p-value or effect size** (e.g., the 80% rule) required to trigger an "actionable" disparity.

## 3. Visualization and Intersectional Analysis

The reporting documentation uses visual tools to translate complex statistical parity into actionable business risks.

- **Fairness Disparity Chart:** A bar chart used to identify metrics falling outside **acceptable thresholds**. It must include **"Whiskers" (CIs)**; narrow whiskers outside the threshold indicate a **statistically significant bias**.
- **Intersectional Heatmap:** This tool is used to identify **compounded disadvantage** at the overlap of demographics (e.g., age + gender).
- **Visual Integrity:** To prevent drawing conclusions from insufficient data, the documentation requires **color gradients** to show disparity magnitude and **cell opacity/grey-out** to represent sample size.

## 4. Final Audit Status & Action Plan

Every evaluation must conclude with a definitive status for each metric to determine the next steps in the deployment lifecycle.

- ✅ **PASS:** The metric is within the threshold and the result is stable. The action is to **document and monitor** the system in production.
- ⚠️ **INCONCLUSIVE:** The metric shows potential bias, but the sample size is too small for certainty. The action is to **collect more data** on that specific subgroup.
- 🚨 **FAIL:** The metric is poor and statistically significant. The action is to **pause deployment** and initiate a mandatory **"Mitigation" phase**.

---

## Understanding Statistical Validation

**Analogy for Understanding Statistical Validation:**

Executing the **Bootstrap** method is like **running a 100-meter dash 1,000 times** instead of once. If a runner consistently finishes at the same time, you have a stable measurement of their speed. If their times vary wildly (a wide confidence interval), you cannot be certain how fast they actually are, and you should be cautious about using that single "raw score" to make a high-stakes decision.

---

*This template is based on the Fairness Metrics Tool from the AI Fairness Audit Playbook. For detailed guidance, refer to the component documentation.*
