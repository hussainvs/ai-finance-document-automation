# 100-Document Regression / Load Test Plan

**Status: PLANNED, NOT RUN.** The matrix has 100 planned scenarios, but no 100-document run has been executed. Empty observed-result fields are intentional.

## Planned mix

| Group | Cases | Count |
|---|---|---:|
| Valid invoices | 001–030 | 30 |
| Image receipts | 031–045 | 15 |
| Multi-page/complex invoices | 046–055 | 10 |
| Missing required field | 056–065 | 10 |
| Ambiguous/non-invoice inputs | 066–073 | 8 |
| Exact duplicates | 074–085 | 12 |
| Invoice-number conflict / near-match | 086–093 | 8 |
| Unsupported/damaged input | 094–100 | 7 |
| **Total** | **001–100** | **100** |

## Run in four batches

Use batches of 25. After each batch record actual start/end time, number of inputs, successful routes, review routes, failures/retries, ledger-row delta, and final folder per case. Duplicate tests must start from a documented canonical seed row and be run individually.

## Acceptance invariants

- A review/rejected file must not create an unauthorized new finance row in the same run.
- An exact duplicate must not create a second row.
- A conflicting invoice number must be held for review and must not be silently posted.
- A legitimate new invoice number must not be rejected solely due to a similar vendor/amount.
- Unsupported formats must not auto-post.
- All observed row deltas must reconcile to the expected deltas or have a documented defect.

## Before publishing a result

Only fill actual result columns after real execution. Save raw evaluator JSON, CSV summary and before/after QA sheet snapshots. Never count a planned case, an incomplete case or a missing evidence row as a pass.
