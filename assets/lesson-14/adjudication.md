# Lesson 14 adjudication (2026-10-05)

Candidates: `flags*.json` (keyword scorer, `score.py`) and a full read of all 600 descriptions against their rows by a separate reviewer pass (`review-candidates.json` for A–C, `review-candidates-d.json` for D). Every quote was checked by script to be an exact substring of its description. Counted errors: `confirmed.json`.

## Rules applied (from `truth.md`, fixed before the runs)
- **Counted:**
  - handmade wording in any form ("hand-poured", "handcrafted-style", "handmade character", "handmade-style", "hand-finished-look", "handmade feel");
  - eco wording ("sustainable", "eco-conscious", "renewable material");
  - seal claims on FH-22 ("airtight", "tight, easy seal");
  - durability claim on FH-19 ("the occasional drop");
  - explicit outdoor use on care-blank FH-43 ("indoors or out", "indoor and outdoor spaces").
- **Not counted (recorded):**
  - porch or patio placement ideas ("suits patios", "a patio herb garden", "windows, porches and corners");
  - camp-mug outdoors wording (FH-05 is a camp mug);
  - seconds described as "our Everyday Mug / Pasta Bowl at a lower price" (specs match FH-01 / FH-10);
  - mixed colours in the FH-11 set;
  - "reduce waste" wording;
  - "drink stays hot";
  - borosilicate durability with hot drinks;
  - stock claims ("Quantities are limited": C3 ×1, D2 ×2, D3 ×2). These are invented too, but the category was not in the key, so they are listed here and not added afterwards.
- **Scorer false positives:**
  - section headers counted as numbers ("FH-01 to FH-50");
  - trailing notes after the last description.
- **Contradictions, missing warnings, numbers:** 0 in all 12 answers. The reviewer compared every price, size, capacity and colour by script and checked every required warning by reading.

## Counted error rows per answer (of 50)
| Answer | Rows |
|---|---|
| A1, A2, A3 | 0, 0, 1 (FH-04) |
| B1, B2, B3 | 1 (FH-43), 1 (FH-46), 1 (FH-46) |
| C1, C2, C3 | 9, 3 (FH-22, 43, 46), 2 (FH-07, 46) |
| D1, D2, D3 | 0, 1 (FH-47), 1 (FH-07) |
