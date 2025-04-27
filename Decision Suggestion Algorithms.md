# 📄 Pattern: Decision Suggestion Algorithms

## Intent
Algorithmically **generate, rank, and suggest actionable choices** for human decision-makers—improving consistency, efficiency, and context-aware optimization while preserving human judgment.

The system aims not to replace decisions, but to **augment decision-making under complexity, uncertainty, or time pressure**.

## Context
In emergency response, education, service allocation, or logistics, human operators must select among many options (e.g., hospitals to route patients, schools for placement). Traditional decision-making is vulnerable to inconsistency, overload, or suboptimal outcomes.

Suggestion algorithms act as **cognitive exoskeletons**, narrowing choices and surfacing ranked recommendations based on contextual data.

## Problem
How can institutions provide decision-makers with **contextualized, optimized, and explainable suggestions**—without eroding human agency, creating automation bias, or misaligning with real-world constraints?

## Forces

| Force | Tension |
|:------|:--------|
| Decision Fatigue | Too many suggestions overwhelm users |
| Anchoring Risk | Poor suggestions may disproportionately influence choices |
| Dynamic Environments | Suggested options must adapt to changing contexts |
| Trust & Legitimacy | Suggestions must be perceived as credible |
| Constraints | Recommendations must honor logistical, legal, and policy limitations |

## Solution
A decision suggestion engine that:

- Ingests real-time contextual data (location, resource availability, urgency)
- Applies optimization, ranking, or recommendation models
- Surfaces ranked or tiered actionable choices
- Displays relevant explanatory signals
- Allows human override and adjustment
- Monitors suggestion acceptance rates and refines models

## Structure

```text
+-----------------------------+     +--------------------------+     +-------------------------------+
| Contextual Data Sources     | --> | Optimization/Ranking Model| --> | Decision Suggestion Generator |
| (Status, Location, Rules)   |     | (Multi-criteria ranking)  |     | (Ranked Recommendations)     |
+-----------------------------+     +--------------------------+     +-------------------------------+
                                                                          |
                                                       +----------------------------------+
                                                       | Suggestion Interface for Users   |
                                                       | (UX Display + Reason Codes)      |
                                                       +----------------------------------+
                                                                 |
                                              +-----------------+-----------------+
                                              |                                   |
                          +-----------------------------------+     +----------------------------------+
                          | Human Decision & Override Module |     | Suggestion Outcome Feedback Loop |
                          +-----------------------------------+     +----------------------------------+
```


## Participants

| Component | Responsibility |
|:----------|:---------------|
| Context Aggregator | Pulls real-time operational and contextual data |
| Ranking Model | Scores and ranks available options |
| Suggestion UX | Presents ranked options and rationale |
| Human Decision Module | Captures selections or overrides |
| Feedback Loop | Refines model based on outcomes |

## Consequences

| Benefit | Trade-off / Mitigation |
|:--------|:-----------------------|
| Reduces decision fatigue | Must avoid user over-reliance |
| Supports optimized choices | Must sustain transparent logic |
| Adapts to real-time factors | Monitor for context drift |
| Preserves human agency | UX must avoid black-box feel |

## Known Applications

| Agency/Institution | Use Case |
|:-------------------|:---------|
| FDNY | EMS Hospital and Unit Suggestion Tool |
| DOE | MySchools Student Placement Engine |
| Emergency Management | Disaster shelter assignment optimization |

## Implementation Considerations

### 🧠 Model Design
- Prefer multi-objective optimization models
- Consider multi-armed bandit algorithms for exploration
- Include explainability mechanisms (e.g., SHAP, decision trees)

### ⚖️ Fairness & Ethics
- Align optimization goals with policy and equity
- Monitor emergent biases in suggestions

### 🔁 Feedback & Adaptation
- Track override and acceptance rates
- Allow tuning of optimization goals over time

### 🔐 Data Privacy & Security
- Use only justifiable, policy-compliant features
- Mask irrelevant identifiers

## Related Patterns
- Risk Scoring for Prioritization
- Triage-Based Case Assignment
- Capacity-Aware Prioritization

## Anti-patterns to Avoid
- Blind ranking without explainability
- Hardcoding static suggestion logic
- No capture of override patterns
- Suggesting infeasible or unavailable options

## Example Tools & Frameworks

| Function | Tools |
|:---------|:------|
| Optimization Modeling | Google OR-Tools, Gurobi, CPLEX |
| Recommendation Systems | Surprise, LightFM, TensorRec |
| Explanation | SHAP, LIME, Fairlearn |
| UX Interface | Streamlit, Dash |
| Governance Monitoring | MLflow, Evidently AI |

---

# ✨ Signature Features

- **Augmentation, not automation:** Enhances human agency.
- **Anchored recommendations:** Grounded in real-world operational and policy constraints.
- **Transparent and adaptive:** Explainable suggestions and continuous learning.
- **Multi-objective optimization:** Balancing speed, fairness, specialization, and context.
