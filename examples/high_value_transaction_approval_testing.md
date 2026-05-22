# High-Value Transaction Approval Testing

This worked example shows how an audit team can turn a control expectation into a reproducible analytical test.

## Audit objective

Assess whether high-value transactions were approved by an authorized manager before payment or posting.

## Risk and control expectation

Risk: high-value transactions may be processed without appropriate review, increasing the risk of unauthorized payments, fraud, or policy non-compliance.

Control expectation: transactions above the defined threshold require documented approval by an authorized manager before the transaction is completed.

## Analytics use-case decision gate

| Question | Example answer |
| --- | --- |
| Is the process and risk clear? | Yes. The process is transaction approval before posting/payment. |
| Is there a measurable rule? | Yes. Amount threshold, approval role, and approval timestamp. |
| Is data available? | Usually from ERP payment tables, workflow logs, and user/role master data. |
| Is the output useful? | Yes. Exceptions can support targeted testing and follow-up. |
| Are confidentiality risks manageable? | Yes, if fields are minimized and sensitive vendor/person fields are masked where possible. |

## Required data fields

| Field | Purpose |
| --- | --- |
| transaction_id | Unique transaction key. |
| transaction_date | Period and sequence testing. |
| payment_or_posting_date | Determines whether approval occurred before completion. |
| amount | Threshold testing. |
| currency | Threshold normalization if multiple currencies exist. |
| requester_id | Process context. |
| approver_id | Approval evidence. |
| approval_timestamp | Sequence testing. |
| approval_status | Confirms approval was granted, not rejected or pending. |
| approver_role | Validates authority. |
| delegation_flag | Identifies delegated approval cases. |

## Example exception logic

A transaction is a potential exception when:

1. Amount exceeds the approval threshold.
2. No approval record exists; or
3. Approval exists but occurred after payment/posting; or
4. Approver role was not authorized for the threshold; or
5. Approval status was not final/approved.

## Example pseudo-query

```sql
select
    transaction_id,
    amount,
    currency,
    payment_or_posting_date,
    approver_id,
    approval_timestamp,
    approval_status,
    approver_role
from transactions
where amount > 10000
  and (
      approver_id is null
      or approval_timestamp > payment_or_posting_date
      or approval_status <> 'approved'
      or approver_role not in ('manager', 'senior_manager', 'director')
  );
```

## Interpretation

Potential exceptions should be reviewed before reporting. Common false-positive causes include emergency approvals, retrospective workflow migration, approved delegations, threshold changes, or approval evidence stored in another system.

## Evidence-strength assessment

Strong evidence requires:

- Complete transaction population.
- Validated approval workflow extract.
- Current and historical role/authority mapping.
- Reproducible exception logic.
- Business review of exceptions and false positives.

If role data is stale or approval evidence is incomplete, the result may still be useful for follow-up but should not be reported as a confirmed control failure without additional evidence.
