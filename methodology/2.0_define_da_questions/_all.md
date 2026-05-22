# Introduction and Purpose

Internal audit data analysis often fails before the first script is written. The usual problem is not the tool; it is an unclear audit question.

A weak question sounds like:

> Can we analyze purchase orders?

A stronger question sounds like:

> For purchase orders above CHF 50,000 created during the audit period, identify cases where approval occurred after release, the approver was not authorized for the amount, or the requester and approver were the same person.

The second version is usable because it defines the population, expected behavior, exception logic, required fields, and audit purpose.

This section adapts research-methodology distinctions from Card, Min, and Serghiou's *Open, rigorous and reproducible research* to internal audit practice. The goal is not to make every audit analysis academic. The goal is to help auditors label the type of question they are asking, choose a suitable analytical approach, and avoid overstating what the data can prove.

The two core distinctions are:

- **Confirmatory vs. exploratory**: Are we testing a defined expectation, or looking for patterns and leads?
- **Causal vs. non-causal**: Are we trying to assess an intervention's effect, or describe relationships, distributions, and exceptions?

These distinctions matter because they affect data requirements, evidence strength, reporting language, and whether the output can support an audit conclusion or only a planning lead.

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

# Confirmatory vs. Exploratory Questions

Confirmatory and exploratory questions both have a place in internal audit. The mistake is treating them as if they produce the same kind of evidence.

| Dimension | Confirmatory | Exploratory |
| --- | --- | --- |
| Starting point | Defined audit objective, risk, control, rule, threshold, or hypothesis | Open-ended area of interest, unfamiliar process, unexplained risk, or broad population |
| Main purpose | Test whether expected behavior occurred | Discover patterns, anomalies, leads, or possible explanations |
| Typical output | Exception list, exception rate, pass/fail result, trend against a threshold | Risk indicators, clusters, outliers, correlations, process patterns, questions for follow-up |
| Evidence status | Can support audit testing if data, logic, and exceptions are validated | Usually supports planning, scoping, or follow-up; not a finding by itself |
| Main risk | False comfort if the rule, population, or data quality is wrong | Overclaiming patterns as conclusions or findings |

## Confirmatory questions in audit

Use confirmatory questions when the audit team can define the expected behavior before analysis.

Good confirmatory questions usually include:

- population;
- period;
- rule or expectation;
- exception condition;
- required fields; and
- intended audit use.

Examples:

- Were all payments above CHF 50,000 approved before payment date by an authorized approver?
- Did terminated users retain system access after their termination date?
- Were purchase orders created before invoice receipt for all sampled procure-to-pay transactions?
- Did all privileged-access reviews occur within the required quarterly review window?

Confirmatory analysis is often suitable for control testing, compliance testing, full-population exception testing, and targeted sample selection.

## Exploratory questions in audit

Use exploratory questions when the audit team needs to understand the data, process, or risk pattern before defining a precise test.

Examples:

- Which transaction types show unusual approval timing patterns?
- Which vendors have unusual combinations of bank-account changes, payment frequency, and manual payment overrides?
- How do access-request volumes and approval delays vary by system, role, and business unit?
- Are there clusters of expense claims with unusual timing, amount, or category patterns?

Exploratory analysis is valuable, but the reporting language must be disciplined. Prefer “indicator,” “lead,” “pattern,” or “hypothesis” until follow-up confirms the issue against criteria and source evidence.

## Practical rule

If the audit report would say “the control failed because...,” the analysis must be confirmatory or converted into a confirmatory follow-up test. If the output only suggests where to look next, label it exploratory.

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

# Application Examples

The examples below show how the same audit area can produce different question types. The labels matter because they affect what the result can be used for.

## Expense reports

| Type | Better audit question | Typical use | Caution |
| --- | --- | --- | --- |
| Confirmatory | Were all expense reports above CHF 1,000 approved by an authorized manager within 48 hours? | Control testing or exception testing | Requires reliable approval timestamp, approver role, and population completeness. |
| Exploratory | Which expense categories, submitters, or timing patterns show unusual exception rates? | Planning, scoping, sample selection | Patterns are leads, not findings, until validated. |
| Causal | Did implementation of automated expense checks reduce policy violations compared with the prior period or a comparable group? | Evaluation of process/control change | Needs comparison logic and controls for volume, policy, and user-mix changes. |
| Non-causal | How are expense amounts and processing times distributed by category, country, and department? | Process understanding and risk assessment | Describes concentration; does not explain why it occurs. |

## Inventory management

| Type | Better audit question | Typical use | Caution |
| --- | --- | --- | --- |
| Confirmatory | Were high-priority items replenished within 24 hours after reaching the reorder point? | Control testing | Requires accurate reorder-point, priority, stock-level, and replenishment timestamps. |
| Exploratory | Which product/location combinations show unusual stockout or adjustment patterns? | Planning and follow-up targeting | Outliers may reflect seasonality, product lifecycle, or data-entry practices. |
| Causal | Did RFID implementation improve inventory accuracy compared with similar locations without RFID? | Evaluation of intervention effect | Needs a credible comparison group and stable accuracy measurement. |
| Non-causal | How do inventory adjustments vary by location, product group, and adjustment reason? | Population understanding and risk assessment | Shows where differences exist, not what caused them. |

## High-value transactions

