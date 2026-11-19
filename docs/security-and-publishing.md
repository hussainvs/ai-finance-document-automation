# Security and Publishing Checklist

## Keep private

- n8n credentials, API keys, OAuth tokens, cookies, private keys and `.env` files.
- Real invoices, receipts, customer details, personal email addresses and real financial ledgers.
- Private n8n editor URLs/workflow IDs, Google Drive folder IDs, spreadsheet IDs and internal account identifiers when they expose private resources.
- Raw execution payloads that contain document content or credentials.

## Before adding workflow JSON

1. Export the workflow from n8n.
2. Open the JSON as text and search for tokens, private URLs, email addresses, real file names, IDs and document content.
3. Replace Drive and Sheets IDs with obvious placeholders such as `REPLACE_WITH_TEST_FOLDER_ID`.
4. Remove credential blocks/references where they reveal account-specific names or IDs; document which credentials the user must create in their own workspace.
5. Confirm all nodes point to test folders and a test spreadsheet, never the live ledger.
6. Test the sanitized workflow in a separate test workspace before public publishing.

## Before making the repository public

- Review every changed file with `git diff --stat` and a text search for `token`, `secret`, `password`, `authorization`, `@`, private Google links and workspace IDs.
- Check CSVs for actual invoice contents and personal data.
- Keep account-specific runbooks and unsanitized exports out of the public repo.
- If a secret was committed, revoke/rotate it; deleting the file in a later commit is not enough.

This repository is a portfolio prototype and is not a certified bookkeeping or accounting system.
