# Lecture Notes to Study Pack

**SCSE4041 Prompt Engineering Mini-Project · Problem Pool C2 · Milestone 2**

**Project title:** Lecture Notes to Study Pack: A Prompt-Engineering Workflow for Exam Revision

Team **Fluxbit** · Team ID **PE-B65-04** · Batch **B65-80**

- Team leader: Umesh Sharma — S24CSEU2483
- Team member: Anuj Sharma — S24CSEU2472
- Faculty name supplied: Saonal Kukreja

## Repository and prototype

- Public GitHub repository: https://github.com/umeshsharmabu/Lecture-Notes-to-Study-Pack
- Prototype source: [index.html](./index.html)
- GitHub Pages URL: not yet enabled or verified. To publish, open Settings → Pages, choose Deploy from a branch, select `main` and `/(root)`, then test the generated URL in a private browser window.

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

## Model and test disclosure

The report records manual prompt runs with ChatGPT (GPT-6). Milestone 1 proposed Google AI Studio; the change is disclosed rather than claiming Gemini runs that were not performed. The 12-case matrix records 11 passes and one failure: two questions at Hard difficulty remained recall-level despite being source-grounded. This is a small preliminary test set, not an independently replicated benchmark.

## Privacy and limitations

Use only academic material the team is authorized to use. Do not enter personal, confidential or restricted information. AI-generated material may be wrong or incomplete; verify it against the original notes. The workflow supports revision and does not guarantee exam performance.

## Submission items still requiring team action

The GitHub repository is public. The GitHub Pages prototype link, actual member contribution tasks/evidence/agreed percentages, and 90–150 second public reel still need completion and verification. The two PDF deliverables and three PNG captures remain in the local working ZIP; this repository contains text extracts and SVG diagrams, not those original binary assets.
