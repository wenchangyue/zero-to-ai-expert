# Lesson 13 demo design (2026-10-04)

**Claim to test:** a request typed fresh each week drifts; a fixed template with explicit rules gives the same, complete answer on new inputs; an added AI self-check may or may not add anything.

- Task: a Grade 3 parent's weekly school newsletter (fictional, `week2.txt`, `week3.txt`) → dates, what to bring or pay, deadlines. Answer key and traps fixed before the runs (`truth.md`), including a fairness note for A-W2.
- Claude Sonnet via `automation/run_demo.py` (restricted, no tools, plain system prompt, stdin closed); 3 fresh runs per setup per week.
- Setups: A typed fresh each week (two different natural wordings); B the template (`template.txt`, first part); C the template plus a five-line checklist the model applies and reports.
- Checks: `score.py` (item = keyword and correct date on the same line), `weekday_check.py` (every "Weekday, Month Day" pair vs the 2026 calendar, and dates before the newsletter), manual reading of all 18 answers.

## Results (`scores.json`, `weekday-check.json`)
| Setup | Answers | Required items found | Wrong calendar dates | Tables / same columns |
|---|---|---|---|---|
| A typed fresh | 6 | 27 / 39 | 2 answers (picture day "Wednesday, Oct 7" — before the newsletter; "Wednesday, Oct 15" — a Thursday) | 0 tables |
| B template | 6 | 39 / 39 | 0 of 72 weekday-date pairs | 6 / one column set |
| C template + checklist | 6 | 39 / 39 | 0 of 92 pairs | 6 / one column set |

- A week 3 ("for my 3rd grader"): 3/3 answers were written to the child, with emojis; 3/3 left the field trip as "next Thursday" without a date; 3/3 left out the conference sign-up opening.
- Traps (other grades, cancelled book fair, corrected retake date): 0 errors in every setup.
- C: every checklist line ticked in all 6 answers, no fix reported; answers longer (median words C vs B in `scene-data.json`). We did not test the self-check on an answer with a known mistake, and only final answers were saved.

Limits: one model, one fictional school, two weeks, 3 runs per setup.

## After gate round 1
B and C were re-run with a neutral example date ("Mon Jan 5"; the first example "Wed Oct 14" was the week-2 picture-day answer). Results above are from the re-run (`runs-bc-v2.json`, merged into `runs.json`); the first B/C runs are in `runs-v1-leaky-example.json`. Scorer fixed for ordinal dates (A: 26 → 27). `detail_check.py`: all fees, forms, times and rules present in the 12 B/C answers (presence only). C: all six checklist sections tick five lines; the only "removed" notes describe the template's own exclusions; no corrected error is reported. Only final answers were saved, so internal corrections can't be seen.
