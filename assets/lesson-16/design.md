# Lesson 16 demo design (2026-10-07)

**Question:** can AI screen 200 search results for a literature review, and how do you check for the relevant paper it dropped?

- **Answer key:** the human decisions of a published systematic review (Oud et al. 2018, borderline personality disorder psychotherapies), from the SYNERGY dataset (CC0). See `truth.md`.
- **Sample:** 200 records, all 20 included plus 180 excluded at random (seed 42); 61 records have no abstract (6 of the 20 included).
- **Model and harness:** Claude Sonnet via `automation/run_demo.py` (restricted, no tools); 3 runs per request.

## Requests
- **A:** all 200 at once, plain request "which should I include". Fixed before the runs.
- **B:** batches of 20, a decision per paper (Include / Exclude / Unsure) with "Unsure if no abstract" and "Exclude only when it clearly fails". Fixed before the runs.
- **C** (**added after seeing A and B**): a fresh chat's second look at the 182 records outside A1's main keep list (including optional companion reports).
- **No-abstract rule** (**added after seeing A and B**, computed by script, no AI): excluded records with no abstract and one of the four therapies in the title.

## Results (`scores.json`, `scene-data.json`)
| Request | Recall of the 20 (runs 1–3) | Records kept | Time per full pass |
|---|---|---|---|
| A all at once | 17, 17, 18 | 18, 26, 29 | 25–33 s |
| B batches + a decision each | 18, 18, 17 | 50, 52, 51 | ≈ 80 s (10 × ≈ 8 s) |

- **Canary check** (3 included papers chosen before the runs): all three were kept in 6 of 6 runs, including runs that missed 2–3 relevant papers.
- **The same misses everywhere:**
  - paper 8: its abstract says 12 weeks and about half with BPD. Our criteria left out the review's exception for disaggregated BPD data;
  - paper 68: no abstract; the title says "naturalistic evaluation";
  - paper 153: no abstract; the title says group schema therapy (A1, A2);
  - B2 and B3 also dropped paper 56 (full DBT vs partial arms) as "incomplete", while A kept it 3/3.
- **Coverage:** B decided all 200 in every run. A3 said "31" but listed 29 numbers.
- **C:** flagged 14, 16 and 16 records; recovered 153 in 3/3 runs; recovered neither 8 nor 68.
- **No-abstract rule:** 14 records, including 68 and 153.
- **Nothing recovered paper 8.**

**Limits:**
- one review, one model, 3 runs;
- the sample is enriched (10% relevant vs 1.9% in the full 1,053-record search);
- the labels are full-text decisions, so a title and abstract may not be enough to confirm some of them (they would need "Unsure" and a full read);
- the criteria are our paraphrase, and they omitted one exception.
