# Fairness Audit Playbook: Historical Context Assessment Tool(Part 1)

## Project Overview

| Field                           | Value                                                                 |
|---------------------------------|-----------------------------------------------------------------------|
| **Project Name/System Title**   | [Enter Name, e.g., "CreditSwift" Automated Loan Approval]             |
| **Project Domain**              | [Enter Application Domain, e.g., Lending, Hiring, Healthcare, Criminal Justice] |
| **Project Phase**               | Phase 1: Historical Context Assessment (Sprint 1)                     |
| **Date of Assessment**          | [Enter Date]                                                          |
| **Last Revision Date**          | [Enter Date]                                                          |

## Assessment Context & Scope

| Field                       | Value                                                                                                         |
|-----------------------------|---------------------------------------------------------------------------------------------------------------|
| **Assessment Trigger**      | [Describe the specific event, e.g., "New AI project scoping for automated decision system," "Post-incident bias review," or "Compliance requirement for high-risk AI under the EU AI Act"] |
| **Deployment Region(s)**    | [List jurisdictions, e.g., European Union, USA, Global]                                                      |
| **Primary System Objective**| [State what the system is trying to achieve and who the intended beneficiaries are]                            |

## Decision-Making Team

| Role                            | Name/Role                                       | Responsibilities/Notes                                         |
|----------------------------------|-------------------------------------------------|----------------------------------------------------------------|
| **Lead Assessor**               | [Name/Role, e.g., Senior AI Governance Specialist]         |                                                                |
| **Domain Expert(s)**            | [Name/Role, e.g., Historical Lending Compliance Officer, Sociologist] |                                                                |
| **Technical Lead**              | [Name/Role, e.g., ML Engineer, Data Scientist]              |                                                                |
| **Stakeholder Representative(s)**| [Name/Role, e.g., Legal Counsel, Community Advocate, or User Representative] |                           |

## Regulatory & Ethical Parameters

| Parameter                      | Value                                                                                |
|--------------------------------|-------------------------------------------------------------------------------------|
| **Applicable Legal Frameworks**| [Identify mandatory standards, e.g., GDPR, EU AI Act, ECOA, Title VII]              |
| **Identified Protected Attributes** | [List attributes requiring protection in this domain, e.g., Race, Gender, Age, Disability Status] |
| **Primary Ethical Lens**       | [Select the guiding framework, e.g., Rawlsian Justice, Egalitarianism, or Virtue Ethics] |

---

## 1. Domain & Historical Research

| #   | Required Artifact     | Audit Question                                                               | Response           |
| :-- | :-------------------- | :--------------------------------------------------------------------------- | :----------------- |
| 1.1 | Domain Identification | What specific domain (e.g., lending) is this for?                            | [Your Answer Here] |
| 1.2 | Metric Critique       | Does our "success" metric (e.g., "predicting arrest") embed historical bias? | [Your Answer Here] |
| 1.3 | Historical Inventory  | What documented practices (e.g., redlining) have marginalized groups here?   | [Your Answer Here] |
| 1.4 | Continuity Analysis   | How have previous systems in this domain reinforced hierarchies?             | [Your Answer Here] |

**Notes/Supporting Evidence:** [Add any additional notes, sources, or evidence here]

---

## 2. Data & Representation Audit

| #   | Required Artifact         | Audit Question                                                                     | Response           |
| :-- | :------------------------ | :--------------------------------------------------------------------------------- | :----------------- |
| 2.1 | Provenance Log            | What social/political contexts shaped the collection of this data?                 | [Your Answer Here] |
| 2.2 | Categorical Analysis      | Are categories (e.g., race, credit) treated as objective vs. socially constructed? | [Your Answer Here] |
| 2.3 | Statistical Proxy Report  | Which features (e.g., Zip code) correlate with protected attributes?               | [Your Answer Here] |
| 2.4 | Variance Report           | How do dataset demographics compare to real-world benchmarks?                      | [Your Answer Here] |
| 2.5 | Representation Gap Report | Are there gaps where information is sparse due to historical neglect?              | [Your Answer Here] |

**Notes/Supporting Evidence:** [Add any additional notes, sources, or evidence here]

---

## 3. Technical Mechanism & Pipeline Audit

| #   | Required Artifact     | Audit Question                                                        | Response           |
| :-- | :-------------------- | :-------------------------------------------------------------------- | :----------------- |
| 3.1 | Mechanism Report      | Through what path (label bias, noise) might history manifest in code? | [Your Answer Here] |
| 3.2 | Vulnerability Map     | Which pipeline components are most vulnerable to these patterns?      | [Your Answer Here] |
| 3.3 | Encoding Log          | How are social categories encoded, and what nuances are lost?         | [Your Answer Here] |
| 3.4 | Feedback Loop Diagram | Does the prediction influence future "Ground Truth" data?             | [Your Answer Here] |
| 3.5 | Intersectional Audit  | Does the data identify unique risks at demographic intersections?     | [Your Answer Here] |

**Notes/Supporting Evidence:** [Add any additional notes, sources, or evidence here]

---

## 4. Multi-Framework Analysis
Evaluate the project through these three lenses:

1. **Consequentialist:** Impact on the many (total outcome).
   - [Your Analysis Here]

2. **Deontological:** Rule-based fairness (adherence to rights).
   - [Your Analysis Here]

3. **Virtue Ethics:** Alignment with company/societal values.
   - [Your Analysis Here]

### The Rationale Log

| #   | Audit Question                                                              | Response           |
| :-- | :-------------------------------------------------------------------------- | :----------------- |
| 4.1 | Which framework aligns with our primary stakeholders?                       | [Your Answer Here] |
| 4.2 | If Frameworks A and B suggest different paths, which did we choose and why? | [Your Answer Here] |
| 4.3 | What data shift would require us to re-evaluate these trade-offs?           | [Your Answer Here] |

**Notes/Supporting Evidence:** [Add any additional notes, sources, or evidence here]

---

## 5. Risk Classification Matrix

Use the following matrix to classify identified risks. Refer to the component guide for scoring guidelines.

| Historical Pattern | Severity (1-3) | Likelihood (1-3) | Relevance (1-3) | Priority Score | Notes     |
| :----------------- | :------------: | :--------------: | :-------------: | :------------: | :-------- |
| [Pattern 1]        |    [Score]     |     [Score]      |     [Score]     |    [Total]     | [Details] |
| [Pattern 2]        |    [Score]     |     [Score]      |     [Score]     |    [Total]     | [Details] |
| [Pattern 3]        |    [Score]     |     [Score]      |     [Score]     |    [Total]     | [Details] |

**Priority Levels:**
- 7-9: Critical priority - Requires immediate mitigation
- 5-6: High priority - Requires mitigation if launch is successful
- 3-4: Medium priority - Requires monitoring after launch
- 1-2: Low priority - No action needed

---

## 6. Recommendations & Next Steps

**Key Findings:** [Summarize the most important insights from this assessment]

**Recommended Actions:** [List specific mitigation strategies or next steps]

**Integration with Next Component:** [How will this inform the Fairness Definition Selection Tool?]

**Sign-off:**
- Assessor: ___________________________ Date: _______________
- Reviewer: ___________________________ Date: _______________

---

*This template is based on the Historical Context Assessment Tool (HCAT) from the AI Fairness Audit Playbook. For detailed guidance, refer to the component documentation.*
