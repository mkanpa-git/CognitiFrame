# 🧠 CognitiFrame: Patterns for Systemic AI and Decision Architecture

*A catalog of patterns for architecture, ethics, and accountability in applied intelligence systems.*

---

## 📘 Preface

We’ve grown comfortable thinking about AI in terms of **context windows**, **agentic frameworks**, **workflow orchestrators**, and an ever-expanding alphabet of technical splendor.  

We refine **model architectures**, optimize **prompt engineering rituals**, and assemble **CSP-integrated toolchains**—as if layering tools ever closer to perfection might somehow tame the unruliness of human decision-making.

It’s a beautiful illusion:  
That with enough tokens parsed and pipelines orchestrated, governance will be automatic, judgment will be objective, and consequences will sort themselves out.

We often treat AI as a **model**, not a **process**—as if decisions stop once the model outputs a score.  
In practice, that score travels. It moves through systems. It justifies denials, triggers workflows, and shapes outcomes for people.

We frame **fairness** as a metric. But fairness lives in context—who is impacted, who can appeal, who defines equity in the first place.

We define **explainability** as feature importance or attention weights. But what actually matters is **legibility**—to caseworkers, to residents, to auditors, to courts.

We describe AI as **automation**—but many decisions require **judgment**, **dialogue**, and **discretion**.

We approach governance as a **compliance checkbox**. But in long-lived institutions, it’s really about architectural commitments—**traceability**, **reversibility**, and **institutional memory**.

In short, as AI systems become more embedded into institutional decision-making processes, they don’t replace human judgment—they shape it.
They filter options, signal risk, and recommend action.
And judgment, when guided by machines, still carries **consequences**.

---

## 🧩 What This Catalog Is

**CognitiFrame** is a pattern catalog for people designing AI systems not just to *work*, but to *hold up under scrutiny*—technical, legal, and human.

It doesn’t offer the best algorithm. It offers ways to think about:

- How signals flow  
- Where risk accumulates  
- When human judgment matters  
- And what institutions remember-or forgets

While other AI pattern collections have focused on principles of trustworthiness[^1] or system design patterns for ethical alignment[^2],  agent-based architectural patterns for AI planning and coordination[^3], or responsible design patterns embedded within machine learning pipelines[^4],**CognitiFrame** approaches the challenge through the lens of institutional systems—where decisions unfold across workflows, policies, histories and futures.

These patterns reflect how AI is entering the spaces where public decisions are made—not as retrofits, but as forward-looking structures that surface recurring tensions, design needs, and the demands of fairness, transparency, and public accountability.

