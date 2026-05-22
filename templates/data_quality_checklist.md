# Data Quality Checklist

## Receipt checks

- File/table received from expected source.
- Period matches request.
- Row count matches source-owner expectation or reconciliation report.
- Field list matches request.
- File format can be opened and processed.

## Completeness checks

- Required fields are present.
- Key identifiers are populated.
- Date fields cover expected period.
- No unexpected filters are visible.
- Population reconciles to source report where possible.

## Validity checks

- Date formats are valid.
- Numeric fields parse correctly.
- Categorical values are understood.
- Key fields are unique where expected.
- Duplicates are identified and explained.

## Reasonableness checks

- Values fall within plausible ranges.
- Outliers are flagged, not automatically removed.
- Missing values are quantified.
- Transformation row counts are tracked.
- Exceptions are reviewed with business context.

## Documentation

- Validation procedures documented.
- Limitations recorded.
- Data owner questions logged.
- Final usable dataset version identified.
