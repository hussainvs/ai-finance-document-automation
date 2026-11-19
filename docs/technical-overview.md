# Technical Overview

## Components

### 1. Document intake

A Drive folder acts as the unprocessed queue. A sort step is intended to make the processing order stable and easier to reproduce in QA. Supported PDFs and common images enter the extraction pipeline; unsupported formats are routed for review rather than trusted as invoices.

### 2. Extraction and normalization

PDF text extraction and image/vision paths supply content for structured field extraction. Target fields include transaction direction, party/vendor or client, invoice number, date, category, amounts/tax and payment status. Model output should be treated as a proposal, not as the source of truth.

### 3. Deterministic validation

Validation checks required fields, whether the transaction direction is clear, and whether the extracted information is sufficiently usable to proceed. Missing or ambiguous critical fields should route to human review without silently creating a finance row.

### 4. Duplicate/conflict detection

The prototype looks up existing finance records before posting. Correct behavior requires two properties:

- **Duplicate prevention:** matching invoice submissions must not create additional ledger rows.
- **Near-match precision:** a legitimate invoice with a different invoice number must not be blocked simply because vendor and amount look similar.

Case 18–20 evidence is currently mixed with historical finance rows, so this behavior needs a clean regression run.

### 5. Ledger and document state

Accepted income and expense items are written to their appropriate sheets and the file is moved to Processed. Items requiring review are logged and routed to Needs Review. A core invariant to validate is that a document routed to review/rejection does not also receive a newly committed ledger row in the same run unless an explicit human approval step authorizes it.

### 6. QA evaluator

A separate evaluator loads a manifest and expected outcomes, then inspects finance sheets, Drive folders and reviewer-email/log evidence. It compares observed state to each case's pass criteria and appends test results. Evaluator success means that the evaluator ran; it does not imply all test cases passed.

## Reliability principles

- Keep Ground Truth read-only.
- Record before/after ledger row counts.
- Use a stable case ID for every fixture.
- Use idempotent or duplicate-safe writes wherever possible.
- Make retries observable and bounded.
- Keep historical test logs; do not rewrite previous test outcomes.
- Distinguish execution success from business correctness.
