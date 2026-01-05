# Historical Context Assessment Tool (HCAT) Case Study: Booking.com Hotel Recommendation System

**Project Name:** AI-Powered Hotel Recommendation Engine

**Date:** January 15, 2026

**Assessor(s):** Dr. Maria Rodriguez, AI Ethics Lead; James Chen, Data Scientist

**Domain:** Hospitality and Travel Industry

---

## 1. Domain & Historical Research

| #   | Required Artifact     | Audit Question                                                               | Response                                                                                                                                                                                                                                                                                                                            |
| :-- | :-------------------- | :--------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1.1 | Domain Identification | What specific domain (e.g., lending) is this for?                            | Hospitality and travel booking platform. The AI system recomments hotels based on user preferences, historical data, and pricing algorithms.                                                                                                                                                                                        |
| 1.2 | Metric Critique       | Does our "success" metric (e.g., "predicting arrest") embed historical bias? | Success is measured by booking conversion rates and user satisfaction scores. Historical analysis reveals that "satisfaction" metrics may reflect privileged user demographics (wealthy travelers) rather than equitable access. The algorithm optimizes for revenue, potentially perpetuating economic segregation in hospitality. |
| 1.3 | Historical Inventory  | What documented practices (e.g., redlining) have marginalized groups here?   | Racial discrimination in hotel accommodations (pre-1960s Jim Crow laws)<br>- Economic redlining in tourism destinations<br>- Gender-based pricing discrimination in hospitality<br>- Disability access barriers in travel infrastructure<br>- Colonial-era exploitation of tourism in developing regions                            |
| 1.4 | Continuity Analysis   | How have previous systems in this domain reinforced hierarchies?             | Legacy booking systems used postcode-based pricing tiers that correlated with socioeconomic status. Early recommendation algorithms favored established hotel chains over independent properties in marginalized communities. GPS-based routing systems historically avoided certain neighborhoods                                                                                                                                                                                                                                                                                                                  |

**Notes/Supporting Evidence:**
- References: "The Negro Motorist Green Book" (1940s travel guide for Black travelers)
- UNWTO reports on tourism inequality
- Studies on algorithmic bias in recommendation systems (e.g., 2023 ACM FAccT conference papers)

---

## 2. Data & Representation Audit


| #   | Required Artifact         | Audit Question                                                                     | Response                                                                                                                                                                                                                                                                     |
| :-- | :------------------------ | :--------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2.1 | Provenance Log            | What social/political contexts shaped the collection of this data?                 | Data collected from 2010-present during period of increasing income inequality and gentrification. User data primarily from Western Europe and North America (70% of bookings). Historical booking patterns reflect post-2008 economic recovery biases toward luxury travel. |
| 2.2 | Categorical Analysis      | Are categories (e.g., race, credit) treated as objective vs. socially constructed? | Hotel "star ratings" and "luxury tiers" are socially constructed categories that correlate with economic status rather than objective quality measures. Geographic categories (neighborhoods, districts) often reflect historical segregation patterns.                      |
| 2.3 | Statistical Proxy Report  | Which features (e.g., Zip code) correlate with protected attributes?               | "- Postcode correlates with race/ethnicity (r=0.68) <br> Device type correlates with socioeconomic status (mobile vs desktop users)<br>Payment method correlates with income level<br>Travel frequency correlates with disposable income"                                    |
| 2.4 | Variance Report | How do dataset demographics compare to real-world benchmarks? | Dataset: 65% European users, 25% North American, 10% other<br>World Tourism Organization benchmarks: 50% Asia-Pacific, 20% Europe, 15% Americas<br>Significant underrepresentation of Global South travelers and lower-income demographics.|
| 2.5 | Representation Gap Report | Are there gaps where information is sparse due to historical neglect?              | - Limited data from African and South Asian markets<br>- Underrepresented LGBTQ+ travel patterns<br>- Sparse disability accommodation data<br>- Missing data from conflict zones and developing regions|

**Notes/Supporting Evidence:**
- Internal data audit revealed 40% of global tourism market underrepresented
- Partner hotel data shows bias toward Western chains
- User demographic analysis shows 80% of training data from top 10% income bracket

---

## 3. Technical Mechanism & Pipeline Audit

