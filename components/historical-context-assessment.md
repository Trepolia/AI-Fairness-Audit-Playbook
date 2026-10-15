# Fairness Audit Playbook – Component 1
# Historical Context Assessment Tool (HCAT)

- [Fairness Audit Playbook – Component 1](#fairness-audit-playbook--component-1)
- [Historical Context Assessment Tool (HCAT)](#historical-context-assessment-tool-hcat)
  - [1. Purpose](#1-purpose)
    - [HCA Team](#hca-team)
    - [Implementation Triggers](#implementation-triggers)
  - [2. Historical Context Assessment Questionnaire](#2-historical-context-assessment-questionnaire)
    - [1. Domain & Historical Research](#1-domain--historical-research)
    - [2. Data & Representation Audit](#2-data--representation-audit)
    - [3. Technical Mechanism & Pipeline Audit](#3-technical-mechanism--pipeline-audit)
    - [4. Multi-Framework Analysis](#4-multi-framework-analysis)
  - [3. Historical Context Risk Classification Matrix](#3-historical-context-risk-classification-matrix)
    - [Matrix Scoring Components](#matrix-scoring-components)
    - [Risk Classification Example](#risk-classification-example)
  - [4. Implementation Guides](#4-implementation-guides)
    - [Quick Start Guide - For Experienced Users](#quick-start-guide---for-experienced-users)
    - [Detailed Walkthrough - For New Teams](#detailed-walkthrough---for-new-teams)

## 1. Purpose

The Historical Context Assessment Tool (HCAT) is a governance framework designed for engineering teams to conduct rigorous historical analysis following scientific fairness best practices. The primary goals are:
* Uncover specific historical patterns of discrimination within a project’s domain.
* Translate qualitative histories into technical risk definitions (e.g., identifying "Zip Code" as a proxy for redlining).
* Prioritize mitigation efforts using a quantitative risk matrix.
* Prevent fairness debt: as technical debt accumulates when choosing quick fixes over robust solutions, fairness debt accumulates when models are built on social data without understanding systemic harms.

### HCA Team
* Technical Teams (Data Scientists & Engineers): Execute the assessment and map findings to features.
* Domain Experts: Provide historical and sociological context regarding industry-specific discrimination.
* Stakeholders: Individuals or groups potentially affected by the system’s outcomes who provide lived-experience input.
* Leadership (AI Governance): Review the risk matrix and provide final sign-off on mitigation strategies.

### Implementation Triggers
The HCAT serves as the first component of the AI Fairness Audit Playbook, ensuring that fairness assessments address root causes rather than symptoms of bias. Typical triggers include:
  1. Lifecycle & Scope Triggers
      * New AI Project Scoping: Initiating any project that automates decisions previously handled by humans or legacy systems.
      * Success Metric Definition: During problem formulation, when defining what constitutes a successful outcome.
  2. High-Risk Domain Triggers
      * Regulated Sectors: Operations in domains with documented systemic bias, including finance (lending/credit), healthcare, hiring, education, and criminal justice.
      * Power Asymmetry: Applications where the technology functions as a gatekeeper for essential resources.
  3. Data & Classification Triggers
      * Social Classifications: Systems relying on categories defined by protected attributes rather than objective measures.
      * Historical Feedback Loops: When models train on data where the ground truth was shaped by prior human decisions.

HCAT must be completed before choosing a mathematical fairness definition (for example, demographic parity or equal opportunity), as the historical analysis informs which definitions are appropriate.

---

## 2. Historical Context Assessment Questionnaire
*To be completed during the scoping cycle.*

### 1. Domain & Historical Research

| # | Audit Question | Required Artifact |
| :-- | :--- | :--- |
| 1.1 | **Application Domain:** What specific domain (e.g., lending) is this for? | Domain Identification |
| 1.2 | **Success Definition:** Does our success metric embed historical bias? | Metric Critique |
| 1.3 | **History of Harm:** What documented practices (e.g., redlining) have marginalized groups here? | Historical Inventory |
| 1.4 | **Technological Continuity:** How have previous systems in this domain reinforced hierarchies? | Continuity Analysis |

---

### 2. Data & Representation Audit

| # | Audit Question | Required Artifact |
| :-- | :--- | :--- |
| 2.1 | **Source Context:** What social/political contexts shaped data collection? | Provenance Log |
| 2.2 | **Classification Politics:** Are categories (e.g., race, credit) treated as objective or socially constructed? | Categorical Analysis |
| 2.3 | **Proxy Forensic:** Which features (e.g., zip code) correlate with protected attributes? | Statistical Proxy Report |
| 2.4 | **Demographic Variance:** How do dataset demographics compare to real-world benchmarks? | Variance Report |
| 2.5 | **Data Deserts:** Are there gaps where information is sparse due to historical neglect? | Representation Gap Report |

---

### 3. Technical Mechanism & Pipeline Audit

| # | Audit Question | Required Artifact |
| :-- | :--- | :--- |
| 3.1 | **Mechanism Analysis:** Through what path (label bias, noise) might history manifest in code? | Mechanism Report |
| 3.2 | **Vulnerability Heatmap:** Which pipeline components are most vulnerable to these patterns? | Vulnerability Map |
| 3.3 | **Codification:** How are social categories encoded, and what nuances are lost? | Encoding Log |
| 3.4 | **Feedback Loops:** Does the prediction influence future ground-truth data? | Feedback Loop Diagram |
| 3.5 | **Intersectionality:** Does the data identify unique risks at demographic intersections? | Intersectional Audit |

---

### 4. Multi-Framework Analysis

Evaluate the project through these three lenses:

1. **Consequentialist:** Impact on aggregate outcomes.
2. **Deontological:** Rule-based fairness and rights adherence.
3. **Virtue Ethics:** Alignment with organizational and societal values.

**The Rationale Log**

| # | Audit Question |
| :-- | :--- |
| 4.1 | Which ethical framework aligns with primary stakeholders? |
| 4.2 | If frameworks conflict, which did we choose and why? |
| 4.3 | What data shift would require re-evaluation of these trade-offs? |

---

## 3. Historical Context Risk Classification Matrix

### Matrix Scoring Components
* **Historical Pattern:** Specific documented pattern of discrimination with historical evidence.
* **Severity:** Impact of this bias if perpetuated (High - 3 / Medium - 2 / Low - 1).
* **Likelihood:** Probability of this pattern manifesting in AI systems (High - 3 / Medium - 2 / Low - 1).
* **Relevance:** Applicability to the specific AI system being developed (High - 3 / Medium - 2 / Low - 1).
* **Priority Score:** Calculated as Severity + Likelihood + Relevance.

### Priority Score Interpretation
* 7–9: Critical — immediate mitigation required.
* 5–6: High — mitigation required if launch proceeds.
* 3–4: Medium — monitor post-launch.
* 1–2: Low — no immediate action.

---

## 4. Implementation Guides

### Quick Start Guide — For Experienced Users

**Prerequisites:** Familiarity with AI fairness concepts and access to domain experts.

**Rapid Assessment Checklist:**
- [ ] Scan data for obvious proxy variables and demographic imbalances.
- [ ] Identify domain and review historical harms (focus on 2–3 key patterns).
- [ ] Flag high-risk pipeline components.
- [ ] Score top risks using the priority matrix.
- [ ] Document findings and escalate critical issues.

**Deliverables:** Risk matrix with 3+ identified patterns, priority scores, and mitigation recommendations. Feed results into FDST for metric selection.

### Detailed Walkthrough — For New Teams

**Step 1: Preparation**
- Assemble a cross-functional team (data scientists, domain experts, stakeholders).
- Gather project documentation and data samples.
- Review component overview and success criteria.

**Step 2: Domain Research**
- Research industry-specific discrimination patterns.
- Identify relevant legal cases and regulatory requirements.
- Document historical context and current systemic issues.

**Step 3: Questionnaire Completion**
- Complete Sections 1–3 with evidence and examples.
- Flag information gaps for further research.

**Step 4: Risk Classification**
- Review identified patterns against scoring criteria and calculate priority scores.

**Step 5: Documentation & Integration**
- Compile findings into a structured assessment and prepare an executive summary.
- Feed results into FDST for metric selection.

**Success Checklist:**
- [ ] All questionnaire sections completed with evidence.
- [ ] Risk matrix populated with priority scores.
- [ ] Key findings documented with actionable recommendations.
- [ ] Integration plan for the next assessment phase prepared.

**Common Pitfalls to Avoid:**
- Skipping domain research.
- Treating categories as purely objective.
- Focusing only on technical bias without historical context.
- Not involving diverse stakeholders.

[playbook]: ../ai-fairness-audit-playbook.md
[hcat-template]: /templates/hcat.md
[Fairness Definition Selection Tool]: ./fairness-definition-selection.md
