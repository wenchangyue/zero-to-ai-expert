# Lesson 14 answer key (fixed 2026-10-05, before any run)

Input: `products.csv`, a fictional home-goods shop ("Fernhill Home", SKUs FH-01…FH-50), 50 rows, columns sku, product, material, size, details, colors, care, price, note. Written for this lesson; no real brand.

## What counts as an error in a description (per description, per kind)

1. **Contradicts the sheet** (definite error)
   - FH-04, FH-13, FH-17, FH-19: says or implies microwave safe.
   - FH-07, FH-14: calls the item flawless / perfect finish (they are seconds).
   - FH-15: lists Moss as a colour. FH-35: lists Ink as a colour.
   - FH-44: says it has a drainage hole. FH-45: suggests fresh flowers or water.
   - FH-48: says it arrives assembled / ready to use out of the box.
   - Any number, colour, material, size or price that differs from the row.
2. **Invented claim** (not in the row; the shop can't stand behind it)
   - A care or safety claim on a row whose care column is blank (FH-05, 08, 12, 18, 22, 27, 39, 42, 43, 47, 48, 50): dishwasher, microwave, oven, freezer, machine-washable, food-safe, waterproof, outdoor use.
   - On any row: handmade / handcrafted / hand-thrown / hand-poured, lead-free, BPA-free, non-toxic, food-safe (unless in the row), organic, eco-friendly / sustainable, recycled (except FH-46), made in a place, small-batch, warranty / lifetime, chip-, scratch-, stain-, shatter-resistant.
   - A number that is not in the row (e.g. a burn time for FH-32 or FH-34, which have none).
3. **Missing warning** (the note is a fact the buyer needs)
   - FH-03 single cup; FH-04, 13, 17 not microwave safe; FH-19 not for microwave use; FH-07, 14 seconds / small flaws; FH-23 labels not included; FH-44 no drainage hole; FH-45 not watertight / dried stems only; FH-48 ships unassembled.
   - FH-28 (unique) and FH-46 (bubbles) are nice to have, not counted.

Accurate unit conversions (e.g. 12 oz ≈ 355 ml) are recorded separately, not counted as errors.
Puffery without a checkable claim ("cozy", "beautiful", "perfect for slow mornings") is not an error. "Perfect" counts only when it describes the finish of FH-07 / FH-14.

## Row groups (from the sheet, before the runs)
- Care blank: 12 rows (listed above).
- Details blank: FH-15, 16, 17, 18, 32, 34, 36, 40, 41, 45, 46 (11 rows).
- Has a note: FH-03, 04, 07, 13, 14, 15, 17, 19, 23, 28, 35, 45, 46, 48 (14 rows).

## Checks
- `score.py`: keyword and number rules above per description, then every flag read by hand and adjudicated (`adjudication.md`).
- Sampling: for each answer, the exact chance that a random sample of k descriptions (k = 5, 10) contains at least one error (hypergeometric over the real error rows), and what a word sweep across all 50 finds.
