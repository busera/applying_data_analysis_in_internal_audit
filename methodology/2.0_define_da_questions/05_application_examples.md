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
