# Core Definitions

The definitions below are adapted for internal audit from Card, Min, and Serghiou's classification of research questions.

## Confirmatory question

A confirmatory question tests a predefined expectation, rule, threshold, or hypothesis.

In internal audit, confirmatory questions usually connect directly to:

- an audit objective;
- a risk or control expectation;
- a policy, law, standard, or procedure;
- a defined population; and
- specific exception criteria.

Example:

> Were all payments above CHF 50,000 approved by an authorized approver before payment date?

## Exploratory question

An exploratory question looks for patterns, anomalies, relationships, or risk indicators when the audit team does not yet have a specific testable expectation.

Exploratory analysis is useful for planning and discovery, but it is usually hypothesis-generating. It should not be reported as a finding until the pattern is validated against criteria, data quality, and business context.

Example:

> What approval timing patterns appear in high-value payments across business units?

## Causal question

A causal question asks whether a change, intervention, or exposure caused an outcome.

Causal questions require stronger design than ordinary audit analytics. They need a clear intervention, outcome, timing, comparison logic, and plausible controls for confounding factors.

Example:

> Did introducing automated approval routing reduce late approvals compared with comparable business units that did not implement it?

## Non-causal question

A non-causal question describes what exists in the data without claiming that one factor caused another.

Most practical audit analytics are non-causal. They describe exceptions, trends, distributions, relationships, process flows, or anomalies.

Example:

> How are late approvals distributed by business unit, approver role, and transaction value?

## Important boundary

Question type is not the same as evidence quality. A confirmatory question can still produce weak evidence if the population is incomplete or the logic is wrong. An exploratory question can produce useful planning insight without being strong enough for a finding.

Use the [Analytics Evidence Quality Gate](../analytics_evidence_quality_gate.md) after analysis to decide how far the result can be relied on.
