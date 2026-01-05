# Model Card: [Model Name]
**Version:** 1.0  
**Date:** YYYY-MM-DD  
**Owner:** [Team Name / Lead Engineer]  
**Status:** [Draft / Under Review / Approved]

---

## 1. Model Details
* **Model Type:** (e.g., Logistic Regression, Transformer, XGBoost)
* **Intended Use:** (e.g., "Predicting customer churn to offer discounts")
* **Out-of-Scope Use:** (e.g., "This model should NOT be used to determine credit worthiness")
* **Training Data Source:** [Link to Dataset]

---

## 2. Fairness Analysis (From Playbook Phase 3 & 4)
*Document the results of your fairness audit here.*

### **A. Chosen Fairness Definition**
* **Metric Used:** (e.g., Equal Opportunity / False Positive Rate Parity)
* **Reasoning:** (e.g., "This is an allocative system where we want to ensure all qualified users have equal access to the benefit.")

### **B. Quantitative Results (Disparity Table)**
| Group (Sensitive Attribute) | Metric Value (e.g., TPR) | Disparity vs. Baseline |
| :--- | :--- | :--- |
| **Reference Group** (e.g., Group A) | 0.85 | 1.0 (Baseline) |
| **Subgroup 1** (e.g., Group B) | 0.82 | 0.96 |
| **Subgroup 2** (e.g., Group C) | 0.79 | 0.92 |

**Analysis:** (e.g., "Group C is seeing a 6% lower success rate. This falls in our 'Yellow' zone and required the following mitigation...")

---

## 3. Bias Source Identification (From Playbook Phase 2)
*Where did potential bias originate?*
* **Historical Bias:** [Describe if found]
* **Representation Bias:** (e.g., "We found that users over age 65 were under-represented by 40% in the training set.")

---

## 4. Mitigation & Interventions
*What did you do to fix the disparities found?*
* [ ] Re-weighting the training data
* [ ] Changing the decision threshold
* [ ] Collecting more diverse data
* [ ] None (Justification required)

---

## 5. Technical Limitations & Risks
* **Data Gaps:** (e.g., "Model was not tested on users from the APAC region.")
* **Environmental Impact:** (Estimated carbon footprint of training if applicable).
* **Potential Bottlenecks:** (e.g., "Model latency increases when checking fairness constraints.")

---

## 6. Sign-off
* **Engineering Lead:** ____________________
* **Fairness Staff Engineer (if applicable):** ____________________