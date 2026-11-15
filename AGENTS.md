# AGENTS.md: Project (Paper Reproduction with Contribution)

Point of reference for continuing sessions. Read this first, then continue from any unchecked item below. Tick items off and add notes as work is done.

## Context

- Course: MSAI6320 (NLP), Dr. Ahmed Shawahna. Team of two students. Weight: 40% of the grade.
- Task: reproduce a paper and add our own contribution, completed in the second half of the semester.
- Must run on a laptop or Google Colab (keep compute light).
- Paper: *A Synthetic Request-Reply Email Corpus Annotated with Document-Level Politeness and Sentence-Level Face Acts* (Alipanah, Barriere, Baier). Listed as Findings of EMNLP 2026 (id `2026.findings-emnlp.22`; not verified against the official proceedings).
- Notes file: `NLP Project.md`. It was AI-generated and its details are partly unverified (see below). Treat it as a plan, not a source of truth.

## What is verified (from the abstract)

- Corpus of request-reply emails with sentence-level face-act labels and document-level politeness scores.
- Politeness annotated on three dimensions (directness vs indirectness, positive face saving, negative face saving) under Brown and Levinson's theory; overall politeness is their average.
- Document-level politeness is modeled by multi-target regression, improved by adding face-act classifier predictions.
- Context-sensitive face-act classifiers outperform context-free ones.
- Code and data are said to be at `github.com/alipanahroshad-oss/email-politeness-corpus`.

## What is NOT verified

- Contents of the GitHub repo (splits, annotation guidelines, evaluation scripts, license).
- The Hugging Face dataset link in the notes (`ralipanah/email-politeness-corpus`): no page was found.
- Corpus size, model details, and exact reported numbers.
- Any source of Arabic politeness data for the planned extension.

## Plan (from the notes, to be checked against the real repo)

1. Get the released dataset and understand its structure and label schema.
2. Analyze class distribution and imbalance.
3. Baseline: TF-IDF + Logistic Regression.
4. Reproduce: BERT sentence-level face-act classification (context-free).
5. Reproduce: context-aware classification.
6. Reproduce: document-level politeness regression with and without predicted face acts.
7. Contribution (pick at least one, see below).
8. Compare against the paper's reported results and discuss differences.

Candidate contributions:
- Arabic politeness classification with an Arabic pretrained model (e.g. AraBERT). Needs a data source.
- Model comparison: TF-IDF + LR vs BERT vs RoBERTa (vs Arabic transformer).
- Improved use of conversation context.

Known reproduction risks: understanding the annotation scheme, multi-label handling, leakage between related synthetic emails, evaluating classification and regression separately. Avoid regenerating the synthetic data with GPT-4o (API cost); use the released data.

## Pending items

- [ ] Confirm the project paper with the instructor and with the teammate.
- [ ] Open the GitHub repo and verify what it contains (data, splits, code, license, README).
- [ ] Find the real dataset location (Hugging Face link unverified).
- [ ] Download the data and write a short data-exploration notebook.
- [ ] Implement the TF-IDF + Logistic Regression baseline.
- [ ] Reproduce the BERT face-act classifiers (context-free and context-aware) and record metrics (accuracy, precision, recall, macro-F1).
- [ ] Reproduce the document-level regression experiments.
- [ ] Decide the contribution; if Arabic, find or build a suitable Arabic politeness dataset first, otherwise pick a feasible alternative.
- [ ] Implement and evaluate the contribution.
- [ ] Compare results with the paper and write the analysis.
- [ ] Add `requirements.txt` and a README with run instructions.
- [ ] Write up the final report/deliverable required by the course (confirm format and deadline with the instructor).

## Working notes

- Keep results honest: separate reproduced numbers from the paper's reported numbers.
- The notes' results table is a template ("to calculate"), not reported results.
