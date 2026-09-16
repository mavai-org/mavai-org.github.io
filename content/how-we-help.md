---
title: "How We Help"
description: "A statistical baseline for each AI service you deploy, continuous monitoring against it, and a method documented in public — with the tools and the know-how to build it into your delivery pipeline."
keywords: ["AI baseline", "LLM monitoring", "probabilistic testing", "AI service testing", "statistical baseline", "EU AI Act", "ISO 42001", "FINMA AI", "AI evidence"]
---

Every answer a language-model service gives can be judged right or wrong. What no single answer tells you is how often the service is right, and that rate moves whenever the model, the prompts or the circumstances change. Mavai™ turns that fact into something you can know rather than hope: a statistical baseline for each service you deploy, continuous monitoring against it, and a method documented in public. Where the EU AI Act, ISO/IEC 42001 or a sector supervisor's guidance applies to your service, the records this produces are the evidence those instruments require. Where none applies, they are the evidence you would want anyway.

## Baseline

The rate is not known until it is measured. We measure the service as deployed and record the result as a baseline: the model and version, the system prompt, the family of user prompts, the success rate they achieve over a stated number of runs, the latency profile, and the covariates: the exogenous conditions the service was measured under, such as the provider backend, the region or the time of day. The baseline belongs to the service, not to the model. Change any of its parts and the baseline no longer applies; change the conditions and a different baseline is called for.

## Monitor

From then on the live service is tested against its baseline as part of your normal delivery pipeline: every release, every model update, every prompt change, and on a schedule in between. Each check takes a fresh sample of the live service and compares its success rate with the bound the baseline implies for a sample of that size. A rate below the bound is flagged as degradation, with a stated confidence, typically 95%, before it reaches production. This is oversight across the whole project lifecycle, not a one-off audit before go-live.

## Comply

The baseline is the record, monitoring is the evidence, and the method is documented in public: the [Statistical Companion](https://r.mavai.org/statistical-companion.pdf) sets out the statistics and the [open-source frameworks](/projects/) implement it line by line. Every measurement and every verdict is persisted as a structured record that states what was measured and how many times, and, for every verdict, the bound it was judged against and the confidence of the claim. Anyone can repeat the procedure on the same service, and anyone can check that the verdict follows from the record. The confidence level is part of the claim, and the record says so.

## What changes, from project to pipeline

Knowing that a stochastic service does what you say it does is not a document produced at the end. It changes how the project is tested, and the change does not stop at the project: once the baseline exists, the pipeline that ships and runs the service is where it earns its keep.

- **Acceptance criteria become rates, not outputs.** "Answers the question correctly" becomes "answers correctly at least 95% of the time, at 99% confidence, on this prompt family."
- **Sample sizes are computed, not guessed.** The statistics determine how many runs carry a claim. A test whose evidence cannot support its verdict is refused, never quietly passed.
- **Every change to the service re-opens the question.** A new model version or an edited system prompt is a new service until it is re-baselined, and the pipeline knows it.
- **Monitoring becomes part of operations.** Planned and resourced from the start, with its own owner, running on the same schedule as everything else you operate.
- **Something new gets deployed alongside the application.** Monitoring a live service means running its checks where it runs, against the inputs and the backends it really sees. That takes an artefact of its own, a *sentinel*: a lightweight runner that carries the same tests as the pipeline, without a test harness, and measures the service in its deployed environment.

All of this is well within reach of a team that already runs a delivery pipeline, because the tools carry the weight. [punit](/projects/punit/) for Java, [feotest](/projects/feotest/) for Rust and [baseltest](/projects/baseltest/) for Python do the statistics, the sizing and the record-keeping; a test that would take a statistician to write takes a contract file and a command. The sentinel is documented in the [punit user guide](https://github.com/mavai-org/punit/blob/main/docs/USER-GUIDE.md) and its [deployment guide](https://github.com/mavai-org/punit/blob/main/docs/SENTINEL-DEPLOYMENT-GUIDE.md), and it is ready to put into practice. Mavai brings the know-how to put the tools where they belong: we train your team to write service contracts and size the evidence, integrate the frameworks into your development and operations pipeline, and read the results with you. What you do with the evidence, and to whom you present it, is up to you.

## Let's talk

A first conversation covers where your service lifecycle stands today and what a baseline-and-monitor regime would mean for your project. No preparation is needed.

[Let's talk →](/contact/)
