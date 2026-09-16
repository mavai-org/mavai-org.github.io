---
title: "How We Help"
description: "A statistical baseline for every AI service you deploy, then continuous monitoring against it — the evidence the EU AI Act, ISO/IEC 42001 and sector supervisors ask for."
keywords: ["AI compliance", "EU AI Act Article 72", "post-market monitoring AI", "AI baseline", "LLM monitoring", "ISO 42001", "NIST AI RMF", "FINMA AI", "AI assurance", "statistical baseline"]
summary: "Baseline · Monitor · Comply Mavai Methodologies measures how often your AI service gets it right, records that as a baseline, monitors the live service against it for the life of the project, and holds it to a contract that regulation can share."
---

## What a client gets

A service built on a language model does not pass or fail. It succeeds at a rate, and that rate moves whenever the model, the prompts or the circumstances change. Mavai Methodologies turns that fact into something you can know rather than hope. Quality is the point; regulation is the reason more teams are now asking for it.

Three things, in order: **Baseline · Monitor · Comply**

### Baseline

Any one call can be judged right or wrong. What nobody knows in advance is how often the service gets it right. We measure the service as deployed and record the result as a baseline: the model and version, the system prompt, the family of user prompts, the success rate they achieve at a stated confidence, the latency profile, and the covariates that describe the circumstances under which the measurement was made. The baseline belongs to the service, not to the model. Change any of its parts and the baseline no longer applies, which is exactly what you want a regulator to see.

### Monitor

From then on the live service is tested against its baseline as part of your normal delivery pipeline: every release, every model update, every prompt change, and on a schedule in between. Drift beyond the agreed bounds is flagged, at the confidence the baseline was set at, before it reaches production, let alone a supervisor. This is oversight across the whole project lifecycle, not a one-off audit before go-live.

### Comply

The service is held to a contract: what a good response is, and the rate at which it must be delivered. Every verdict says whether the service complies, at the stated confidence. Where a regulator, a customer or a standard sets the bar, the same contract carries it.

Every measurement and every verdict is persisted as a structured record that states what was measured, how many times, against what bar and at what confidence. Anyone can repeat the procedure on the same service, and anyone can check that the verdict follows from the record. The confidence level is part of the claim, and the record says so.

## What has to change in your project

Knowing that a stochastic service does what you say it does is not a document produced at the end. It changes how a project is tested, whether or not anyone outside the team ever asks:

- **Acceptance criteria become rates, not outputs.** "Answers the question correctly" becomes "answers correctly at least 95% of the time, at 99% confidence, on this prompt family."
- **Sample sizes are computed, not guessed.** The statistics determine how many runs carry a claim. A test whose evidence cannot support its verdict is refused, never quietly passed.
- **Every change to the service re-opens the question.** A new model version or an edited system prompt is a new service until it is re-baselined.
- **Monitoring is a first-class deliverable**, planned and resourced from the start, with its own owner.

We help teams make that shift: designing the contracts, sizing the evidence, integrating the tools into their pipelines, and reading the results.

## Compliance as the outcome

We do not sell compliance. We produce the evidence a team needs to trust its own service, and the regulatory regimes turn out to ask for the same evidence:

| Requirement | What it asks for | What the practice provides |
|---|---|---|
| EU AI Act, Art. 9 | A risk-management system that runs across the whole lifecycle, with testing against defined metrics | Baselines with stated thresholds and confidence; regression at every change |
| EU AI Act, Art. 72 | Post-market monitoring that actively collects performance data through the system's lifetime | Scheduled monitoring against the baseline, with drift detection |
| EU AI Act, Annex IV | Technical documentation including validation and testing procedures, metrics and results | The persisted measurement and verdict records |
| ISO/IEC 42001 | An AI management system with performance evaluation and continual improvement | The same records, organised as management-system evidence |
| NIST AI RMF | Measure and Manage functions: quantitative evaluation and ongoing monitoring | Baselines and monitoring are the measures |
| FINMA guidance on AI | Governance, inventory, and demonstrable control of model risk | Per-service baselines are the inventory and the control |

The names differ. The evidence is the evidence you would want anyway.

## Who this is for

The method is sector-neutral and the implementation work is the same in every sector, regulated or not. Where regulation is bringing it in today: **banking** (advisory, credit and client-facing assistants under FINMA and, where it reaches, the AI Act), **healthcare** (clinical-support and patient-facing services meeting high-risk obligations and medical-device surveillance), **insurance** (underwriting, claims and pricing models that must be demonstrably fair and stable), and **public-sector and supervisory bodies** that deploy AI or must judge the evidence others submit. A team with no supervisor at all runs the same practice; only the audience for the evidence changes.

## The method behind it

The statistics are not proprietary and not hidden. Mavai's frameworks — [punit](/projects/punit/) for Java, [feotest](/projects/feotest/) for Rust and [baseltest](/projects/baseltest/) for Python — are open source and implement one shared specification. The formal basis is set out in the [Statistical Companion](https://r.mavai.org/statistical-companion.pdf), for readers qualified to check it, and the practical introduction is our [guide to probabilistic testing](/probabilistic-testing/).

## Let's talk

A first conversation covers where your service lifecycle stands today, what a baseline-and-monitor regime would mean for your project, and which obligations, if any, it would satisfy along the way. No preparation is needed.

[Let's talk →](/contact/)
