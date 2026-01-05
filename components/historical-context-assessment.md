# Fairness Audit Playbook – Component 1
# Historical Context Assessment Tool (HCAT)

- [Fairness Audit Playbook – Component 1](#fairness-audit-playbook--component-1)
- [Historical Context Assessment Tool (HCAT)](#historical-context-assessment-tool-hcat)
  - [1. Purpose](#1-purpose)
    - [HCA Team](#hca-team)
    - [Implementation Triggers](#implementation-triggers)
  - [2. Historical Context Assessment Questionnaire](#2-historical-context-assessment-questionnaire)
    - [1. Domain \& Historical Research](#1-domain--historical-research)
    - [2. Data \& Representation Audit](#2-data--representation-audit)
    - [3. Technical Mechanism \& Pipeline Audit](#3-technical-mechanism--pipeline-audit)
    - [4. Multi-Framework Analysis](#4-multi-framework-analysis)
  - [3. Historical Context Risk Classification Matrix](#3-historical-context-risk-classification-matrix)
    - [Matrix Scoring Components](#matrix-scoring-components)
    - [Risk Classification Example](#risk-classification-example)
  - [4. Implementation Guides](#4-implementation-guides)
    - [Quick Start Guide - For Experienced Users](#quick-start-guide---for-experienced-users)
    - [Detailed Walkthrough - For New Teams](#detailed-walkthrough---for-new-teams)

## 1. Purpose

The Historical Context Assessment Tool (HCAT) is a governance framework designed for engineering teams to conduct rigorous historical analysis following scientific fairness best practices. The primary objectives are to:
* Uncover specific historical patterns of discrimination within a project’s domain.
* Translate qualitative histories into technical risk definitions (e.g., identifying "Zip Code" as a proxy for redlining).
* Prioritize mitigation efforts using a quantitative risk matrix.
* Prevent "Fairness Debt": Just as technical debt accumulates when choosing "quick" code over "right" code, fairness debt accumulates when models are built on social data without understanding the systemic biases that created that data.

### HCA Team
* Technical Teams (Data Scientists & Engineers): Responsible for executing the assessment and mapping findings to features.
* Domain Experts: Provide historical and sociological context regarding industry-specific discrimination.
* Stakeholders: Individuals or groups potentially affected by the system’s outcomes who provide "lived experience" input.
* Leadership (Staff Engineers/AI Governance): Review the Risk Matrix and provide final sign-off on the mitigation strategy.

### Implementation Triggers
The HCAT will serve as the first component of the [**AI Fairness Audit Playbook**][playbook], ensuring that fairness assessments address root causes rather than merely symptoms of bias. It must be initiated at specific entry points in the project lifecycle to be effective:
  1. Lifecycle & Scope Triggers
      * New AI Project Scoping: Initiating any project that automates decisions previously handled by human or legacy systems.
      * Success Metric Definition: During the "Problem Formulation" stage, when defining what constitutes a "successful" outcome or an "ideal" candidate.
  2. High-Risk Domain Triggers
      * Regulated Sectors: Operations in domains with documented systemic bias, including Finance (Lending/Credit), Healthcare, Hiring, Education, and Criminal Justice.
      * Power Asymmetry: Applications where the technology functions as a gatekeeper for essential resources or social mobility.
  3. Data & Classification Triggers
      * Social Classifications: Systems relying on categories defined by protected attributes rather than objective physics (e.g., "Creditworthiness," "Risk Profile," or gender/racial proxies).
      * Historical Feedback Loops: When the model trains on data where the "ground truth" was created by previous human biases (e.g., historical loan denial rates).

Before Metric Selection: The HCAT must be completed before choosing a mathematical fairness definition (e.g., choosing between Demographic Parity or Equal Opportunity), as the history dictates which metric is most protective.

---

## 2. Historical Context Assessment Questionnaire
*To be completed during the **Scoping Cycle***.

### 1. Domain & Historical Research

| # | Audit Question | Required Artifact |
| :-- | :--- | :--- |
| 1.1 | **Application Domain:** What specific domain (e.g., lending) is this for? | Domain Identification |
| 1.2 | **Success Definition:** Does our "success" metric (e.g., "predicting arrest") embed historical bias? | Metric Critique |
| 1.3 | **History of Harm:** What documented practices (e.g., redlining) have marginalized groups here? | Historical Inventory |
| 1.4 | **Technological Continuity:** How have previous systems in this domain reinforced hierarchies? | Continuity Analysis |

---

### 2. Data & Representation Audit

| # | Audit Question | Required Artifact |
| :-- | :--- | :--- |
| 2.1 | **Source Context:** What social/political contexts shaped the collection of this data? | Provenance Log |
| 2.2 | **Classification Politics:** Are categories (e.g., race, credit) treated as objective vs. socially constructed? | Categorical Analysis |
| 2.3 | **Proxy Forensic:** Which features (e.g., Zip code) correlate with protected attributes? | Statistical Proxy Report |
| 2.4 | **Demographic Variance:** How do dataset demographics compare to real-world benchmarks? | Variance Report |
| 2.5 | **Data Deserts:** Are there gaps where information is sparse due to historical neglect? | Representation Gap Report |

---

### 3. Technical Mechanism & Pipeline Audit

| # | Audit Question | Required Artifact |
| :-- | :--- | :--- |
| 3.1 | **Mechanism Analysis:** Through what path (label bias, noise) might history manifest in code? | Mechanism Report |
| 3.2 | **Vulnerability Heatmap:** Which pipeline components are most vulnerable to these patterns? | Vulnerability Map |
| 3.3 | **Codification:** How are social categories encoded, and what nuances are lost? | Encoding Log |
| 3.4 | **Feedback Loops:** Does the prediction influence future "Ground Truth" data? | Feedback Loop Diagram |
| 3.5 | **Intersectionality:** Does the data identify unique risks at demographic intersections? | Intersectional Audit |

---

### 4. Multi-Framework Analysis

Evaluate the project through these three lenses:
1. **Consequentialist:** Impact on the many (total outcome).
2. **Deontological:** Rule-based fairness (adherence to rights).
3. **Virtue Ethics:** Alignment with company/societal values.

**The Rationale Log**
| # | Audit Question |
| :-- | :--- |
| 4.1 | **Value Alignment:** Which framework aligns with our primary stakeholders?
| 4.2 | **Conflict Resolution:** If Frameworks A and B suggest different paths, which did we choose and why?
| 4.3 | **Revisit Trigger:** What data shift would require us to re-evaluate these trade-offs?

---

## 3. Historical Context Risk Classification Matrix

### Matrix Scoring Components
* **Historical Pattern:** Specific documented pattern of discrimination with historical evidence.  
* **Severity:** Impact of this bias if perpetuated (High - 3 / Medium - 2 / Low - 1):
   * **High:** Directly impacts fundamental rights or life outcomes.  
   * **Medium:** Creates significant disparities in opportunities or resources.  
   * **Low:** Creates differential experiences but with limited material impact.
* **Likelihood:** Probability of this pattern manifesting in AI systems (High - 3 / Medium - 2 / Low - 1):
    * **High:** Pattern frequently appears in similar systems.  
    * **Medium:** Pattern occasionally appears in similar systems.  
    * **Low:** Pattern rarely appears in similar systems.
* **Relevance:** Applicability to the specific AI system being developed (High - 3 / Medium - 2 / Low - 1):
    * **High:** Direct applicability to system's domain/purpose.
    * **Medium:** Partial applicability to certain system components.
    * **Low:** Limited applicability but potential for manifestation.
* **Priority Score:** Calculated as Severity + Likelihood + Relevance:
    * **7-9: Critical priority** - Requires immediate mitigation.
    * **5-6: High priority** - Requires mitigation if the launch is successful.
    * **3-4: Medium priority** - Requires monitoring after successful launch.
    * **1-2: Low priority** - No action needed.


### Risk Classification Example
| Historical Pattern | Severity | Likelihood | Relevance | Priority Score |
| :--- | :---: | :---: | :---: | :--- |
| **Redlining practices** (Lending) | 3 | 3 | 3 | **9 (Critical)** |
| **Gender bias** (Professional Eval) | 3 | 2 | 2 | **7 (High)** |
| **Racial disparities** (Medical Diag) | 3 | 2 | 1 | **6 (Medium)** |
| **Age discrimination** (Advertising) | 2 | 3 | 1 | **6 (Medium)** |
| **Linguistic bias** (NLP/LLM) | 2 | 2 | 1 | **5 (Medium)** |
| **Religious discrimination** (Social) | 2 | 1 | 1 | **4 (Low)** |

---

## 4. Implementation Guides

### Quick Start Guide - For Experienced Users

**Prerequisites:** Familiarity with AI fairness concepts and access to domain experts.

**Rapid Assessment Checklist:**
- [ ] **Step 2:** Scan data for obvious proxy variables and demographic imbalances
- [ ] **Step 1:** Identify domain and review historical harms (focus on 2-3 key patterns)
- [ ] **Step 3:** Flag high-risk pipeline components
- [ ] **Step 4:** Score top 3 risks using priority matrix
- [ ] **Step 5:** Document findings and escalate critical issues.

**Key Decision Points:**
- If historical patterns are obvious → Proceed to risk scoring
- If domain is unfamiliar → Switch to Detailed Walkthrough
- If high-priority risks found → Immediate mitigation planning

**Deliverables:** [Risk matrix](#3-historical-context-risk-classification-matrix) with 3+ identified patterns, priority scores, and mitigation recommendations. Use Documentation [hcat-template]
**Crucial:** Feed these results into the [**Fairness Definition Selection**][Fairness Definition Selection Tool] process (Component 2).

### Detailed Walkthrough - For New Teams

**Step-by-Step Process:**

**Step 1: Preparation**
- Assemble cross-functional team (data scientists, domain experts, stakeholders)
- Gather project documentation and data samples
- Review component overview and success criteria

**Step 2: Domain Research**
- Research industry-specific discrimination patterns
- Identify relevant legal cases and regulatory requirements
- Document historical context and current systemic issues
- Note stakeholder groups and potential impact areas

**Step 3: [Questionnaire](#2-historical-context-assessment-questionnaire) Completion**
- Work through each section systematically:
  - Section 1: Domain & Historical Research (5 min)
  - Section 2: Data & Representation Audit (7 min)
  - Section 3: Technical Mechanism & Pipeline Audit (8 min)
- Document specific examples and evidence for each question
- Flag information gaps requiring further research

**Step 4: [Risk Classification](#3-historical-context-risk-classification-matrix)**
- Review identified patterns against scoring criteria
- Calculate priority scores for each risk
- Categorize risks by priority level
- Identify immediate mitigation needs

**Step 5: Documentation & Integration**
- Compile findings into structured assessment
- Prepare executive summary with key recommendations using [hcat]
- **Crucial:** Feed these results into the [**Fairness Definition Selection**][Fairness Definition Selection Tool] process (Component 2).

**Success Checklist:**
- [ ] All questionnaire sections completed with evidence
- [ ] Risk matrix populated with priority scores
- [ ] Key findings documented with actionable recommendations
- [ ] Integration plan for next assessment phase prepared

**Common Pitfalls to Avoid:**
- Skipping domain research (leads to incomplete analysis)
- Treating categories as objective (misses social construction)
- Focusing only on technical bias (ignores systemic context)
- Not involving diverse stakeholders (limits perspective)

[playbook]: ../ai-fairness-audit-playbook.md
[hcat-template]: /templates/hcat.md
[Fairness Definition Selection Tool]: ./fairness-definition-selection.md