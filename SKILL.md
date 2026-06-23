---
name: scientific-problem-discovery
description: Use for open-ended research reasoning, claim evaluation, literature synthesis, metric design, data interpretation, model building, benchmark comparison, figure interpretation, or any workflow where a conclusion is produced from definitions, evidence, transformations, assumptions, proxies, or comparisons. Focus on auditing the claim-generation chain before answering.
---

# Scientific Problem Discovery

## Purpose

Use this skill to discover hidden problems in how a research conclusion is generated.

The goal is to inspect whether a claim, question, comparison, metric, model, definition, evidence base, transformation, interpretation, or conclusion is validly produced from its premises.

Favor high recall over brevity. Research workers usually need real problem discovery more than token savings. Scan the full claim-generation chain for possible failure points, then rank them by consequence and evidential support.

Start from evidence in the input. Infer the kind of research action from the input itself, and use domain knowledge only when the input supports it.

## Core Rule

Do not evaluate a conclusion as a naked sentence, number, trend, score, label, or figure.

First reconstruct the claim-generation chain:

```text
claim = f(question, object, operational_definition, evidence, transformation, comparison, assumptions, reasoning_step, scope)
```

Only after reconstructing this chain should you judge whether the claim is meaningful, comparable, supported, generalizable, or actionable.

## Mandatory Mindset

Assume there may be hidden failure modes the user has not noticed. The audit should be broad first, then ranked.

Scan the full chain for weak links:

- object: unclear, unstable, or mixed research object;
- concept: concept-to-proxy mismatch or operational definition drift;
- evidence: selection bias, missing counterexamples, weak evidence quality, or unsupported evidence scope;
- transformation: hidden filtering, cleaning, aggregation, scoring, normalization, conversion, or representation changes;
- comparison: incompatible definition spaces, scales, protocols, populations, datasets, metrics, tasks, or representation pipelines;
- reference: baseline, reference case, control, null model, calibration, or denominator mismatch;
- inference: correlation-to-causation jump, trend-to-mechanism jump, proxy-to-concept jump, benchmark-to-real-world jump, or local-to-general overreach;
- alternatives: plausible mechanisms, artifacts, biases, processing choices, or definitions not ruled out;
- presentation: figure, table, wording, visualization, or narrative choices that may create a misleading interpretation;
- scope: conclusions whose strength or generality exceeds what the chain supports.

## Research Action Inference

Before answering, infer what kind of knowledge-production action the user is performing. Possible actions include, but are not limited to:

- defining a concept;
- choosing a proxy or metric;
- comparing two objects, methods, papers, datasets, figures, populations, or claims;
- deriving a quantity or score;
- interpreting a trend, pattern, anomaly, or negative result;
- explaining a mechanism;
- inferring causality;
- generalizing from a sample or case;
- synthesizing literature;
- designing a benchmark or evaluation standard;
- transforming a representation, figure, label, or dataset;
- mapping an idealized, simplified, or proxy system to a target system;
- deciding whether a conclusion can be stated in a paper.

The action type is a hypothesis inferred from input evidence, not a fixed taxonomy. If multiple action hypotheses are plausible, list them and audit the risks for each.

## Reasoning Loop

For every research result, comparison, or interpretation, perform the full scan:

1. Identify the candidate claim.
   - What conclusion is the user trying to draw?
   - Is it descriptive, comparative, causal, mechanistic, predictive, normative, methodological, or practical?

2. Identify the research object.
   - What exactly is being studied, represented, measured, compared, explained, or decided?
   - Is the object physical, conceptual, statistical, textual, algorithmic, visual, social, biological, methodological, or a mixture?

3. Infer the research action.
   - What knowledge-production action is being performed?
   - Are there multiple plausible actions at once?

4. Reconstruct the claim-generation chain.
   - Definitions.
   - Proxies or measurements.
   - Evidence sources.
   - Transformations and filters.
   - Baselines, controls, denominators, or reference cases.
   - Comparisons.
   - Assumptions.
   - Reasoning steps.
   - Intended scope.

5. Scan weak links across the whole chain.
   - Object weakness.
   - Definition/proxy weakness.
   - Evidence weakness.
   - Transformation weakness.
   - Comparison weakness.
   - Baseline/reference/control weakness.
   - Inference weakness.
   - Alternative-explanation weakness.
   - Presentation/representation weakness.
   - Scope weakness.

6. Rank risks.
   - High risk / must resolve before the conclusion is safe.
   - Medium risk / affects confidence, interpretation, or scope.
   - Low risk / worth noting but probably not blocking.
   - Speculative risk / plausible but needs more context.

7. Attach evidence to each important risk.
   - What in the input triggered the risk?
   - Why would it change the conclusion?
   - What wrong conclusion could result if ignored?

8. Propose minimal checks.
   - What smallest metadata, control, sensitivity analysis, counterexample search, robustness check, independent evidence, or reformulation would confirm or refute the risky claim?

9. Limit the conclusion.
   - State what can be concluded now.
   - State what cannot be concluded yet.
   - State the narrowest valid scope of the claim.

## Trigger Operations

Activate this skill whenever the task involves any operation that produces, compares, transforms, or justifies a conclusion, including:

- defining an object, construct, category, mechanism, or research direction;
- choosing a metric, proxy, score, label, benchmark, threshold, or ranking;
- comparing values, papers, methods, datasets, models, populations, cases, trends, figures, or claims;
- interpreting a pattern, anomaly, improvement, negative value, disagreement, or contradiction;
- cleaning, filtering, excluding, aggregating, normalizing, rescaling, converting, plotting, or summarizing information;
- using a baseline, control, reference case, background, calibration, standard, or null model;
- inferring causality, mechanism, importance, superiority, generality, novelty, or practical value;
- mapping a simplified/proxy representation to a real target;
- preparing a statement for a paper, report, presentation, or research decision.

## Output Style

When this skill is active, structure the answer as:

```text
1. Candidate claim or decision
2. Inferred research action(s)
3. Claim-generation chain
4. Full-chain risk scan
   - High risk / must resolve
   - Medium risk / affects confidence or scope
   - Low risk / worth noting
   - Speculative risk / needs more context
5. Comparability and inference-validity checks
6. Alternative explanations
7. Minimal checks or missing metadata
8. Provisional conclusion and forbidden overclaims
```

For each high or medium risk, include: input evidence, why it matters, possible wrong conclusion, and minimal check. Do not overstate certainty. If the chain is underspecified, say what cannot be concluded yet. Do not force the answer into any predefined research field.
