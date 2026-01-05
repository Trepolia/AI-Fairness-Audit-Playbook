# Fairness Audit Playbook – Component 3
# Bias Source Identification Tool

- [Fairness Audit Playbook – Component 3](#fairness-audit-playbook--component-3)
- [Bias Source Identification Tool](#bias-source-identification-tool)
  - [1. Purpose](#1-purpose)
  - [2. Bias Detection Team](#2-bias-detection-team)
  - [3. Implementation Triggers](#3-implementation-triggers)
  - [4. Framework Overview](#4-framework-overview)
  - [5. Bias Type Taxonomy](#5-bias-type-taxonomy)
    - [**Historical Bias**](#historical-bias)
    - [**Representation Bias**](#representation-bias)
    - [**Measurement Bias**](#measurement-bias)
    - [**Aggregation Bias**](#aggregation-bias)
    - [**Learning Bias**](#learning-bias)
    - [**Evaluation Bias**](#evaluation-bias)
    - [**Deployment Bias**](#deployment-bias)
    - [**Intersectional Bias**](#intersectional-bias)
  - [6. Detection Methodology](#6-detection-methodology)
    - [**Detecting Historical Bias**](#detecting-historical-bias)
    - [**Detecting Representation Bias**](#detecting-representation-bias)
    - [**Detecting Measurement Bias**](#detecting-measurement-bias)
    - [**Detecting Learning Bias**](#detecting-learning-bias)
    - [**Detecting Evaluation Bias**](#detecting-evaluation-bias)
    - [**Detecting Deployment Bias**](#detecting-deployment-bias)
    - [**Detecting Intersectional Bias**](#detecting-intersectional-bias)
    - [**Detection Integration Process**](#detection-integration-process)
  - [7. Prioritization Framework](#7-prioritization-framework)
    - [**Assessment Dimensions**](#assessment-dimensions)
    - [**Priority Calculation**](#priority-calculation)
    - [**Priority Categories**](#priority-categories)


## 1. Purpose
The **Bias Source Identification Tool (BSIT)** serves as a methodical framework for locating potential bias entry points throughout the entire machine learning (ML) lifecycle. Its primary goal is to transform bias identification from an ad hoc process into a systematic approach, ensuring that fairness assessments address **root causes** rather than merely symptoms of unfairness. By mapping where and how bias enters the system—from data collection and algorithm design to deployment and feedback loops—the tool enables practitioners to implement **targeted mitigation strategies** tailored to specific mechanisms.

## 2. Bias Detection Team
To ensure a sociotechnical evaluation that accounts for both technical patterns and societal context, the following cross-functional roles are required for the assessment:
- **Technical Lead**: Typically a **Data Scientist or ML Engineer** responsible for implementing and executing quantitative detection techniques across the ML pipeline. 
- **Domain Expert**: Provides necessary context to identify **proxy variables** and measurement biases that may be specific to the application area (e.g., lending, healthcare).
- **Social Scientist / Historian**: Verifies whether identified technical patterns align with **historical inequities** and longstanding patterns of discrimination documented in Phase 1.

## 3. Implementation Triggers
The Bias Source Identification Tool is activated by specific conditions within the Fairness Audit Playbook workflow to ensure continuity between assessment phases:

-   **Completion of Phase 2 (Fairness Definition Selection):** Once appropriate fairness definitions and metrics have been selected, the BSIT is triggered to map those metrics to specific lifecycle stages for targeted detection.
-   **Identification of Critical Risks in HCAT:** When the Historical Context Assessment Tool (Phase 1) identifies high-priority historical patterns, the BSIT is implemented to trace how those patterns might be **technically instantiated** through current data or algorithms.
-   **Lifecycle Scope Expansion:** The tool is triggered whenever there is a requirement to review specific stages under suspicion of bias, such as **Feature Engineering, Model Architecture, or Deployment Feedback Loops**.
-   **Data or Lifecycle Changes:** Any significant change in training data sources or system implementation serves as a trigger to re-evaluate potential bias entry points.

---

## 4. Framework Overview

The Bias Source Identification Tool consists of three integrated components:

1. **Bias Type Taxonomy**: Categorizes different types of bias.
2. **Detection Methodology**: Provides techniques to identify each bias type.
3. **Prioritization Framework**: Guides teams in deciding which issues to address first.

## 5. Bias Type Taxonomy

### **Historical Bias**

- **Definition:** Bias resulting from pre-existing social inequities, regardless of sampling or feature selection.
- **Indicators:**
    - Target variables reflecting historical discrimination.
    - Problematic correlations that mirror societal inequities.
    - Patterns that align with known historical discrimination.
- **Example:** A hiring algorithm trained on historical hiring decisions may perpetuate patterns of gender discrimination in technical roles.

### **Representation Bias**

- **Definition:** Bias arising from how populations are sampled and measured in training data.
- **Indicators:**
    - Demographic imbalances compared to target population
    - Quality disparities across demographic groups
    - Systematic measurement differences
- **Example:** A medical diagnostic system trained primarily on data from young adult males may perform poorly for elderly female patients.

### **Measurement Bias**

- **Definition:** Bias arising from how attributes are measured, proxied, or operationalized.
- **Indicators:**
    - Different measurement approaches across groups
    - Proxy variables with varying accuracy across populations
    - Inconsistent label quality across demographics
- **Example:** Using standardized test scores as a proxy for aptitude may disadvantage groups with less access to test preparation resources.

### **Aggregation Bias**

- **Definition:** Bias arising from combining distinct populations that may have different relationships between features and outcomes.
- **Indicators:**
    - One-size-fits-all models for heterogeneous populations
    - Features with different predictive relationships across groups
    - Unexplained performance disparities across subgroups
- **Example:** A credit scoring model might not account for different cultural approaches to credit usage, creating disparities across ethnic groups.

### **Learning Bias**

- **Definition:** Bias arising from modeling choices that amplify or create disparities.
- **Indicators:**
    - Algorithms that overfit majority patterns
    - Regularization approaches that penalize minority patterns
    - Optimization objectives misaligned with fairness goals
- **Example:** A complex model might learn spurious correlations between protected attributes and outcomes that don't represent causal relationships.

### **Evaluation Bias**

- **Definition:** Bias arising from testing procedures that don't represent real-world performance or fairness.
- **Indicators:**
    - Test datasets with different characteristics than deployment contexts
    - Metrics that don't capture relevant fairness dimensions
    - Insufficient disaggregation of performance across groups
- **Example:** Evaluating a facial recognition system on a test set that doesn't include diverse skin tones will mask potential performance disparities in deployment.

### **Deployment Bias**

- **Definition:** Bias arising from how systems are implemented and used in practice.
- **Indicators:**
    - Context shifts between training and deployment
    - User interactions that reinforce biases
    - Feedback loops that amplify initial disparities
- **Example:** A recommendation system might create filter bubbles that limit exposure diversity based on initial demographic patterns.

### **Intersectional Bias**

- **Definition:** Bias that manifests uniquely at the intersection of multiple identity dimensions (e.g., race, gender, and age), creating distinct patterns of disadvantage that single-attribute analyses fail to detect.
- **Indicators:**
    - Simpson's Paradox: Trends that appear fair in aggregate or across individual attributes (e.g., gender alone) but reverse or reveal significant disparities for specific subgroups (e.g., Black women).
    - Fairness Gerrymandering: Scenarios where a model satisfies fairness constraints for high-level groups but continues to discriminate against intersectional subgroups.
- **Example:** A facial recognition system achieving high accuracy for "women" and "people of color" generally, but exhibiting a 34.4% error rate disparity specifically for darker-skinned women.

## 6. Detection Methodology

### **Detecting Historical Bias**

- **Using [Historical Context Assessment Tool (HCAT)](/components/historical-context-assessment.md):**
  - Extract documented discrimination patterns from the [Historical Context Assessment results](/templates/hcat.md).
  - Identify specific historical mechanisms relevant to your application domain.
  - Reference the historical pattern risk classification to prioritize investigation.
- **Quantitative Techniques:**
  - Compare outcome distributions across groups identified as high-risk in the Historical Context Assessment.
  - Analyze correlations between system predictions and historical patterns documented in the assessment.
  - Test whether current data distributions match historically documented disparities.

### **Detecting Representation Bias**

- **Using [Historical Context Assessment Tool (HCAT)](/components/historical-context-assessment.md):**
    - Reference demographic groups identified as historically underrepresented in your domain.
    - Use historical documentation to establish appropriate population benchmarks.
    - Identify measurement approaches that have historically varied across groups.
- **Quantitative Techniques:**
    - Compare dataset demographics to population benchmarks established from historical context.
    - Analyze missing data patterns for correlation with protected attributes.
    - Assess data quality metrics across demographic groups identified in the historical assessment.

### **Detecting Measurement Bias**

- **Using [Fairness Definition Selection Tool (FDST)](/components/fairness-definition-selection.md):**
    - Reference the [selected fairness definitions](/templates/fdst.md) to identify which measurement biases are most relevant.
    - For individual fairness definitions, focus on detecting inconsistent proxies across similar individuals.
    - For group fairness definitions, prioritize detecting systematic measurement differences across groups.
- **Quantitative Techniques:**
    - Test proxy variables for differential accuracy across groups based on your selected fairness criteria.
    - Analyze feature distributions to detect encoding schemes that create disparities.
    - Measure label consistency across annotators for different demographic groups.

### **Detecting Learning Bias**

- **Using [Fairness Definition Selection Tool (FDST)](/components/fairness-definition-selection.md):**
    - Analyze model behavior specifically for violations of your [selected fairness definitions](/templates/fdst.md).
    - For equal opportunity definitions, focus on false negative rate disparities.
    - For demographic parity definitions, examine overall prediction rate differences.
- **Quantitative Techniques:**
    - Measure model performance across groups according to your selected fairness metrics.
    - Test regularization effects on minority group performance.
    - Analyze model behavior against fairness constraints documented in your definition selection.
  
### **Detecting Evaluation Bias**

- **Using [Fairness Definition Selection Tool (FDST)](/components/fairness-definition-selection.md):**
    - Verify that the evaluation framework includes disaggregated performance analysis across all demographic groups and intersections identified as high-risk in the HCAT.
    - Assess whether the selected metrics capture the specific fairness dimensions (e.g., equal opportunity vs. demographic parity) mandated by the FDST.
    - Confirm that statistical significance thresholds are established to distinguish genuine disparities from random variation in test results.
- **Quantitative Techniques:**
    - Perform Coverage Assessment to ensure the test dataset reflects the diversity and characteristics of the actual deployment context, rather than just the training distribution.
    - Conduct Slice Analysis to identify hidden performance gaps in specific population subgroups that may be obscured by aggregate accuracy metrics.
    - Calculate Confidence Intervals for all fairness metrics to account for statistical uncertainty, especially for minority groups with smaller sample sizes.

### **Detecting Deployment Bias**

- **Using [Historical Context Assessment Tool (HCAT)](/components/historical-context-assessment.md):**
  - Reference documented patterns of institutional trust or technological exclusion to identify groups likely to interact differently with the system.
  - Identify infrastructure constraints (e.g., limited internet connectivity or device disparities) noted in the historical analysis that may impact system accessibility.
- **Quantitative Techniques:**
  - Implement Disparity Growth Rate Analysis post-deployment to track whether fairness metrics are stable or worsening over time through iterative system use.
  - Conduct Distribution Shift Monitoring to detect changes in input data caused by system-influenced user behaviors (e.g., users adapting their behavior to achieve a specific result).
  - Perform Human-AI Interaction Monitoring by tracking "override rates," "abandonment patterns," or "completion times" disaggregated by demographic group to identify trust or usability disparities.
  - Execute Accessibility Audits to verify that interface design choices, such as language support or interaction modalities, do not create systematic barriers for marginalized populations.

### **Detecting Intersectional Bias**

To identify these complex bias sources, the detection process must include the following analytical steps:

- **Subgroup Disaggregation:**
    - Analyze performance across all combinations of protected attributes identified as high-risk in the Historical Context Assessment Tool (HCAT).
    - Implement Multi-dimensional Fairness Metrics, such as Intersectional Demographic Parity or Multi-attribute Error Rate Balance, to examine disparities across all attribute combinations simultaneously.
- **Simpson's Paradox Audit:**
    - Systematically compare single-attribute fairness metrics with their intersectional counterparts to identify cases where aggregate fairness masks subgroup unfairness.
- **Causal Pathway Mapping:**
    - Trace how multiple protected attributes interact to influence features (e.g., how the intersection of gender and race might influence historical access to specific educational or professional opportunities).
- **Feedback Loop Analysis:**
    - Track whether bias amplification effects manifest differently at demographic intersections, as these groups often face distinct patterns of trust and interaction with automated systems.

### **Detection Integration Process**

1. Begin by consulting the Historical Context Assessment results to identify highest-risk bias patterns.
2. Reference your selected fairness definitions to determine which bias types most directly threaten your fairness goals.
3. Prioritize detection efforts on bias types that both align with historical patterns and directly impact your chosen fairness definitions.
4. Document each identified bias source with explicit references to both historical context and fairness definition connections.
5.  Prioritization of Intersections: Because comprehensive analysis of every possible intersection is computationally difficult, the team should prioritize intersections based on:
    1.  Historical Documentation: Intersections with a documented history of unique marginalization in the specific application domain. 
    2.  Sample Size: Groups with enough representation to provide statistically significant results, or critical minority groups that require specialized Bayesian analysis.
    3.  Stakeholder Impact: Input from affected communities regarding which overlapping identities face the highest risk of harm.

## 7. Prioritization Framework

### **Assessment Dimensions**

- **Severity:** Potential harm if the bias source remains unaddressed (1-5 scale).
- **Scope:** Proportion of decisions or individuals affected (1-5 scale).
- **Persistence:** Whether effects compound over time through feedback loops (1-5 scale).
- **Intervention Feasibility:** Relative ease of addressing the bias source (1-5 scale).
- **Historical Alignment:** Connection to historical patterns identified in HCA (1-5 scale).

### **Priority Calculation**

Priority Score = (Severity × 0.3) + (Scope × 0.2) + (Persistence × 0.2) + (Historical Alignment × 0.2) + (Intervention Feasibility × 0.1)

Priority Scale:
- 7–9 (Critical): Requires immediate mitigation before deployment.
- 5–6 (High): Requires mitigation if the launch is successful.
- 3–4 (Medium): Requires monitoring post-launch.

### **Priority Categories**

- **High Priority:** Score ≥ 4.0
- **Medium Priority:** 3.0 ≤ Score < 4.0
- **Low Priority:** Score < 3.0