[^1]: CSIRO Responsible AI Pattern Catalogue – https://research.csiro.au/ss/science/projects/responsible-ai-pattern-catalogue/  
[^2]: *Responsible-AI-by-Design: A Pattern Collection for Designing Responsible AI Systems* (arXiv, 2022) – https://arxiv.org/pdf/2203.00905  
[^3]: *Agent Design Pattern Catalogue: A Collection of Architectural Patterns* – Patterns for designing agent-based AI systems, supporting goal-seeking, deliberation, and coordination. [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0164121224003224), [arXiv](https://arxiv.org/html/2405.10467v1)  
[^4]: *Responsible Design Patterns for Machine Learning Pipelines* – A library of RDPs addressing data governance, bias mitigation, and transparency in ML workflows. [arXiv](https://arxiv.org/abs/2306.01788)


---

## 🔍 What Problems Do These Patterns Help Solve?

Instead of listing capabilities, we start with the **questions** people in public-interest systems face:

- How do I structure PDFs and forms into usable data without losing trust or auditability?  
  → [Automated Document Intelligence](./Automated%20Document%20Intelligence.md)

- How do I accurately and systematically extract actionable insights from free-text, genomic, audio, or social data?  
  → [Information Extraction & Interpretation](./Information%20Extraction%20and%20Interpretation.md)

- How do I monitor for fairness loss once a model is deployed and in use?  
  → [Bias & Equity Monitoring](./Bias%20and%20Equity%20Monitoring.md)

- Are there patterns—like benefit churn or complaint spikes—that signal a resident might need help?  
  → [Civic Signal Detection for Resident Support](./Civic%20Signal%20Detection%20for%20Resident%20Support.md)

- Can we make sure translated notices still sound like we care?  
  → [Communication & Translation Automation](./Communication%20and%20Translation%20Automation.md)

- How do I explain a decision—months later—to an auditor, or even a judge?  
  → [Decision Traceability & Institutional Memory](./Decision%20Traceability%20and%20Institutional%20Memory.md)

- How do I prioritize inspections, case reviews, or interventions fairly under resource constraints?  
  → [Risk Scoring for Prioritization](./Risk%20Scoring%20for%20Prioritization.md)

- Can we build AI systems that recommend actions without replacing human discretion?  
  → [Decision Suggestion Algorithms](./Decision%20Suggestion%20Algorithms.md)

- How do I structure eligibility or compliance checks to be explainable, defensible, and equitable?  
  → [Eligibility or Compliance Matching](./Eligibility%20or%20Compliance%20Matching.md)

- How can we proactively find and support residents before needs escalate unseen?  
  → [Outreach Targeting & Resource Deployment](./Outreach%20Targeting%20and%20Resource%20Deployment.md)

- What parts of the city are economically struggling, based on non-traditional signals?  
  → [Economic Development & Business Sentiment Analysis](./Economic%20Development%20and%20Business%20Sentiment%20Analysis.md)

- How do I allocate scarce health or safety resources before a crisis peaks?  
  → [Emergency & Public Health Response](./Emergency%20and%20Public%20Health%20Response.md)

- Which blocks are at environmental risk—and how can we detect utility anomalies before they cascade?  
  → [Environmental & Utility Monitoring](./Environmental%20and%20Utility%20Monitoring.md)

- How do I flag possible fraud that’s not just suspicious, but defensible?  
  → [Fraud, Risk & Compliance Analytics](./Fraud%20Risk%20and%20Compliance%20Analytics.md)

- How can planners, residents, and agencies all understand the impact of new zoning rules?  
  → [Planning, Mapping, & Visualization](./Planning%20Mapping%20and%20Visualization.md)

- Where do cases get stuck, dropped, or delayed—and how can I optimize them fairly?  
  → [Predictive Case & Service Optimization](./Predictive%20Case%20and%20Service%20Optimization.md)

- How do I maintain infrastructure predictively, before failure—not after?  
  → [Predictive Maintenance & Infrastructure Monitoring](./Predictive%20Maintenance%20and%20Infrastructure%20Monitoring.md)

- Before a new rule is passed, can we model how it might affect different populations?  
  → [Regulation Change Impact Modeling](./Regulation%20Change%20Impact%20Modeling.md)

- What are people actually saying—in reviews, surveys, or social media?  
  → [Sentiment & Opinion Mining](./Sentiment%20and%20Opinion%20Mining.md)

- How do we balance throughput and fairness in managing urban mobility?  
  → [Smart City Mobility & Traffic Optimization](./Smart%20City%20Mobility%20and%20Traffic%20Optimization.md)

- How do we automate and optimize operational workflows—routing, triage, scheduling—at scale without losing flexibility?  
  → [Operational Automation & Optimization](./Operational%20Automation%20and%20Optimization.md)

- Can AI be used in surveillance settings while respecting ethics and legal guardrails?  
  → [Surveillance & Public Safety Augmentation](./Surveillance%20and%20Public%20Safety%20Augmentation.md)


---

## 🧠 Why This Matters

These aren’t just use cases. They’re **decision patterns**.  
They help you see how:

- Information flows  
- Power is applied  
- Trust is earned—or lost  
- Outcomes unfold across time and institutions

**CognitiFrame** exists because designing AI systems means designing for **consequence**.  
That’s architecture. And it’s worth getting right.
