# Lesson 16 answer key (fixed 2026-10-07, before any run)

**Source:** SYNERGY dataset (CC0), review `Oud_2018`: Oud M, Arntz A, Hermens ML, Verhoef R, Kendall T. *Specialized psychotherapies for adults with borderline personality disorder: a systematic review and meta-analysis.* Aust N Z J Psychiatry 2018;52(10):949-961 (PMID 30091375, PMC6151959).
- `label_included` = the review authors' final decision after full-text screening.
- File `Oud_2018_ids.csv`: 1,053 records, 20 included.

**Sample (`papers.json`):**
- All 20 included records plus 180 excluded drawn at random (Python `random.seed(42)`, records with an OpenAlex ID), then shuffled with the same seed and numbered 1–200.
- Titles and abstracts come from OpenAlex (abstract rebuilt from its inverted index). 61 records have no abstract in OpenAlex, including 6 of the 20 included; they are kept as title-only.
- The sample is enriched: 10% included versus 1.9% in the full search.

**Criteria given to the model** (our paraphrase of the review's Methods, "Eligibility criteria"):
- **Include:** randomized controlled trials of dialectical behavior therapy, mentalization-based treatment, transference-focused psychotherapy or schema therapy, for adults (18+) with borderline personality disorder. The therapy must include individual psychotherapy and last at least 16 weeks. The comparison can be another structured psychotherapy or a control such as treatment as usual, a waiting list or community treatment by experts.
- **Exclude:** trials where under two thirds of participants have BPD; incomplete versions of a therapy (for example skills training only).

## Scoring (per run)
- **Recall:** how many of the 20 included records were kept (Include or Unsure). A dropped included record is a miss.
- **Workload:** how many records were kept in total. Keeping a record the review later excluded at full text is not an error at this stage.
- **Coverage:** whether every one of the 200 records got a decision; records with no decision are counted separately.
- **Canary check** (the "papers you already know" test):
  - records [7, 22, 59] were picked at random from the 20 included before any run (seed 42);
  - for each run, did it keep all three?
  - this shows whether a three-paper check would have warned you.

## Requests (fixed before the runs)
- **A:** all 200 in one message, one plain request listing the papers to include. 3 runs.
- **B:** batches of 20, a decision for every paper (Include / Exclude / Unsure) with a short reason, plus two rules: "Unsure if the abstract is missing or doesn't say", and "Exclude only when the abstract clearly fails a criterion". 10 batches × 3 runs.
