# Limitations and Roadmap

## Known limitations

1. Latest strict QA baseline: 19/25 PASS (76%); six mismatches.
2. Cases 18–20 require a clean, controlled retest because historical ledger rows overlap later review-log records. They remain failures in the recorded baseline until a new run proves otherwise.
3. Cases 06, 08 and 25 have open route, vendor-normalization and category discrepancies.
4. The 100-case test matrix is planned; all 100 rows are `PLANNED_NOT_GENERATED` / `NOT_RUN`.
5. Time-saving values are estimates; manual and post-automation human handling times have not been measured with a comparable stopwatch study.
6. Any sample monthly finance report is synthetic demo content, not evidence of real agency performance.
7. The workflow is not represented as production-ready accounting software.

## Next steps

1. Export and back up all workflows, QA workbook and three QA Data Tables privately.
2. Create a clean QA state and retest the seed invoice and cases 17–20 sequentially.
3. Add a tested invariant: a document routed to review/rejection cannot create an unauthorized ledger row in the same run.
4. Resolve vendor normalization and category policy.
5. Run the 100 planned scenarios in four batches of 25, preserving input manifest and raw output evidence.
6. Measure manual handling, post-automation review/correction time, retries and automation runtime.
7. Capture and sanitize authentic workflow, human-review, finance-output and QA-result screenshots.
8. Review workflow exports and screenshots for sensitive information before public release.