| #   | Required Artifact     | Audit Question                                                        | Response                                                                                                                                                                                                                                                                        |
| :-- | :-------------------- | :-------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 3.1 | Mechanism Report      | Through what path (label bias, noise) might history manifest in code? | Label bias: User "satisfaction" labels trained on privileged user feedback. Selection bias: Training data from paid advertising campaigns targeting high-income users. Confirmation bias: Algorithm reinforces existing booking patterns rather than exploring diverse options. |
| 3.2 | Vulnerability Map     | Which pipeline components are most vulnerable to these patterns?      | High Risk: User profiling and recommendation ranking algorithms<br>Medium Risk: Price optimization and availability filtering<br>Low Risk: Basic search and filtering (though still affected by data quality)                                                                   |
| 3.3 | Encoding Log          | How are social categories encoded, and what nuances are lost?         | Geographic locations encoded as coordinate grids lose cultural/historical context. "Budget" vs "luxury" categories erase socioeconomic nuances. Language preferences mask cultural identities. Disability accommodations reduced to binary flags.                               |
| 3.4 | Feedback Loop Diagram | Does the prediction influence future "Ground Truth" data?             | Yes - successful recommendations create more data for those patterns, reinforcing existing biases. Failed recommendations from marginalized users create sparse data, reducing future visibility. Price predictions influence market behavior.                                  |
| 3.5 | Intersectional Audit  | Does the data identify unique risks at demographic intersections?     | Limited intersectional analysis. System fails to capture compounded disadvantages: Black women travelers, disabled LGBTQ+ users, low-income families from developing regions. Current features treat attributes independently.                                                                                                                                                                                                                                                              |
**Notes/Supporting Evidence:**
- Algorithm audit revealed 35% performance drop for users from underrepresented regions
- A/B testing showed 22% lower booking rates for recommended hotels in diverse neighborhoods
- Feedback analysis showed systematic rating differences by user demographics

---

## 4. Ethical Analysis & Trade-offs

### Multi-Framework Analysis
Evaluate the project through these three lenses:

1. **Consequentialist:** Impact on the many (total outcome).
   - The system increases overall booking volume by 15%, benefiting the travel industry broadly. However, it reduces access for 30% of potential users from marginalized groups, creating net negative social impact.

2. **Deontological:** Rule-based fairness (adherence to rights).
   - Violates principles of equal access and non-discrimination. The system creates barriers based on historical disadvantages rather than merit, contravening human rights frameworks.

3. **Virtue Ethics:** Alignment with company/societal values.
   - Conflicts with Booking.com's stated values of "making it easier for everyone to experience the world." The system perpetuates rather than challenges historical inequities.

### The Rationale Log

| #   | Audit Question                                                                                       | Response           |
| :-- | :--------------------------------------------------------------------------------------------------- | :----------------- |
| 4.1 | Which framework aligns with our primary stakeholders?                           | [Your Answer Here] |
| 4.2 | If Frameworks A and B suggest different paths, which did we choose and why? | [Your Answer Here] |
| 4.3 | What data shift would require us to re-evaluate these trade-offs?               | [Your Answer Here] |

**Notes/Supporting Evidence:**
- Stakeholder interviews revealed tension between business metrics and ethical concerns
- Legal review identified potential GDPR/Article 7 violations
- User research showed 45% of affected users would switch platforms if alternatives existed

---

## 5. Risk Classification Matrix

Use the following matrix to classify identified risks. Refer to the component guide for scoring guidelines.

| Historical Pattern                           | Severity (1-3) | Likelihood (1-3) | Relevance (1-3) | Priority Score | Notes                                          |
| :------------------------------------------- | :------------: | :--------------: | :-------------: | :------------: | :--------------------------------------------- |
| Geographic discrimination in recommendations |       3        |        3         |        3        |       9        | Critical - Direct impact on access to services |
| Economic bias in pricing algorithms          |       3        |        3         |        2        |       8        | High - Affects affordability and market access |
| Underrepresentation of Global South users    |       2        |        3         |        3        |       8        | High - Market expansion risk                   |
| Intersectional disadvantages                 |       3        |        2         |        2        |       7        | High - Compounded harm effects                 |
| Disability access barriers                   |       2        |        2         |        2        |       6        | Medium - Legal compliance risk                 |
| Cultural representation gaps                 |       2        |        2         |        1        |       5        | Medium - Brand reputation impact |

**Priority Levels:**
- 7-9: Critical priority - Requires immediate mitigation
- 5-6: High priority - Requires mitigation if launch is successful
- 3-4: Medium priority - Requires monitoring after launch
- 1-2: Low priority - No action needed

---

## 6. Recommendations & Next Steps

**Key Findings:**
The Booking.com recommendation system perpetuates historical patterns of discrimination in the hospitality industry, particularly affecting travelers from marginalized economic, geographic, and social groups. The primary risks are geographic bias in recommendations (priority 9) and economic discrimination in pricing (priority 8).

**Recommended Actions:**
1. **Immediate (Week 1-2):** Implement geographic diversity requirements in recommendation algorithms
2. **Short-term (Month 1-3):** Develop inclusive data collection strategies for underrepresented regions
3. **Medium-term (Month 3-6):** Audit and recalibrate pricing algorithms for economic fairness
4. **Long-term (Month 6+):** Build intersectional fairness metrics and monitoring systems

**Integration with Next Component:**
The HCAT findings strongly indicate need for Demographic Parity as primary fairness definition, with Equal Opportunity as secondary metric. Geographic and economic patterns identified here will inform bias source identification in the next phase.

**Sign-off:**
- Assessor: Dr. Maria Rodriguez  Date: January 20, 2026
- Reviewer: Sarah Johnson  Date: January 20, 2026

---

*This case study demonstrates application of the Historical Context Assessment Tool (HCAT) to a real-world AI system in the travel industry. For detailed guidance, refer to the component documentation.*
