# Causal vs. Non-Causal Questions

Most internal audit analytics should be framed as non-causal unless the audit team has a defensible design for causal inference.

## Causal questions

A causal question asks whether an intervention or exposure changed an outcome.

Examples:

- Did the new approval workflow reduce late approvals?
- Did automated three-way matching reduce invoice exceptions?
- Did a training program reduce policy violations?
- Did introducing continuous monitoring reduce repeat control failures?

Causal questions require more than a before/after chart. At minimum, the audit team should consider:

- the intervention date and affected population;
- a credible comparison group or baseline;
- other changes that occurred at the same time;
- data quality before and after the intervention;
- whether the outcome definition stayed stable; and
- whether observed changes could be explained by volume, mix, seasonality, staffing, system migration, or policy changes.

Common causal designs include interrupted time-series analysis, difference-in-differences, regression discontinuity, matching, and controlled before/after comparisons. These methods are useful, but they usually require specialist review before being used for strong conclusions.

## Non-causal questions

A non-causal question describes patterns, exceptions, relationships, distributions, or flows without claiming that one thing caused another.

Examples:

- What percentage of payments were approved after payment date?
- Which business units have the highest late-approval rate?
- How are approval delays distributed by approver role and transaction amount?
- Which vendors share bank accounts or addresses?
- How do access requests flow through approval steps?

Non-causal analysis is often the right choice for audit work because it aligns with practical audit purposes: identifying exceptions, understanding populations, selecting samples, prioritizing follow-up, and communicating risk patterns.

## Reporting discipline

Do not write “X caused Y” unless the analysis was designed to support causal inference. Safer language is often:

- “was associated with”;
- “coincided with”;
- “was higher among”;
- “was concentrated in”;
- “indicates a potential risk area”; or
- “requires follow-up to determine root cause.”
