# 📄 Pattern: Outreach Targeting & Resource Deployment

## Intent
To algorithmically **identify, prioritize, and deploy outreach efforts and resources** toward individuals, communities, or locations with the greatest predicted need, risk, or opportunity for impact—supporting proactive, equitable, and efficient service delivery.

Rather than waiting for inbound requests or reactive service, the institution moves **outward**—intelligently, strategically, and fairly.

## Context
Cities and agencies often face the challenge of invisible or underserved populations: who needs help but hasn't asked?  
Where are preventable risks accumulating?

Outreach targeting aims to **amplify limited resources** by identifying those who would most benefit from early intervention, education, or services—before crises escalate or disparities widen.

Traditional targeting by geography or complaint volume can miss dynamic, cross-cutting indicators. Predictive targeting surfaces hidden need and structural inequities more systematically.

## Problem
How can institutions **proactively identify and reach underserved, at-risk, or high-impact populations**—while ensuring targeting strategies are fair, explainable, adaptive, and outcome-driven?

## Forces

| Force | Tension |
|:------|:--------|
| Visibility Gaps | Those most in need may be least visible in traditional systems |
| Targeting Fairness | Must avoid reinforcing biases or systemic exclusion |
| Dynamic Risk Profiles | Needs and risks evolve over time and context |
| Resource Constraints | Limited staff or funding forces hard prioritization decisions |
| Ethical Responsibility | Targeting must respect privacy, autonomy, and dignity |

## Solution
An outreach targeting system that:

- Ingests demographic, behavioral, historical, and environmental data
- Predicts need, risk, or eligibility propensity for services or interventions
- Ranks or clusters populations, areas, or individuals for outreach prioritization
- Optimizes resource deployment plans (e.g., canvassing routes, outreach team assignments)
- Provides explainable targeting rationales to staff and stakeholders
- Monitors outcomes (e.g., engagement rates, service uptake) for model refinement

## Structure

```text
+------------------------------+     +-----------------------------+     +-------------------------------+
| Demographic & Operational Data| --> | Need/Risk Prediction Engine  | --> | Outreach Targeting Priorities  |
| (Census, Service Histories)    |     | (Propensity, Risk Scoring)   |     | (Individuals, Areas, Households) |
+------------------------------+     +-----------------------------+     +-------------------------------+
                                                                                |
                                                      +-----------------------------------+
                                                      | Resource Deployment Optimization |
                                                      | (Scheduling, Routing, Assignment) |
                                                      +-----------------------------------+
                                                                                |
                                                +-----------------+-----------------+
                                                |                                   |
                        +------------------------------------+     +-------------------------------------+
                        | Outreach Interface (Dashboards, UI)|     | Outcome Monitoring & Feedback Loop |
                        +------------------------------------+     +-------------------------------------+
```

## Participants

| Component | Responsibility |
|:----------|:---------------|
| Data Aggregator | Collects and normalizes internal and external datasets |
| Propensity/Risk Model | Predicts service need, eligibility likelihood, or vulnerability |
| Target Prioritization Engine | Ranks individuals, areas, or groups for outreach |
| Deployment Optimizer | Plans team assignments, schedules, and routing |
| Outcome Tracker | Captures outreach results to refine future targeting |

## Consequences

| Benefit | Trade-off / Mitigation |
|:--------|:-----------------------|
| Enables proactive service delivery and early intervention | Requires ethical targeting policies and governance to prevent misuse |
| Maximizes impact per resource deployed | Targeting models must be continuously evaluated for fairness and drift |
| Reduces inequities by surfacing hidden need | Must avoid stigmatizing communities or creating surveillance perceptions |
| Improves operational efficiency in outreach | Requires integration with real-world logistical constraints |

## Known Applications

| Agency/Institution | Use Case |
|:-------------------|:---------|
| DSS | Homebase RAQ (Risk Assessment Questionnaire) for homelessness prevention outreach |
| DOHMH | Outreach targeting for vaccination campaigns and health screenings |
| DEP | Targeted water conservation and lead testing outreach |
| DOE | Chronic absenteeism prevention targeting |

## Implementation Considerations

### 🧠 Model Design and Targeting Logic
- Use multivariate models blending socio-demographic, behavioral, and geographic indicators
- Prioritize transparency: explain why areas or individuals were targeted
- Incorporate equity-focused features (e.g., historical under-service)

### ⚖️ Fairness & Ethical Anchoring
- Conduct disparate impact analyses before deployment
- Avoid proxy features that encode racial, income, or disability biases
- Provide opt-out mechanisms for privacy preservation where possible

### 🔁 Outcome Feedback and Adaptive Learning
- Monitor outreach engagement, service uptake, and downstream outcomes
- Retrain models periodically to adapt to changing conditions

### 🔐 Data Privacy and Sensitivity
- Respect data minimization principles—use only necessary attributes
- Anonymize sensitive information when feasible

## Related Patterns

- Risk Scoring for Prioritization
- Capacity-Aware Prioritization
- Decision Suggestion Algorithms
- Eligibility or Compliance Matching

## Anti-patterns to Avoid

- Targeting solely based on geography without risk or need analysis
- Treating model outputs as ground truth without human verification
- Over-targeting that creates fatigue or perception of harassment
- Failing to monitor outreach effectiveness

## Example Tools & Frameworks

| Function | Tools |
|:---------|:------|
| Predictive Modeling | scikit-learn, H2O.ai, XGBoost, TensorFlow |
| Geo-Optimization | ArcGIS, QGIS, Google OR-Tools |
| Outcome Monitoring | PowerBI, Tableau, Evidently AI |
| Fairness Auditing | Aequitas, IBM AI Fairness 360, Fairlearn |

## ✨ Signature Features

- **Proactive, Need-Based Service Delivery:** Outreach is driven by predicted need and opportunity, not reactive complaint systems.
- **Equity-Centered Targeting:** Prioritization corrects for historical inequities.
- **Dynamic Adaptation:** Targeting evolves with new data and outcomes.
- **Explainable and Transparent Outreach:** Decisions are traceable and understandable to stakeholders.
