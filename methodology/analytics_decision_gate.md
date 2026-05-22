# Analytics Decision Gate

Use this gate before investing time in data extraction, cleansing, scripting, or visualization. Internal audit data analysis is strongest when the audit question, expected behavior, and usable data are aligned.

## Decision criteria

| Criterion | Strong signal | Weak signal | Decision impact |
| --- | --- | --- | --- |
| Business process and risk clarity | The process, risk, control objective, and population are understood. | The audit team is still unclear what risk or control is being tested. | Clarify scope before requesting data. |
| Bright-line rule or measurable expectation | There is a policy threshold, approval rule, expected sequence, timing requirement, or known risk indicator. | The question is broad, subjective, or cannot be translated into observable data fields. | Narrow the question or treat the work as exploratory. |
| Data availability and usability | Source systems, fields, owners, extraction method, and expected row counts are known. | Data access is uncertain, fields are missing, or quality is unknown. | Run a small feasibility check before full analysis. |
| Audit value | The result can improve assurance, planning, risk assessment, or stakeholder insight. | The output would be interesting but not useful for audit conclusions or decisions. | Do not pursue unless it supports learning or planning. |
| Confidentiality and proportionality | The data requested is necessary and can be handled securely. | The request collects more sensitive data than needed. | Minimize, mask, or use synthetic data where possible. |

## Recommended decision outcomes

| Outcome | Use when | Next action |
| --- | --- | --- |
| Proceed | Criteria are mostly strong. | Request data and define validation checks. |
| Narrow scope | The idea is promising but too broad. | Reduce the population, question, or data fields. |
| Feasibility first | Data access or quality is uncertain. | Request a small extract or metadata sample. |
| Exploratory only | No reliable threshold exists, but patterns may inform planning. | Label outputs as hypothesis-generating, not audit findings. |
| Stop | Audit value is weak or data risk is disproportionate. | Use another audit procedure. |

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
