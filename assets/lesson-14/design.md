# Lesson 14 demo design (2026-10-05)

**Question:** after AI writes fifty product descriptions at once, how do you check them without reading all fifty, and when do you check more?

- **Input:** `products.csv`, a fictional shop (Fernhill Home, FH-01…FH-50). It has 12 blank care cells, 11 blank details cells and 14 notes: not microwave safe, seconds, discontinued colours, unassembled, not watertight, labels not included, no drainage hole.
- **Answer key:** `truth.md`, fixed before any run.
- **Model and harness:** Claude Sonnet via `automation/run_demo.py` (restricted, no tools, plain system prompt, stdin closed). Each request was run 3 fresh times with the whole sheet in one message.

## Requests
- **A** plain: "Write a product description for each of these 50 products."
- **B** template: 40–70 words, warm but plain, only facts from the row, follow the notes, then list blank columns.
- **C** "make them sell": engaging, persuasive, 80–100 words, highlight benefits, SEO-friendly.
  - Added after A and B. A was nearly clean, so I tested the wording shop owners commonly use. A and B are kept and reported.
- **D** C plus three rules written after the C sweep:
  - only facts from the row;
  - nothing about how or where it was made, and no eco/sustainable;
  - no care, safety or durability claims the row doesn't make.

  This is the "fix the request and rerun" step.

## Checks
- `score.py`: keyword and number flags.
- A separate full read of all 600 descriptions against their rows: `review-candidates*.json`, adjudicated in `adjudication.md` and counted in `confirmed.json`.
- `sample.py`: exact hypergeometric chance that a random sample of 5 or 10 rows hits at least one bad row, and a word sweep for claim words the sheet never uses (`SWEEP`).

## Results (`scores.json`, `sampling.json`, `scene-data.json`)
| Request | Rows with an invented claim (run 1, 2, 3; of 50) | Median words |
|---|---|---|
| A plain | 0, 0, 1 | 28–31 |
| B template | 1, 1, 1 | 50–55 |
| C make them sell | 9, 3, 2 | 77–89 |
| D sell + 3 rules | 0, 1, 1 | 80–98 |

- **Never wrong anywhere:** 0 contradictions, 0 missing warnings and 0 numbers outside the row in all 12 answers. The mistakes were additions.
- **FH-46 (bubbles in the glass):** "handmade" in 5 of the 12 answers (B2, B3, C1, C2, C3).
- **Random sample, C2 (3 bad rows):** P(a random 5 hits ≥ 1) = 0.276; for 10, 0.496. If 5 of 50 were bad, a random 10 comes back clean with p = 0.311.
- **Sweep, C1–C3:**
  - It flagged 15 rows; 13 were real.
  - It found 13 of the 14 bad rows.
  - It missed "built for little hands and the occasional drop" (C1 FH-19).
  - Its 2 false hits were "outdoorsy" on the camp mug.
- **Sweep, D:** it found both remaining bad rows ("relaxed, handcrafted feel", "handmade-style charm").

**Limits:** one model, one fictional shop, a short tidy sheet, 3 runs per request. The sweep words fit this sheet. The stock claims ("Quantities are limited") are not in the key and are not counted.
