---
title: "baseltest"
description: "A Python-native probabilistic testing framework — declarative-first, with one command-line tool to check, explore, optimise, measure and test a stochastic service."
keywords: ["baseltest", "probabilistic testing", "Python testing framework", "stochastic testing", "non-deterministic testing", "Python", "LLM testing", "statistical assertions", "declarative testing"]
weight: 7
language: "Python"
---

**baseltest** is a probabilistic testing framework for Python. It is designed for systems where behaviour is non-deterministic by nature — LLM-backed services above all, but also ML model inference, randomised algorithms, and anything network-dependent. It brings the same statistical methodology as [punit](/projects/punit/) and [feotest](/projects/feotest/) to the Python ecosystem, expressed in Python idioms rather than ported from either.

## How it works

A stochastic service does not pass or fail a single invocation; it succeeds at a rate. baseltest treats that rate as the thing under test: it runs the service repeatedly, judges each response against declared criteria, and renders a verdict backed by real statistics — Wilson confidence bounds and feasibility-checked sample sizes — rather than a green tick over one lucky sample.

## Key capabilities

- **Declarative-first authoring** — a small, language-agnostic contract file (`mavai-contract/1`) names the inputs, what a good response looks like, and optionally the bar it must clear; no statistical vocabulary is needed for a first honest result
- **One command, five verbs** (`basel`) — **check** validates a contract with zero samples, **explore** sweeps a grid of service configurations, **optimize** searches the configuration space iteratively, **measure** records every criterion and persists a baseline, and **test** renders a statistical verdict
- **Multiple criteria per contract** — a service examined through several Bernoulli streams in one run, each at its own bar, with per-criterion verdicts
- **Declared and empirical thresholds** — a criterion either carries its own normative bar, or derives one from a measured baseline that a later test is judged against
- **Risk-driven sizing** — state the worst acceptable true rate and the confidence, and baseltest computes the required sample size; a run whose evidence cannot carry the claim is refused, never quietly passed
- **Structured-response checks** — JSON, XML and YAML transforms with standards-pinned path expressions (RFC 9535 JSONPath, XPath 1.0), validated against declared schemas before a single sample is paid for
- **Built-in language-model services** — declare an LLM service by name and configuration and run it without writing binding code; home-grown services are reached through a registered binding
- **Latency bounds** — evaluate response times at percentile level, derived from a baseline's latency profile or declared outright
- **Covariate-aware identity** — a baseline records the resolved service identity it was measured under; a drifted configuration key or covariate refuses the test, naming the key
- **Contractual exit codes** — success, judgement failure, refusal and unsupportable evidence are distinct exit codes, made for CI
- **Graduation to Python** — when the contract file runs out of expressive power, author the service contract directly in Python against the same engine; nothing is lost by graduating
- **HTML reporting** — the `mavai` renderer draws verdict, measurement, exploration and optimisation reports over the artefacts every run persists

## The parameter triangle

You control two of three variables — sample size, confidence, and threshold — and statistics determines the third. baseltest sizes a declared bar at its feasibility minimum by default, accepts an explicit sample size, or derives the size from your stated risk.

## Relationship to punit and feotest

baseltest implements the same statistical methodology as punit and feotest, verified against the same [mavai-R](/projects/mavai-r/) reference datasets. The three frameworks share a specification — what to compute — but not an implementation. Where punit uses JUnit extensions and Java annotations, and feotest uses Rust macros and traits, baseltest leads with a declarative contract file and a command-line tool, with direct Python authorship as the graduation path.

## Add to your project

baseltest is published on [PyPI](https://pypi.org/project/baseltest/) and requires Python 3.11 or newer:

```sh
pip install baseltest
```

Then write a contract file and run it:

```yaml
format: mavai-contract/1
contract: greeting-service-is-polite
service: greeting-service
inputs:
  - "Alice"
  - "Bob"
criteria:
  - threshold: 0.95
    contains: "hello"
```

```sh
basel check greeting.yaml    # validate the contract, zero samples
basel test greeting.yaml     # judge it against its declared bar
```

## Get started

Visit the [baseltest repository on GitHub](https://github.com/mavai-org/baseltest) for installation instructions, a ready-to-run example that needs no API key, and the full user guide.
