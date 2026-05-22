# Analytics Evidence Quality Gate

Use this gate after analysis has been performed and before relying on the output for audit planning, control testing, stakeholder communication, or reportable findings.

The use-case decision gate asks: **Is this worth analyzing?**

This evidence-quality gate asks: **Can we trust and use the result?**

## Evidence-quality criteria

| Criterion | Strong signal | Weak signal | Decision impact |
| --- | --- | --- | --- |
| Population completeness | The extract reconciles to a source-system report, expected row count, control total, or independently obtained population listing. | The population may be incomplete, filtered unexpectedly, duplicated, or missing relevant entities or periods. | Do not conclude on the full population until completeness is resolved. |
| Key field accuracy | Fields used in the logic are understood, mapped to source-system definitions, and spot-checked against source records. | Field meaning is ambiguous, transformed without explanation, or not traceable to source records. | Validate field definitions and sample records before relying on exceptions. |
| Logic validity | The script or query implements the audit rule exactly as intended and has been reviewed. | The logic is difficult to explain, unreviewed, or only approximately aligned to the control expectation. | Review and correct logic before using outputs as audit evidence. |
| Exception validation | Exceptions have been checked for false positives, timing issues, master-data changes, or legitimate business explanations. | The output is treated as a finding without validating whether exceptions are real. | Use results for follow-up only until exceptions are validated. |
| Reproducibility | Inputs, transformations, scripts, parameters, dates, row counts, and outputs are documented well enough to rerun or review. | The result depends on manual steps, undocumented filters, or overwritten files. | Improve documentation before relying on the result. |
| Limitations and uncertainty | Known data gaps, assumptions, exclusions, and residual uncertainty are documented. | Limitations are unknown or omitted from the interpretation. | Restrict the conclusion or disclose the limitation. |
| Review and sign-off | A knowledgeable reviewer has checked the data, logic, output, and interpretation. | Only the analyst has reviewed the result. | Obtain review before communicating conclusions. |

## Evidence-use outcomes

| Outcome | Use when | Permitted use |
| --- | --- | --- |
| Reliable for audit evidence | Population, fields, logic, exceptions, reproducibility, and review are strong. | Support control testing, audit conclusions, or reportable findings. |
| Reliable for planning | Some limitations remain, but the direction is useful and the risk of overstatement is controlled. | Support planning, scoping, risk assessment, or sample selection. |
| Follow-up required | Exceptions or logic are plausible but not validated. | Use as a lead list for inquiry or additional testing. |
| Exploratory insight only | The analysis is useful for learning or hypothesis generation but lacks a reliable rule or validated population. | Use for discussion or planning hypotheses only. |
| Do not use | Population, field accuracy, logic, or confidentiality issues undermine reliance. | Do not use for audit conclusions; redesign the procedure. |

## Minimum evidence pack

For any analysis that may support audit work, preserve enough evidence for another auditor to understand and challenge the result:

- Audit objective, risk, control expectation, and population.
- Data source, extraction date, period covered, and source owner.
- Requested fields and rationale for each field.
- Row counts before and after cleansing or filtering.
- Completeness and accuracy checks performed.
- Script, query, notebook, or documented manual steps.
- Exception logic and thresholds.
- Output file or table with generation date.
- Exception validation notes and false-positive handling.
- Limitations, assumptions, and reviewer sign-off.

## Example: payment approval testing

An output showing 42 late approvals is not automatically an audit finding.

Before reporting, check:

1. Does the payment population reconcile to the source payment report?
2. Is “approval timestamp” the final approval, first approval, or workflow update timestamp?
3. Are payment dates and approval timestamps in the same timezone?
4. Were any emergency approvals, delegated approvals, or retroactive workflow migrations allowed by policy?
5. Were sampled exceptions traced back to source records?
6. Did a reviewer confirm that the script reflects the control expectation?

If those checks are strong, the output may support control testing or a finding. If not, it is a lead list for follow-up, not a conclusion.
