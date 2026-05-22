# Data Governance and Reproducibility

Data analysis in internal audit should be reproducible, proportionate, and defensible. The goal is not only to produce an output, but to preserve enough evidence for another auditor to understand what was requested, received, transformed, tested, and reported.

## Confidentiality and proportionality

Before requesting or handling data, document:

- The audit objective supported by the data.
- The minimum required fields.
- Fields intentionally excluded because they are unnecessary or sensitive.
- Data classification and confidentiality requirements.
- Approved storage location.
- Access restrictions.
- Retention and deletion expectations.
- Whether masking, aggregation, or synthetic data can be used.

## Data receipt record

For each dataset, retain:

| Item | Description |
| --- | --- |
| Source system | Application, database, report, or data owner source. |
| Data owner | Person or team responsible for the data. |
| Extract date/time | When the data was generated or received. |
| Population definition | What records should be included. |
| Period covered | Start and end dates. |
| Filters applied | Any extraction filters or exclusions. |
| Row count | Number of records received. |
| Field list | Columns received and their definitions. |
| Transfer method | How the data was shared. |
| Storage location | Where the working copy is stored. |

## Transformation log

Record every material transformation:

- File or table used as input.
- Transformation step.
- Rationale.
- Script/query/notebook reference.
- Row count before and after.
- Field changes.
- Exceptions or rejected records.
- Reviewer or preparer.

## Reproducibility checklist

Before relying on the output, confirm:

- The input data can be traced to source or owner confirmation.
- The analysis file, script, or notebook is versioned.
- Package or tool versions are documented where relevant.
- Manual adjustments are visible and justified.
- Random processes use fixed seeds or are not material to the conclusion.
- Intermediate outputs can be regenerated.
- Final tables/charts can be tied back to the analysis steps.
- Assumptions and limitations are documented.

## Practical minimum standard

For each analysis, keep enough documentation to answer four questions:

1. What data did we request and receive?
2. Why was that data appropriate for the audit objective?
3. What did we do to the data?
4. Why is the output reliable enough for the intended audit use?
