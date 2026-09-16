---
title: "Mavai — Testing Non-Deterministic Systems"
description: "Open-source tools for probabilistic testing, AI performance measurement, and regulatory compliance. Statistical unit testing for non-deterministic systems."
keywords: ["probabilistic testing", "AI performance measurement", "ISO 42001", "non-deterministic testing", "AI regression testing", "AI compliance", "statistical unit testing", "punit"]
# The "Mavai in a Nutshell" cards on the home page. Card bodies are Markdown.
nutshell:
  heading: "Mavai in a Nutshell"
  cards:
    - title: "Baseline"
      body: >-
        Any one call can be judged right or wrong. What nobody knows in advance is
        how often the service gets it right. A baseline measures that rate at a
        stated confidence and records it together with the model, the prompts, and
        the circumstances it was measured under.
    - title: "Monitor"
      body: >-
        Hold the service to its baseline for as long as it runs. Every release,
        every model or prompt change, and on a schedule in between, the live
        service is tested against the baseline, and drift beyond the agreed bounds
        is flagged at the confidence the baseline was set at.
    - title: "Comply"
      body: >-
        Regulators ask for three things: a record of what was measured, evidence
        that the service is still being watched, and a method that others can
        inspect. The baseline is the record. Monitoring is the evidence. And the
        method is already documented in public: the
        [Statistical Companion](https://r.mavai.org/statistical-companion.pdf)
        sets out the statistics, and the [open-source frameworks](/projects/)
        implement it line by line. That is the technical documentation the EU AI
        Act asks for, and what any supervisor, auditor or standard can read.
---
