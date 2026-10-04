# Answer key — fixed 2026-10-04 before any run

Task: a parent of a Grade 3 child wants, from each weekly newsletter (fictional, written for this lesson), every date, what to bring or pay, and every deadline that applies to Grade 3 or all grades. Newsletters: `week2.txt` (Fri Oct 9, 2026), `week3.txt` (Fri Oct 16, 2026). (Week 1 is the imaginary week the template was written in; it is not run.)

## Week 2 — items that belong in the answer (6)
| id | Item | Must show |
|---|---|---|
| W2a | Picture day | Wed Oct 14; order form; from $18 |
| W2b | Grade 3 field trip | Thu Oct 22; slip + $6 due Mon Oct 19 |
| W2c | Library day moves to Thursday | Thursdays, from Oct 15 |
| W2d | No school | Mon Oct 12 |
| W2e | Food drive | week of Oct 12–16; canned goods (optional) |
| W2f | PTA meeting | Tue Oct 13, 7 p.m. (optional) |
Traps: T2x Grade 5 band night (other grade — must not be listed as Grade 3); T2y book fair Oct 13 (cancelled — must not be listed as happening).

## Week 3 — items (7)
| id | Item | Must show |
|---|---|---|
| W3a | Halloween parade | Fri Oct 30, 9 a.m.; no masks or toy weapons |
| W3b | Field trip | Thu Oct 22; slip + $6 by Mon Oct 19 |
| W3c | Conference sign-ups open | Mon Oct 19 |
| W3d | Conferences + early dismissal | Nov 5 and 6, 12:30 p.m. |
| W3e | Picture retakes | Wed Nov 4 (corrected; not Nov 3) |
| W3f | Book fair | Oct 26–29 |
| W3g | Lost and found donated | Fri Oct 23 |
Traps: T3x science fair (Grades 4–5); T3y retake date given as Nov 3.

## Scoring (score.py)
- An item counts as found when the answer mentions its keyword and its key date (any common format: "October 14", "Oct 14", "10/14", "Wed 14"). Optional items (W2e, W2f) are counted separately and are not errors when left out.
- Errors: a trap listed as applying to Grade 3 or as happening; a wrong date for a found item (checked by hand from the saved answers).
- Format: does the answer use the same columns as the other runs of its setup (table with Date / What / Bring or pay / Deadline)? Checked by hand and recorded in `scores.json`.
- Fairness note (before the runs): the week-2 request in setup A does not say the child is in Grade 3, so T2x (Grade 5 band night) is not counted as an error for A-W2. Everything else is scored the same way for all setups.

## Correction after gate round 1 (2026-10-04)
- The first template's formatting example was "(for example, Wed Oct 14)", which is the correct week-2 picture-day answer. That leaks the answer for one item. The example was changed to "(for example, Mon Jan 5)" and setups B and C were re-run (3 × 2 weeks each). The first B/C runs are kept as `runs-v1-leaky-example.json` and are not used for results.
- `score.py` date pattern now accepts ordinal suffixes ("October 30th"); the first version missed them.
