# Screenshot Guide for the Portfolio

Capture these from the **real connected n8n workspace**. Use synthetic QA data. Do not use generated mock screenshots as if they were real application evidence. Crop or hide browser URLs, private workflow IDs, spreadsheet IDs, email addresses and credentials.

## Recommended public screenshots

1. **`01-finance-workflow-overview.png` (required):** zoomed-out QA Finance workflow canvas, showing intake, extraction, validation, ledger/review branches and file movement. Use the QA copy rather than screenshots of both main and QA copies; the two are similar.
2. **`02-validation-duplicate-check.png` (required):** close-up of `Check Data Quality`, `Find Existing Invoice` and `Decide Next Step`. Ensure expressions, credentials and private values are not readable.
3. **`03-human-review-workflow.png` (required):** Human Review subworkflow canvas showing `Ask Human to Review`, `Human Decision`, ledger/rejection branches and folder movement.
4. **`04-qa-evaluator-overview.png` (required):** evaluator canvas showing manifest/ground truth reads, finance/Drive/email inspection, comparison and test-log output.
5. **`05-finance-output-synthetic.png` (recommended):** income or expense sheet with clearly synthetic example records; hide private links and irrelevant rows.
6. **`06-qa-results-19-of-25.png` (required):** actual evaluator summary showing 19 PASS, 6 FAIL, 0 incomplete (76%). Do not edit the counts in the screenshot.
7. **`07-human-review-email.png` (optional):** a synthetic review notification with the reason visible. Do not expose personal email addresses.

## How to capture

- Maximize the browser, close irrelevant tabs and adjust canvas zoom.
- Use Windows Snipping Tool (`Win + Shift + S`) for screenshots.
- Keep the cursor away from node labels. Capture full canvas for overviews and a closer crop for logic-heavy nodes.
- Save the images to `docs/assets/screenshots/` and update the README links only after real images exist.
- If one canvas is too large to read, take a full overview plus one close-up instead of shrinking text to unreadable size.

## What to omit

- API keys, OAuth tokens, authorization headers or credential selectors.
- Private n8n workspace/workflow IDs or editor URLs when these reveal account-specific resources.
- Private Google Drive/Sheets IDs, personal email addresses and real financial records.
- The raw data table unless it contains only safe synthetic values.
