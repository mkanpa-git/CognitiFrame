# 🛡️ Pattern: Eligibility or Compliance Matching

## Intent

To automate the assessment of whether an entity (person, business, application, document) meets predefined eligibility criteria, policy rules, or regulatory requirements—enhancing decision speed, consistency, and transparency.

---

## Context

Institutions frequently need to verify eligibility or compliance against complex, multi-layered criteria:
- Citizens qualifying for benefits
- Businesses qualifying for licenses
- Applicants meeting regulatory thresholds
- Documents meeting completeness or compliance standards

Manual review is time-consuming, prone to human error, and lacks auditability. AI-driven eligibility or compliance matching uses rule-based engines, ML models, or hybrid approaches to rapidly assess inputs against formalized criteria.

---

## Problem

How can systems consistently and accurately determine eligibility or compliance against dynamic, evolving criteria—while maintaining explainability, fairness, and auditability?

---

## Forces

| **Force**                       | **Tension**                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| Complexity of criteria           | Criteria often span multiple dimensions, exceptions, and conditional logic |
| Changing regulations             | Laws and policies change, requiring constant model updates                 |
| Interpretability vs automation   | Decisions must be explainable to regulators, not just fast                  |
| False positives vs false negatives | Compliance risks from either over-rejecting or over-accepting applicants   |
| Fairness across demographics     | Risk of bias if historical data reflects systemic inequalities             |

---

## Solution

An eligibility or compliance matching system combining:

- **Rule-based engines** for codified, stable policy requirements
- **Machine learning models** for nuanced prediction (where rules are incomplete or dynamic)
- **Human-in-the-loop review** for exceptions or borderline cases
- **Explainability layers** to justify each eligibility decision or compliance match
- **Continuous monitoring** to capture rule or policy changes

---

## Structure

```text
+---------------------+     +--------------------------+     +-----------------------+
| Intake & Preprocess | --> | Criteria Matching Engine | --> | Outcome & Rationale    |
| (Data validation)   |     | (Rules + ML Models)       |     | (Decision + Explanation) |
+---------------------+     +--------------------------+     +-----------------------+
                                              |
                        +---------------------+-------------------------+
                        |                                                   |
         +----------------------------+               +----------------------------+
         | Human Review for Exceptions |               | Policy Change Monitor       |
         +----------------------------+               +----------------------------+
```
---

## Participants

| **Component**             | **Responsibility**                                                         |
|----------------------------|-----------------------------------------------------------------------------|
| Intake Processor           | Pre-validates input data, ensuring completeness, consistency, and format normalization |
| Rules Engine               | Applies deterministic eligibility rules based on codified policies        |
| ML Prediction Engine       | Handles probabilistic eligibility assessments where hard rules are insufficient |
| Explanation Generator      | Produces human-readable rationales for eligibility decisions               |
| Human Review Interface     | Manages exceptions, appeals, or uncertain matches                          |
| Policy Change Monitor      | Detects updates in laws, regulations, or program eligibility criteria      |
| Audit Logger               | Captures detailed logs of decisions, inputs, and rationales for compliance review |

---

## Consequences

| **Benefit**                              | **Trade-off / Risk Mitigation**                                        |
|-------------------------------------------|------------------------------------------------------------------------|
| Consistent, scalable eligibility decisions | Requires governance to maintain rule/model currency                  |
| Increased transparency and auditability   | Needs explainability even for complex probabilistic models            |
| Faster service delivery                   | Must build strong exception-handling pathways                         |
| Adaptability to policy changes            | Requires structured policy monitoring and retraining protocols        |
| Reduced human workload                    | Still requires periodic human oversight for fairness and compliance   |

---

## Known Applications

| **Sector**     | **Use Case**                                                  |
|----------------|----------------------------------------------------------------|
| Government     | Public benefits eligibility screening (e.g., Medicaid, SNAP)  |
| Finance        | Loan eligibility verification, credit risk scoring            |
| Healthcare     | Insurance eligibility pre-checks, clinical trial enrollment   |
| Education      | Scholarship eligibility matching, student grant screening     |
| Public Safety  | Background compliance checks for licenses and permits         |

---

## Implementation Considerations

### 🧠 Data Validation
- Normalize key fields (e.g., income bands, residency, status)
- Ensure minimal required fields before attempting eligibility matching
- Build pre-screening layers to route clearly incomplete applications

### 🛂 Rules vs ML Balance
- Start rules-first where policy determinism is strong
- Introduce ML cautiously to avoid black-box effects in eligibility
- Maintain separate explanation paths for rule-based vs ML-driven outcomes

### 🔄 Governance and Monitoring
- Establish checkpoints for rule and model revalidation after every policy cycle
- Implement alert systems for detected policy updates from source authorities
- Maintain stakeholder access to review and challenge eligibility findings

---

## Related Patterns

- `Automated Document Intelligence`
- `Benefit Recommendation Engines`
- `Risk Scoring and Prioritization`
- `Policy Change Propagation Pipelines`
- `Exception Handling and Appeals Management`

---

## Anti-patterns to Avoid

- Hardcoding eligibility logic into monolithic application code
- Blindly replacing nuanced eligibility rules with purely statistical models
- Ignoring demographic fairness and disparate impact audits
- Failing to provide applicants with visibility into decision rationale
- Allowing policy drift without revalidating rule/model congruence

---

## Example Tools and Frameworks

| **Function**                | **Example Tools**                                         |
|------------------------------|-----------------------------------------------------------|
| Rules Engines                | Drools, Camunda DMN, OpenL Tablets                        |
| ML Model Serving             | Amazon SageMaker, Azure ML, TensorFlow Serving            |
| Explainability Frameworks    | SHAP (Shapley values), LIME, IBM AI Explainability 360     |
| Workflow Orchestration       | Apache Airflow, Camunda BPM, Salesforce Flow Engine        |
| Compliance Auditing          | Open Policy Agent (OPA), Fairlearn, Aequitas               |

---

## Signature Features

| **Feature**                        | **Description**                                                         |
|-------------------------------------|-------------------------------------------------------------------------|
| Dual Track Matching Pipeline        | Rule-based decisions with ML fallback when deterministic matching is insufficient |
| Explainability Layer                | Detailed human-readable rationale for every eligibility outcome        |
| Appeals and Exception Management    | Clear workflow for handling disputed or borderline eligibility results |
| Policy Update Propagation           | Monitoring service feeding rules/model revision pipelines              |
| Full Audit Trail                    | Capturing input, matching logic, decision outcome, and human reviews    |

---
