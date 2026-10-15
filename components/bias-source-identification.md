# Fairness Audit Playbook – Component 3
# Bias Source Identification Tool (BSIT)

- [Fairness Audit Playbook – Component 3](#fairness-audit-playbook--component-3)
- [Bias Source Identification Tool](#bias-source-identification-tool)
  - [1. Purpose](#1-purpose)
  - [2. Bias Detection Team](#2-bias-detection-team)
  - [3. Implementation Triggers](#3-implementation-triggers)
  - [4. Framework Overview](#4-framework-overview)
  - [5. Bias Type Taxonomy](#5-bias-type-taxonomy)
    - [Historical Bias](#historical-bias)
    - [Representation Bias](#representation-bias)
    - [Measurement Bias](#measurement-bias)
    - [Aggregation Bias](#aggregation-bias)
    - [Learning Bias](#learning-bias)
    - [Evaluation Bias](#evaluation-bias)
    - [Deployment Bias](#deployment-bias)
    - [Intersectional Bias](#intersectional-bias)
  - [6. Detection Methodology](#6-detection-methodology)
  - [7. Prioritization Framework](#7-prioritization-framework)

## 1. Purpose
The Bias Source Identification Tool (BSIT) is a methodical framework for locating potential bias entry points across the ML lifecycle. Its primary goal is to ensure that fairness definitions selected in FDST map to concrete detection and mitigation activities.

## 2. Bias Detection Team
- **Technical Lead**: Data Scientist or ML Engineer responsible for implementing quantitative detection techniques.
- **Domain Expert**: Identifies proxy variables and measurement biases specific to the application area.
- **Social Scientist / Historian**: Verifies whether technical patterns align with historical inequities.

## 3. Implementation Triggers
Triggers include:
- Completion of FDST (Component 2).
- Identification of critical risks in HCAT (Component 1).
- Lifecycle scope expansion or significant data changes.

---

## 4. Framework Overview
BSIT consists of three integrated components: a bias taxonomy, detection methodologies, and a prioritization framework.

## 5. Bias Type Taxonomy

### Historical Bias
- **Definition:** Bias resulting from pre-existing social inequities.
- **Indicators:** Target variables reflecting historical discrimination; correlations that mirror societal inequities.
- **Example:** A hiring algorithm trained on historical hiring decisions may perpetuate gender discrimination.

### Representation Bias
- **Definition:** Bias from how populations are sampled and measured in training data.
- **Indicators:** Demographic imbalances; quality disparities across groups.
- **Example:** A diagnostic model trained primarily on young adult males may underperform for elderly female patients.

### Measurement Bias
- **Definition:** Bias from how attributes are measured or proxied.
- **Indicators:** Proxy variables with varying accuracy across populations; inconsistent label quality.
- **Example:** Standardized test scores used as a proxy for aptitude may disadvantage groups with less access to test preparation.

### Aggregation Bias
- **Definition:** Bias from combining distinct populations that have different feature–outcome relationships.
- **Indicators:** One-size-fits-all models for heterogeneous populations.

### Learning Bias
- **Definition:** Bias from modeling choices that amplify disparities.
- **Indicators:** Algorithms that overfit majority patterns; regularization that penalizes minority patterns.

### Evaluation Bias
- **Definition:** Bias from testing procedures that don't represent deployment contexts.
- **Indicators:** Test datasets lacking diversity; metrics that do not capture fairness dimensions.

### Deployment Bias
- **Definition:** Bias arising from how systems are implemented and used in practice.
- **Indicators:** Context shifts, feedback loops, interface design choices that create barriers.

### Intersectional Bias
- **Definition:** Bias that manifests uniquely at the intersection of multiple identity dimensions.
- **Indicators:** Simpson's paradox, fairness gerrymandering where aggregate constraints hide subgroup harms.

## 6. Detection Methodology

- Use HCAT results to identify historically marginalized groups and mechanisms.
- Quantitative techniques: compare outcome distributions, analyze correlations between predictions and historical patterns, and test whether current distributions match documented disparities.
- For small groups, apply Bayesian methods and report credible intervals.

## 7. Prioritization Framework

Assessment dimensions: Severity, Scope, Persistence, Intervention Feasibility, Historical Alignment.

Priority Score = (Severity × 0.3) + (Scope × 0.2) + (Persistence × 0.2) + (Historical Alignment × 0.2) + (Intervention Feasibility × 0.1)

Priority categories:
- Critical: Score ≥ 7
- High: 5–6
- Medium: 3–4
- Low: < 3
