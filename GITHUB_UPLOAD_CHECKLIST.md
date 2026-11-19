# GitHub Upload Checklist

## This package's current state

- [x] README and project docs included.
- [x] Latest QA baseline is accurately stated as 19/25 PASS, 6 FAIL, 0 incomplete (76%).
- [x] Cases 18–20 are identified as higher priority without reclassifying them as passes.
- [x] 100-case matrix has 100 planned rows; fixture status is `PLANNED_NOT_GENERATED` and execution status is `NOT_RUN`.
- [x] Time savings are labeled as assumption-based estimates.
- [x] Human review is called out in the screenshot and recording instructions.
- [ ] Real workflow screenshots captured and sanitized.
- [ ] Demo recording captured, checked and linked.
- [ ] Sanitized n8n workflow JSON exports added.
- [ ] Test fixtures are synthetic and included, if safe to publish.
- [ ] Repository name/visibility confirmed before first push.

## Before public upload

- [ ] Scan every file for credentials, private IDs/URLs, emails, real client data and raw execution data.
- [ ] Do not include the internal employer pack or account-specific runbooks.
- [ ] Do not upload Google Sheets or n8n credentials. Link a public-safe demo only if explicitly made shareable and scrubbed.
- [ ] Review the final diff before committing.

## Later, when adding workflows and spreadsheets

1. Export n8n workflows as JSON and sanitize them using `docs/security-and-publishing.md`.
2. Put sanitized JSON files under `workflows/` with a `README.md` explaining required credential placeholders and test resources.
3. Do not upload a live Google Sheet file. Create synthetic sample CSVs under `samples/`; keep the real QA workbook private.
4. Save evaluator summary CSV/JSON under `evidence/` after an actual run. Preserve prior reports; do not rewrite the old result to match a new result.
