# 📄 Pattern: Risk Scoring for Prioritization

## Intent

To algorithmically assign risk scores to entities (e.g., buildings, individuals, cases, regions) to support prioritization decisions—improving allocation of limited resources such as inspections, case reviews, outreach, or benefits with measurable transparency and policy alignment.

---

## Context

Government and civic institutions frequently operate under resource constraints: too many inspections to conduct, cases to review, or services to deliver, and not enough staff or time. Traditional prioritization methods—like FIFO, rule-based heuristics, or complaint volume—fail to capture latent or compound risks.

Risk scoring systems use machine learning to predict adverse outcomes (e.g., fire, eviction, re-entry into shelter, hospitalization), enabling early intervention and more efficient resource targeting.

---

## Problem

How can institutions rank or prioritize service units (cases, buildings, people) by underlying risk—at scale, with fairness, auditability, and adaptability to real-world constraints?

---

## Forces

| **Force**                     | **Tension**                                                                 |
|------------------------------|------------------------------------------------------------------------------|
| Resource scarcity            | Must decide whom to serve first under limited capacity                      |
| Historical bias in data      | Training data may reflect or reinforce systemic inequities                  |
| Explainability vs Model Power| Complex models offer better accuracy but reduce transparency                |
| Staff override vs trust erosion | Human overrides risk undermining algorithmic legitimacy                 |
| Adaptation to shifting trends| Risk signals change over time (e.g., heatwaves, pandemics, gentrification)  |

---

## Solution

A predictive scoring system trained on historical patterns of adverse outcomes, supported by a pipeline to:

- Ingest structured and unstructured real-world signals (inspections, demographics, complaints, prior incidents)  
- Train a classification/regression model for adverse events  
- Score new cases/buildings/records periodically or in real-time  
- Provide ranked lists or heatmaps for prioritized service deployment  
- Allow policy-configured thresholds or exclusion criteria  
- Integrate with human workflows and allow override logging  
- Track model calibration and performance over time

---

## Structure

```
+---------------------------+     +---------------------------+     +---------------------------+
| Operational Data Sources  | --> | Feature Engineering       | --> | Risk Prediction Model     |
| (Complaints, Events, etc.)|     | (Spatial, Temporal, etc.) |     | (ML Classifier/Regressor) |
+---------------------------+     +---------------------------+     +---------------------------+
                                                                       |
                                                    +----------------------------------+
                                                    | Prioritized Risk-Scored Entities |
                                                    | (Cases, Buildings, People, etc.) |
                                                    +----------------------------------+
                                                                |
                                                +----------------+-----------------+
                                                |                                  |
                                +----------------------------+      +-----------------------------+
                                | Decision Interface (UX)    |      | Policy Overrides / Logging  |
                                | (List, Map, API)           |      | (Manual review or exclusion)|
                                +----------------------------+      +-----------------------------+
```

---

## Participants

| **Component**            | **Responsibility**                                                                 |
|--------------------------|------------------------------------------------------------------------------------|
| Feature Store            | Holds engineered features used for modeling                                       |
| Prediction Engine        | Applies trained model to score incoming units                                     |
| Risk Triage Interface    | Displays risk-ranked outputs for operational action                               |
| Policy Configuration     | Sets thresholds, criteria, or exclusions for scores                                |
| Human Reviewer Module    | Enables overrides, adds context, logs justifications                              |
| Feedback Loop Evaluator  | Compares predictions to actual outcomes for recalibration                         |

---

## Consequences

| **Benefit**                                 | **Trade-off / Mitigation**                                               |
|--------------------------------------------|---------------------------------------------------------------------------|
| More efficient resource targeting           | Requires clear explanation and audit path for public accountability       |
| Enables early intervention and risk mitigation | Model drift must be monitored and retraining procedures established   |
| Supports transparency in prioritization     | Ethical review boards may be needed to vet logic and input data           |
| Aligns practice with policy goals           | Must document how equity and legal compliance are ensured in scoring      |

---

## Known Applications

| **Agency**     | **Use Case**                                                           |
|----------------|------------------------------------------------------------------------|
| FDNY           | RBIS: Fire inspection prioritization using ALARM model                 |
| DSS            | Housing Prioritization for homeless prevention and placement           |
| ACS            | Severe Harm Risk Model for child welfare triage                        |
| DOHMH          | Targeted health inspections and public health outreach models          |

---

## Implementation Considerations

### 🧠 Model Training & Evaluation

- Use interpretable models (XGBoost, Logistic Regression) where possible  
- Consider calibration and lift curves to evaluate score quality  
- Include variables that reflect policy-aligned priorities (e.g., elderly, low-income)

### ⚖️ Fairness & Ethics

- Conduct fairness audits (e.g., disparate impact analysis)  
- Log score overrides and track patterns of exclusion or divergence  
- Mask sensitive variables if proxy discrimination is a concern

### 🔁 Feedback & Governance

- Integrate with audit dashboards to compare predicted vs. actual outcomes  
- Retrain models periodically or after policy shifts  
- Allow policy leaders to review feature importances and scoring logic

### 🔐 Data Privacy & Security

- Use hashed identifiers to prevent PII leakage  
- Log all access and risk score views by users  
- Avoid black-box vendor models without transparency

---

## Related Patterns

- `Eligibility Threshold Prediction`  
- `Outreach Targeting & Resource Deployment`  
- `Triage-Based Case Assignment`  
- `Capacity-Aware Prioritization`  

---

## Anti-patterns to Avoid

- Training on biased or incomplete data without external validation  
- Hardcoding priority thresholds without policy input  
- Using opaque third-party scores without interpretability  
- Failing to explain why certain entities were ranked higher or lower  
- Allowing unchecked manual overrides with no logging or review

---

## Example Tools & Frameworks

| **Function**           | **Tools**                                                      |
|------------------------|-----------------------------------------------------------------|
| Modeling & Scoring     | scikit-learn, XGBoost, H2O.ai, DataRobot, LightGBM             |
| Fairness Auditing      | Aequitas, IBM AI Fairness 360, Fairlearn                      |
| Explanation & UX       | SHAP, LIME, Dash, Streamlit                                   |
| Model Governance       | MLflow, WhyLabs, ModelDB                                      |
| Policy Feedback Loop   | Evidently AI, Open Policy Agent (OPA) + Decision Logs         |
