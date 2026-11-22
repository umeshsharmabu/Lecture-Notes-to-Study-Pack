# Lecture Notes to Study Pack

**SCSE4041 Prompt Engineering Mini-Project **

## Repository and prototype

- Public GitHub repository: https://github.com/umeshsharmabu/Lecture-Notes-to-Study-Pack
- Prototype source: [index.html](./index.html)
- GitHub Pages URL: https://umeshsharmabu.github.io/Lecture-Notes-to-Study-Pack/ <img width="468" height="41" alt="image" src="https://github.com/user-attachments/assets/12a5b57a-9499-4949-9b40-16b876e4726c" />


## Run the prototype locally

Open `index.html` in a modern browser. Enter a subject, difficulty, MCQ count (1–15) and authorized lecture-note text. Copy each prepared prompt into the selected model and paste the actual response into the corresponding output field. Run P1, then P2, then P3. Export the session JSON to retain the prompts, source notes and pasted model outputs.

**Implementation disclosure:** this is a static, human-in-the-loop prompt runner. It does not call an LLM API, use a backend/database, or store API keys. Model execution is external and manual. The "Load sample" action loads notes/settings only; it does not prefill model outputs.

## Three-prompt pipeline

- **P1 — Summary and Key Terms:** organizes source notes by topic, extracts terms, copies formulas exactly, and flags gaps.
- **P2 — MCQs and Answer Key:** generates up to the requested number of source-supported four-option MCQs with explanations and exact source quotes.
- **P3 — Grounding Audit:** checks summary/key-term claims, formulas, MCQ support, answer uniqueness and answer-key correctness against the notes.

## Repository map

- `prompts/v1/`, `prompts/v2/`, `prompts/v3/`: saved prompt versions.
- `prompts/final/`: final P1, P2 and P3 prompt templates.
- `code/index.html`: prototype implementation; root `index.html` is the GitHub Pages entry point.
- `test-data/`: sample notes, test matrix, edge/invalid cases and manual-run notes.
- `docs/diagrams/`: editable SVG workflow and architecture diagrams.
- `docs/`: report text extracts, supporting-document text extract, form answer sheet, reel script and submission checklist.
- `CHANGELOG.md`: dated changes.

