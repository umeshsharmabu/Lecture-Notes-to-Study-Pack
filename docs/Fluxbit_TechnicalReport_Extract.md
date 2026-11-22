# Fluxbit Technical Report — Text Extract

The original two-page PDF and editable DOCX remain in the local working ZIP. This is the extracted text for repository readability.

<PARSED TEXT FOR PAGE: 1 / 2>
                                                                         SCSE4041 | Supporting Document | Technical Report
                                             TECHNICAL REPORT


                    Lecture Notes to Study Pack
                        SCSE4041 Prompt Engineering Mini-Project | Problem Pool C2
  Team ID: PE-B65-04 | Team leader: Umesh Sharma (S24CSEU2483) | Member: Anuj Sharma (S24CSEU2472) |
                                              Faculty: Saonal Kukreja

                                        Team name: Fluxbit | Batch: B65-80


1. Problem and objective
University students spend time converting lecture notes into concise revision material. Manual preparation can
be slow, while generic AI prompts can omit concepts, introduce unsupported statements, or create ambiguous
questions. This project designs a repeatable prompt workflow that uses only the supplied lecture notes to create
a topic-wise summary, key terms, formulas, multiple-choice questions (MCQs), answer explanations and a
source-grounding audit.


2. Architecture and tools
The prototype is a static HTML browser interface. It collects the subject, difficulty, requested MCQ count and
lecture notes; substitutes these values into three prompt templates; and provides copy/paste areas for the real
model outputs. The workflow is intentionally human-in-the-loop: the user runs each prompt in an external
model interface and pastes the full response back into the browser. The local page has no backend, database,
API key or remote storage.

The three prompts are P1 (Summary and Key Terms), P2 (MCQs and Answer Key) and P3 (Grounding Audit). P1
creates source-organized material, P2 generates up to the requested number of questions with exact source
quotes, and P3 checks claims, formulas, options and answer keys against the notes. The UI validates empty input
and constrains the MCQ count to 1-15.

Model disclosure: Milestone 1 proposed Google AI Studio as the primary tool. The manual test runs documented
for this draft were executed with ChatGPT (GPT-6), which was available for the build. This tool change is
disclosed; the prompts are model-agnostic and may be re-run in Gemini/Google AI Studio, but the final Q9
answer and evidence must identify the model actually used.


3. Prompt design and evaluation
The final workflow separates generation from verification. It places source notes inside explicit delimiters and
treats embedded instructions as data, not commands. P2 must create no more questions than the source
supports and includes a short exact quote for each answer. P3 returns PASS only if no unsupported factual
claims or answer-key errors remain; otherwise it returns NEEDS FIXES.

Three purposeful versions are retained: v1 reproduces the Milestone 1 single-prompt baseline; v2 adds
structured sections, difficulty and a variable question count; v3 decomposes the task into P1, P2 and P3. The 5-
versus-10 question-count inconsistency in the Milestone 1 materials is handled by the explicit {num_questions}
variable, bounded to 1-15.




                                     Fluxbit | Supporting Technical Report | Page 1
<PARSED TEXT FOR PAGE: 2 / 2>
                                                                        SCSE4041 | Supporting Document | Technical Report

4. Test results
Twelve test scenarios were recorded: normal inputs across OS scheduling and DBMS normalization; formula
preservation; hard difficulty; sparse notes; contradictory notes; Hinglish notes; garbled notes; embedded
prompt injection; empty input; non-academic input; and a 100-question request. Eleven passed and one failed.
The failure was difficulty calibration: two questions requested at Hard remained recall-level, although they
were grounded in the notes. The contradiction and sparse-input cases were surfaced rather than silently
guessed.


5. Limitations and next steps
   Difficulty is not yet calibrated by an independent rubric; add a question-complexity checklist and human
    scoring.
   LLM execution is manual and depends on the operator copying complete prompts and outputs; an API
    integration would require team-owned credentials and deployment.
   Test observations are manual prompt-workflow runs, not automated API integration tests; re-run on the
    final selected model and retain raw outputs.
   Only a small synthetic note set has been included; add more authorized course-note samples and a second
    reviewer before claiming general performance.


6. Responsible use
Use only academic materials the team is authorized to use. Do not submit confidential or personal information.
AI-generated summaries and answer keys may be incomplete or wrong; students must verify all content against
the original notes. The workflow supports revision and does not guarantee exam performance.


References
OpenAI Help Center, “Best practices for prompt engineering with the OpenAI API”:
https://help.openai.com/en/articles/6654000-best-practices-for-prompt-engineering-with-the-openai-api

OpenAI, “Prompt engineering”: https://developers.openai.com/api/docs/guides/prompt-engineering

Google NotebookLM Help: https://support.google.com/notebooklm/




                                    Fluxbit | Supporting Technical Report | Page 2