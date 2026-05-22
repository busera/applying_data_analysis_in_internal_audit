# Analytics Use-Case Decision Gate

Use this gate before requesting data or writing scripts. Its purpose is narrow: decide whether a proposed audit question is suitable for data analysis.

This is not the evidence-quality gate. It answers: **Is this worth analyzing?** A separate evidence-quality gate answers: **Can we rely on the analytical result?**

## What this gate does

A proposed analytics use case should pass five checks before the audit team invests time in extraction, cleansing, scripting, or visualization:

1. The audit question is clear.
2. The expected behavior can be measured or observed.
3. The required data is likely available and usable.
4. The output would support audit planning, testing, assurance, or reporting.
5. The data request is proportionate and can be handled securely.

## Decision criteria

| Criterion | Strong signal | Weak signal | Decision impact |
| --- | --- | --- | --- |
| Audit question clarity | The audit objective, risk, control expectation, and population can be stated clearly. | The audit team is still asking broad questions such as “Can we analyze purchases?” or “Can we find suspicious activity?” | Clarify the audit objective and scope before requesting data. |
| Measurable rule or observable pattern | There is a policy threshold, approval rule, expected sequence, timing requirement, master-data flag, relationship, or known risk indicator. | The question is subjective or cannot be translated into fields, dates, statuses, amounts, or relationships. | Narrow the question or treat the work as exploratory. |
| Data feasibility | Source systems, fields, owners, extraction method, and expected row counts are known or can be confirmed quickly. | Data access is uncertain, required fields may not exist, or quality is unknown. | Run a small feasibility check before full analysis. |
| Audit value | The result could change audit planning, sample selection, control testing, assurance conclusions, stakeholder discussion, or reporting. | The output would be interesting but would not influence audit work. | Do not pursue unless it supports learning or planning. |
| Confidentiality and proportionality | The data requested is necessary, limited to the purpose, and can be handled securely. | The request collects more sensitive data than needed or creates unnecessary privacy/security risk. | Minimize fields, mask where possible, or use synthetic data for demonstration. |

## Decision outcomes

| Outcome | Use when | Next action |
| --- | --- | --- |
| Proceed | The question is clear, measurable, valuable, and data appears feasible. | Request data and define validation checks. |
| Narrow scope | The idea is promising but too broad. | Reduce the population, period, question, or required fields. |
| Feasibility first | The question is valid but data access, completeness, or field meaning is uncertain. | Request metadata, a field list, row counts, or a small extract before full analysis. |
| Exploratory only | No reliable rule or threshold exists, but pattern-finding may inform planning. | Label outputs as hypothesis-generating, not audit findings. |
| Stop | Audit value is weak or data risk is disproportionate. | Use another audit procedure. |

## Example: from vague idea to analyzable question

Weak question:

> Can we identify high-risk vendor payments?

This is too broad. It does not define the population, expected behavior, data fields, or how the result would be used.

Better question after applying the gate:

> For vendor payments above CHF 50,000, identify cases where approval occurred after the payment date, the approver was not in the authorized approver list, or the requester and approver were the same person.

This is suitable for analysis because it defines:

- Population: vendor payments above CHF 50,000.
- Expected behavior: approval before payment by an authorized approver with segregation of duties.
- Required fields: payment date, amount, requester, approver, approval timestamp, approval status, approver role, and authorization list.
- Exception logic: late approval, unauthorized approver, or same requester/approver.
- Audit use: risk-based sample selection, control testing, or stakeholder discussion.

## Questions to ask before requesting data

1. What audit objective does this analysis support?
2. What risk or control expectation is being tested or explored?
3. What population should be complete?
4. What would count as an exception, anomaly, trend, or relevant pattern?
5. Which fields are required, and why?
6. Which fields are sensitive or unnecessary?
7. How will completeness and accuracy of the extract be validated?
8. What output would change audit planning, testing, or reporting?
9. What limitations would need to be disclosed?
10. Who needs to review the interpretation before communication?

## Link to the four-phase methodology

This gate belongs in Phase 1 before full data request and acquisition. If the answer is “feasibility first,” run a small Phase 2 validation loop before building Phase 3 scripts.

After analysis is performed, use the [Analytics Evidence Quality Gate](./analytics_evidence_quality_gate.md) before relying on the output for planning conclusions, control testing, or reportable findings.
