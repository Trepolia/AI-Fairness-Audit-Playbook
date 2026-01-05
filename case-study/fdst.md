
# Case Study: Booking.com Hotel Recommendation System

Using the provided HCAT Case Study for the Booking.com Hotel Recommendation System, here is the completed Fairness Selection Memo. This document translates the qualitative historical risks identified in your case study into the formal technical requirements for Component 2.

## 📝 Fairness Selection Memo: Booking.com Recommendation Engine

**Project ID:** BK-HOTEL-2026-001  
**Audit Phase:** Technical Scoping (Component 2)  
**Date:** January 20, 2026  
**Auditor/Lead:** Dr. Maria Rodriguez, AI Ethics Lead

### 1. HCAT Ingestion (Contextual Baseline)

Findings derived from the HCAT Case Study.

- **Documented Historical Harm:** The system operates in a domain with deep-rooted discrimination, specifically geographic redlining and socioeconomic segregation in hospitality. Legacy systems historically used postcode-based pricing tiers that disadvantaged marginalized communities.
- **Identified Proxies:** Postcode is a highly potent proxy for race/ethnicity ($r=0.68$). Additionally, device type and payment method serve as proxies for socioeconomic status.
- **Mandatory Requirement:** Based on the Critical Priority (Score: 9) assigned to geographic discrimination, the audit must mandate representation parity across diverse neighborhoods.

### 2. Metric Selection Logic

Selected via the FDST Decision Tree based on case study impacts.

- **Primary Fairness Metric:** Demographic Parity (Statistical Parity)
- **Formula:** $P(\hat{Y}=1 | A=a) = P(\hat{Y}=1 | A=b)$
- **Selection Rationale:** We selected Demographic Parity because the HCAT revealed systemic exclusion where 70% of bookings originate from Western Europe/North America, while the Global South is significantly underrepresented. This metric is required to counteract historical data deserts and ensure the "easier for everyone to experience the world" value is upheld.

**Secondary/Monitoring Metric:** Equal Opportunity  
**Formula:** $P(\hat{Y}=1 | Y=1, A=a) = P(\hat{Y}=1 | Y=1, A=b)$  
**Purpose:** To ensure that hotels of equal quality in diverse neighborhoods have the same probability of being recommended as those in historically favored areas, addressing the identified vulnerability in recommendation ranking.

### 3. The "Impossibility" Disclosure & Trade-offs

Navigating the tensions identified in the Ethical Analysis.

According to Kleinberg's Impossibility Theorem, we acknowledge that:

Achieving Demographic Parity while maintaining Predictive Parity is mathematically impossible because the "base rates" of historical bookings are vastly unequal (80% of data comes from the top 10% income bracket).

- **Sacrificed Metric:** Predictive Parity (Precision)
- **Risk Mitigation for Sacrifice:** While precision may vary across groups initially, we will prioritize geographic diversity requirements (Immediate Action) to build a more equitable ground-truth dataset for future iterations.

### 4. Thresholds & Performance Buffers

Acceptance criteria for the Booking.com audit.

| Category | Acceptable Range | Case Study Baseline |
|----------|-----------------|---------------------|
| Demographic Parity Ratio | $0.85 - 1.15$ | Currently $< 0.50$ (Global South) |
| Max Revenue (Accuracy) Drop | $< 5.0\%$ | Current gain is 15% |
| Intersectional Delta | $< 12\%$ | Currently not captured |

### 5. Governance & Sign-off

Standardized for Tier 3 Compliance.

- **Review Cadence:** Quarterly
- **Intersectional Monitoring:** Mandatory inclusion of compounded risks (e.g., Black women travelers, disabled LGBTQ+ users) in all future reports.

> [!IMPORTANT]
> **Regulatory Alignment:** This audit record serves as a primary artifact for Article 10 of the EU AI Act, documenting the rationale for metric selection based on historical bias patterns identified in the hospitality domain.

- **AI Ethics Lead Sign-off:** Dr. Maria Rodriguez
- **Technical Lead Sign-off:** James Chen

### Next Step for You

Since your case study identified a 35% performance drop for users in underrepresented regions, would you like me to draft the Bias Detection Report (Component 3) using these specific numbers to show the "Fail" state and the required "Mitigation" steps?

---

# Case Study: Internal Loan Application System

**Scenario:** The engineering team developing an AI-powered internal loan application system has discovered demographic disparities in approval rates and is unsure which fairness definition to prioritize.

## Applying the FDS Tool

### 1. Definition Selection Decision Tree Application

| Step | Assessment | Outcome | Selected Metric(s) |
|------|-----------|---------|-------------------|
| Step 1: Historical Context | Lending and credit decisions have a well-documented history of systematic exclusion (e.g., redlining), leading to structural disadvantages and under-representation of certain groups in lending outcomes. | Yes. Systematic exclusion revealed. | Demographic Parity (Mandatory inclusion for monitoring representation). |
| Step 2: Error-Impact Analysis | In lending, the most significant harm is the False Negative (FN): denying a loan to an applicant who would have repaid. This error causes direct economic harm to qualified applicants and perpetuates exclusion. | FNs are more harmful. | Equal Opportunity (Mandatory definition). |
| Step 3: Outcome Calibration | The system exposes probabilistic credit-risk scores to analysts, who use these scores to make final decisions. | Yes. Probabilistic scores exposed. | Sufficiency (Group-Calibrated Scores) (Mandatory inclusion). |

**Primary Definitions Selected:** Equal Opportunity, Sufficiency, and Demographic Parity (for monitoring).

### 2. Trade-Off Analysis (Internal Loan Application System)

#### Selected Definition Documentation

| Element | Documentation |
|---------|--------------|
| **Primary Fairness Definition Selected** | Equal Opportunity (Equality of True Positive Rates): $P(\hat{Y}=1 \| Y=1, A=a) = P(\hat{Y}=1 \| Y=1, A=b)$ |
| **Selection Rationale** | Connection to historical context: Historical lending discrimination (systemic exclusion) makes it critical to ensure that qualified applicants from historically excluded groups have the same probability of receiving a positive prediction (loan approval) as other qualified applicants. Application requirements: The primary goal is finding individuals who are truly qualified (will repay). Missing qualified candidates (False Negatives) is the most critical error to mitigate for ethical and legal compliance (e.g., under ECOA). Stakeholder priorities: Legal and Risk teams prioritize compliance and ensuring that the model does not disproportionately deny creditworthy individuals. |

#### Trade-off Acknowledgment

| Element | Documentation |
|---------|--------------|
| **Fairness Properties Not Satisfied** | Predictive Parity and Equalized Odds may not be satisfied due to impossibility results. Specifically, because historical inequities lead to differences in base repayment rates (Y=1) across groups, we cannot simultaneously satisfy Equal Opportunity (equal true positive rates) and Predictive Parity (equal positive predictive values). We prioritize Equal Opportunity to ensure access for qualified applicants. |
| **Performance Implications** | Implementing Equal Opportunity may require lowering the approval threshold for one group or raising it for another to achieve equal true positive rates. This may cause a slight increase in the overall False Positive Rate (approving individuals who default), potentially increasing credit risk. Our analysis shows a 2% anticipated increase in default rates for the model to achieve parity on qualified approvals. |

#### Monitoring Approach

| Element | Documentation |
|---------|--------------|
| **Monitoring Strategy** | We will track Equal Opportunity as the primary compliance metric. We will also track Demographic Parity and Predictive Parity as secondary metrics to ensure that overall approval rates and the consistency of risk scores remain within acceptable ranges. Disaggregated False Positive Rates will be reviewed quarterly to monitor the impact on credit risk for specific groups. |
