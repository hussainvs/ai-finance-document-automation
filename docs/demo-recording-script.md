# 3-Minute Project Demo Recording Script

**Goal:** demonstrate business context, workflow design, human oversight and QA evidence without rerunning the invoice processor. Use saved runs to avoid consuming model tokens or changing QA state.

## Before recording

- Use a clean browser window; hide bookmarks, unrelated tabs and private URLs.
- Confirm all displayed records are synthetic test data.
- Have these tabs ready: QA Finance workflow, Human Review subworkflow, QA Evaluator saved run, sample finance output and QA results.
- Keep the 19/25 PASS, 6 FAIL and 76% baseline visible and accurate.

## Timeline and suggested narration

### 0:00–0:20 — Problem

> “This project automates parts of invoice processing for a marketing agency. It extracts key finance fields, checks whether a document can be safely processed, and routes exceptions for human review.”

### 0:20–1:05 — Finance workflow

Show the zoomed-out QA Finance workflow, then the validation and existing-invoice lookup section.

> “The workflow handles PDF and image inputs, validates important fields, checks existing records and sends uncertain or potentially duplicate documents to a review path.”

### 1:05–1:35 — Human review

Show the Human Review subworkflow and its decision/ledger/rejection branches.

> “Human review is a separate path. The intended control is that unclear cases need a decision before they can be finalized. I also log the reason so a reviewer has context.”

Only claim a specific approval control if the actual live workflow and saved evidence support it.

### 1:35–2:15 — QA evaluator

Show the evaluator overview and the latest saved result.

> “I built a separate evaluator that compares observed spreadsheet rows, Drive locations and review evidence with expected outcomes. The latest strict baseline passed 19 of 25 cases, with six discrepancies to address.”

### 2:15–2:45 — Findings

Explain that cases 18–20 need clean-state retesting because historical rows overlap later review logs. Mention the other open routing/extraction differences without treating them as passes.

### 2:45–3:00 — Next step

> “My next milestone is a clean duplicate/conflict regression, followed by the planned 100-case test matrix and a measured time study.”

## Export settings

- Record at 1080p if the device can handle it; 720p is acceptable if node text stays readable.
- Prefer one continuous recording with simple tab transitions.
- Host the MP4 as an unlisted video or upload a short compressed clip to a private share, then link it from the README.
- Do not put private execution payloads or raw client data into the video.
