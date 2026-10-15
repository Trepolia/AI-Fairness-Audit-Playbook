# Fairness Audit Playbook: Historical Context Assessment Template (HCAT)

## Project Overview

| Field | Value |
|---|---|
| **Project Name/System Title** | [Enter project or system title] |
| **Project Domain** | [Enter domain: Lending, Hiring, Healthcare, etc.] |
| **Project Phase** | Phase 1: Historical Context Assessment |
| **Date of Assessment** | [Enter date] |
| **Last Revision Date** | [Enter date] |

## Assessment Context & Scope

| Field | Value |
|---|---|
| **Assessment Trigger** | [e.g., New AI project scoping, Post-incident bias review, Compliance requirement] |
| **Deployment Region(s)** | [List jurisdictions, e.g., EU, USA, Global] |
| **Primary System Objective** | [State objective and intended beneficiaries] |

## Decision-Making Team

| Role | Name / Role | Responsibilities |
|---|---|---|
| **Lead Assessor** | [Anonymized — Lead Assessor] | Lead the assessment and compile findings |
| **Domain Expert(s)** | [Anonymized — Domain Expert] | Provide domain context and historical knowledge |
| **Technical Lead** | [Anonymized — Technical Lead] | Execute quantitative analyses and reproduce results |
| **Stakeholder Representative(s)** | [Anonymized — Stakeholder Rep] | Provide stakeholder perspectives |

## Regulatory & Ethical Parameters

| Parameter | Value |
|---|---|
| **Applicable Legal Frameworks** | [e.g., GDPR, EU AI Act, ECOA, Title VII] |
| **Identified Protected Attributes** | [List attributes: Race, Gender, Age, Disability, etc.] |
| **Primary Ethical Lens** | [Select guiding framework: Consequentialist, Deontological, Virtue Ethics] |

---

## 1. Domain & Historical Research

| # | Required Artifact | Audit Question | Response |
|---|---:|---|---|
| 1.1 | Domain Identification | What specific domain is this for? | [Your answer] |
| 1.2 | Metric Critique | Does our success metric embed historical bias? | [Your answer] |
| 1.3 | Historical Inventory | What documented practices have marginalized groups here? | [Your answer] |
| 1.4 | Continuity Analysis | How have previous systems reinforced hierarchies? | [Your answer] |

**Notes / Evidence:** [Add sources and notes]

---

## 2. Data & Representation Audit

| # | Required Artifact | Audit Question | Response |
|---|---:|---|---|
| 2.1 | Provenance Log | What contexts shaped data collection? | [Your answer] |
| 2.2 | Categorical Analysis | Are categories treated as objective or socially constructed? | [Your answer] |
| 2.3 | Statistical Proxy Report | Which features correlate with protected attributes? | [Your answer] |
| 2.4 | Variance Report | How do dataset demographics compare to benchmarks? | [Your answer] |
| 2.5 | Representation Gap Report | Are there gaps due to historical neglect? | [Your answer] |

---

## 3. Technical Mechanism & Pipeline Audit

| # | Required Artifact | Audit Question | Response |
|---|---:|---|---|
| 3.1 | Mechanism Report | Through what path might history manifest in code? | [Your answer] |
| 3.2 | Vulnerability Map | Which pipeline components are most vulnerable? | [Your answer] |
| 3.3 | Encoding Log | How are social categories encoded and what nuances are lost? | [Your answer] |
| 3.4 | Feedback Loop Diagram | Does the prediction influence future ground-truth data? | [Your answer] |
| 3.5 | Intersectional Audit | Does the data identify risks at demographic intersections? | [Your answer] |

---

## 4. Multi-Framework Analysis

1. **Consequentialist:** [Your analysis]
2. **Deontological:** [Your analysis]
3. **Virtue Ethics:** [Your analysis]

**Rationale Log**

| # | Audit Question | Response |
|---|---|---|
| 4.1 | Which framework aligns with stakeholders? | [Your answer] |
| 4.2 | If frameworks conflict, which did we choose and why? | [Your answer] |
| 4.3 | What data shift would require re-evaluation? | [Your answer] |

---

## 5. Risk Classification Matrix

| Historical Pattern | Severity (1-3) | Likelihood (1-3) | Relevance (1-3) | Priority Score | Notes |
|---|---:|---:|---:|---:|---|
| [Pattern 1] | [ ] | [ ] | [ ] | [ ] | [Details] |
| [Pattern 2] | [ ] | [ ] | [ ] | [ ] | [Details] |
| [Pattern 3] | [ ] | [ ] | [ ] | [ ] | [Details] |

Priority levels:
- 7–9: Critical — immediate mitigation
- 5–6: High — mitigation required if launching
- 3–4: Medium — monitor post-launch
- 1–2: Low — no action required

---

## 6. Recommendations & Next Steps

**Key Findings:** [Summarize insights]

**Recommended Actions:** [List mitigation strategies]

**Integration with Next Component:** How this informs FDST

**Sign-off:**
- Assessor: [Anonymized] Date: __/__/____
- Reviewer: [Anonymized] Date: __/__/____

---

*This template is based on the HCAT component of the AI Fairness Audit Playbook.*
