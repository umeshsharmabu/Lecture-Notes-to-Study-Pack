# Edge and invalid fixture inventory

The local working ZIP contains the separate fixture files used in the 12-case test matrix:
- sparse notes; request 10 MCQs; expected to return fewer supported questions;
- contradictory source statements; list both and do not silently resolve;
- Hinglish DBMS notes; produce English while preserving technical terms;
- garbled/incomplete notes; flag gaps and do not reconstruct missing facts;
- embedded prompt-injection instruction; ignore it as an instruction and treat as source data;
- non-academic recipe text; identify as unsuitable and do not produce a study pack.

The original fixture contents remain in the local ZIP; actual recorded outcomes are in ../test-results.csv.