| Type | Better audit question | Typical use | Caution |
| --- | --- | --- | --- |
| Confirmatory | Were all transactions above CHF 50,000 approved before payment by an authorized approver who was not the requester? | Control testing or full-population exception testing | Requires approval hierarchy, requester, approver, payment date, and approval timestamp. |
| Exploratory | What timing, approver, requester, vendor, or business-unit patterns appear in high-value transactions? | Risk-based sample selection | Avoid implying fraud or control failure from pattern detection alone. |
| Causal | Did the new multi-level approval workflow reduce unauthorized or late approvals? | Assessment of control-design change | Needs pre/post design, comparison logic, and stable exception definitions. |
| Non-causal | How do high-value transactions flow through departments, approver roles, and payment channels? | Process understanding and bottleneck/risk identification | Flow analysis does not prove root cause. |

## Access management

| Type | Better audit question | Typical use | Caution |
| --- | --- | --- | --- |
| Confirmatory | Were terminated users disabled within the required timeframe across all in-scope applications? | Access control testing | Requires reliable HR termination dates, user mapping, system logs, and scope definition. |
| Exploratory | Which systems, roles, or user groups show unusual access-change patterns? | Planning or deep-dive selection | Unusual activity may reflect project work, migrations, or support accounts. |
| Causal | Did automated deprovisioning reduce late access removals? | Evaluation of control automation | Needs pre/post and comparison logic; system migrations can confound results. |
| Non-causal | How many privileged accounts exist by system, owner, role, and last-login date? | Risk assessment and inventory understanding | Descriptive inventory does not prove inappropriate access. |

## How to use these examples

A practical workflow is:

1. Start with the audit objective and risk.
2. Draft the confirmatory question if a rule or control expectation exists.
3. Use exploratory questions to understand where risk may be concentrated.
4. Treat causal questions as optional and higher burden.
5. Use non-causal descriptive analysis to explain the population and support scoping.
6. Apply the evidence-quality gate before relying on results for conclusions.

# Exploratory Data Analysis in Auditing

Exploratory data analysis (EDA) is useful in internal audit, but it should not be treated as a shortcut to findings. Its main role is to understand the population, expose data-quality issues, and generate better questions.

## Useful EDA activities

- Profile the population: row counts, periods, entities, transaction types, amounts, statuses, and owners.
- Check data quality: missing values, duplicates, invalid dates, unexpected categories, and inconsistent identifiers.
- Understand distributions: amount ranges, processing times, exception rates, and concentration by business unit or owner.
- Identify outliers and anomalies: unusual timing, amounts, frequencies, relationships, or sequences.
- Compare groups: business units, systems, vendors, approvers, product groups, or geographies.
- Refine later tests: convert interesting patterns into confirmatory follow-up questions.

## Audit value of EDA

EDA can help auditors:

- avoid requesting the wrong fields;
- identify data-quality limitations early;
- refine scope and sample selection;
- detect unexpected risk indicators;
- challenge process-owner narratives; and
- decide whether full-population testing is feasible.

## Discipline required

EDA outputs should usually be labelled as planning insight, risk indicator, or follow-up lead. To become audit evidence, an EDA pattern must be connected to a criterion, validated against reliable data, and tested with a reproducible procedure.

# Practical Value and Limitations

The four question types create value in different ways.

| Question type | Primary audit value | Main limitation |
| --- | --- | --- |
| Confirmatory | Supports assurance over known risks, controls, policies, or thresholds. | Can create false comfort if the rule, data, or population is wrong. |
| Exploratory | Reveals patterns, anomalies, and emerging risks that were not obvious at planning. | Generates leads; does not by itself prove control failure or root cause. |
| Causal | Helps assess whether a change or intervention likely affected an outcome. | Requires stronger design, comparison logic, and specialist review. |
| Non-causal | Describes populations, relationships, distributions, process flows, and concentrations. | Shows what is happening, not why it is happening. |

In many internal audits, the strongest practical sequence is:

1. Use non-causal EDA to understand the population.
2. Use exploratory analysis to identify risk indicators and refine scope.
3. Convert the highest-value leads into confirmatory tests.
4. Use causal analysis only when the audit objective genuinely requires an intervention-effect conclusion and the data/design can support it.

This keeps the audit evidence trail clear: broad exploration informs targeted testing; targeted testing supports conclusions.

# Conclusion and Working Rule

Question design is a core audit analytics control. Before requesting data or writing scripts, auditors should know what type of question they are asking and what the answer can legitimately support.

Working rule:

> If the output will support an audit conclusion, define a confirmatory test against clear criteria. If the output only helps decide where to look next, label it exploratory. If the wording implies cause and effect, raise the evidence bar or rewrite the conclusion as non-causal.

Use the four labels as a practical discipline:

- **Confirmatory**: tests a defined expectation.
- **Exploratory**: generates leads and hypotheses.
- **Causal**: evaluates whether an intervention or exposure changed an outcome.
- **Non-causal**: describes patterns, distributions, relationships, flows, or exceptions.

The point is not classification for its own sake. The point is to prevent overclaiming and to connect each analysis to the right audit use: planning, sample selection, control testing, stakeholder discussion, or reportable finding.

# References

- Card, D., Min, Y., & Serghiou, S. (2021). *Open, rigorous and reproducible research: A practitioner's handbook*. Stanford Data Science. https://stanforddatascience.github.io/best-practices/
- The Institute of Internal Auditors. *Global Internal Audit Standards*. https://www.theiia.org/en/standards/2024-standards/global-internal-audit-standards/
- Richard, D. (2023). *Internal Audit Data Analytics for Beginners*. ISACA. https://www.isaca.org/resources/news-and-trends/industry-news/2023/internal-audit-data-analytics-for-beginners
- ISACA. (2023). *Seven Steps to Empowerment With Data Analytics*. https://www.isaca.org/resources/news-and-trends/newsletters/atisaca/2023/volume-34/seven-steps-to-empowerment-with-data-analytics
- University of Washington Interactive Data Lab. *Visualization Curriculum*. https://idl.uw.edu/visualization-curriculum/
