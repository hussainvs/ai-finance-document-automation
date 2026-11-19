# QA Results and Findings

**Baseline:** 2026-11-18 saved evaluator run, reviewed 2026-11-19.  
**Strict result:** **19/25 PASS (76%), 6 FAIL, 0 INCOMPLETE**.

The full 25-case summary is in [`../evidence/qa-summary.csv`](../evidence/qa-summary.csv).

## Prioritization (not a score change)

| Priority | Cases | Count | Finding |
|---|---|---:|---|
| P1 — duplicate / ledger-integrity | 018–020 | 3 | Historical QA finance rows overlap later review logs; clean retest is needed to attribute behavior to a specific run |
| P2 — route / extraction | 006, 008, 025 | 3 | Conservative review routing, vendor label mismatch and category mismatch |

This severity split does **not** change the strict evaluator count. The observed baseline remains 19/25 with six mismatches. Do not report 22/25 passing based on severity reclassification alone.

## State contamination evidence

The QA expense sheet contained older rows linked to Case 18, 19 and 20 documents; a later review log also recorded them as Pending Review. Those timestamps demonstrate mixed historical state, not proof that the latest processing attempt created each older row.

## Retest method

1. Back up the QA workbook and all QA Data Tables.
2. Verify and remove only confirmed stale synthetic ledger rows from the QA copy, preserving append-only logs.
3. Run the seed document first and check exactly one canonical row.
4. Run duplicate/conflict/near-match cases individually and capture row deltas, final folders and timestamps.
5. Re-evaluate with a new run ID and retain both old and new reports.

## What is not proven yet

- A clean duplicate/conflict regression.
- A successful 100-document run.
- Measured time saved.
- Production readiness.
