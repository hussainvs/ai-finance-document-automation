# Workflow exports (not included yet)

This public starter does not contain raw n8n exports yet. When the owner is ready, add **sanitized** JSON exports here:

- `finance-document-processing.sanitized.json` — QA finance workflow, with all account-specific IDs replaced.
- `qa-evaluator.sanitized.json` — evaluator workflow, with private data table and Drive/Sheets IDs replaced.
- `human-review-subworkflow.sanitized.json` — review subworkflow, with mailbox and Drive references replaced.

Before adding any export, follow `../docs/security-and-publishing.md`. Search the JSON as text for secrets, credentials, private URLs, email addresses, Drive/Sheet IDs, actual filenames and embedded execution data. Replace IDs with explicit placeholder strings. Do not include credentials or live client data. Test the sanitized workflow in a fresh test workspace before public publishing.
