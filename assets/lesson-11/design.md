# Lesson 11 demo design (2026-10-02)

**Claim to test:** an AI research answer with sources can still mislead; asking for the exact sentence behind every number makes it checkable, and the last check is going back to the original.

- Question (same in all setups): did the UK's 2022 four-day week trial work? Key results with numbers and sources.
- Answer key `truth.md`, written from the primary Autonomy report before any run.
- Setups, 3 fresh runs each, Claude Sonnet via Claude Code CLI 2.x, `automation/run_demo.py` (restricted, no settings, plain system prompt, stdin closed):
  - A: no tools (answers from memory);
  - B: WebSearch + WebFetch only;
  - C: same tools, and the prompt asks for the link and the exact sentence for every number, original report preferred, "say so if you could not open a page".
- Checks: `check_sources.py` fetches every cited link with curl (status, saved page text) and looks for each quoted sentence on its page (word-normalized). 403/406 = the site blocks scripts (counted separately, not as dead). 404s were calibrated: real BBC and Guardian pages open with the same script. Number errors and invented attributions judged by hand against the report, with line numbers (`score.py`).
- Limits: one question, one model, 3 runs per setup; a page "has the main results" means it states 92, 71 and 57 as % or "per cent".

## Results (`scores.json`)
| Setup | Links | Returned 404 when checked | Blocked for scripts | Number errors | Notes |
|---|---|---|---|---|---|
| A no search | 13 | 8 | 0 | 3 in 2 of 3 runs | 1 caveat attributed to researchers that the report doesn't contain |
| B search | 20 | 0 | 5 | 1 in 1 of 3 runs | sources listed at the end, no number tied to a link; 7 of 15 opened pages state the main results; 1 invented attribution |
| C search + sentence | 7 | 0 | 0 | 0 | 37 of 37 quoted sentences found word for word on the linked page; 3 of 3 said they could not read the PDF and used Autonomy's own results page |

- 0 of 9 answers said the 57% resignation drop (and 65% sick days) is not statistically significant. The report body says the researchers "are unable to say that these three trends are statistically significant" (l.1168-1170), while its summary says staff leaving "decreased significantly" (l.165-167). All three C runs quoted the summary sentence exactly.
- 1 of 9 mentioned that the revenue figures rest on 23 and 24 of the 61 companies.
