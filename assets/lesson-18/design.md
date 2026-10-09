# Lesson 18 demo design (2026-10-09)

**Curriculum #24:** "Automate One Daily Task With No Code".

**Scope narrowed.** Building and recording a real no-code automation would need an account on an automation service. Creating accounts is prohibited, and using the owner's accounts for a standing automation is not covered by `DECISIONS.md`.

The lesson therefore tests the part that can be tested honestly, the AI step:
- what it does when the input a daily automation passes it quietly breaks;
- which checks make the breakage visible.

The "never ran at all" failure is illustrated with this channel's own daily trigger as a real risk (run conditions, 7-day expiry). The records cited here show no missed run (that does not prove none ever happened); the 2026-10-08 401s were an interrupted run, not a missed trigger.

## Setup
- **Inputs:** fictional bakery inbox, `inputs.json`. Ten mornings, Oct 13–22, 2026. Each input = "Today's date" + "Emails received since 6 pm yesterday (N)".
  - Six normal mornings.
  - Four broken ones: empty (D3), stale re-send of D4 (D5), an HTML 429 error page (D7), header says 6 but 2 included (D9).
- **Answer key:** `truth.md`, fixed before the runs.
- **Runs:** Claude Sonnet via `automation/run_demo.py`, each morning in a fresh chat, 3 runs. The ten mornings were run in one batch, not on ten real mornings; no trigger or delivery was involved.
- **Requests:**
  - A: the plain step;
  - B: plus "STATUS: OK/ALERT" with rules, and a closing "Covered: <date range> · <n> emails read" line.

## Results (`scores.json`, `auto-flags.json`)
| Failure | A flagged | B flagged |
|---|---|---|
| Empty | 3/3 | 3/3 |
| Error page | 3/3 | 3/3 |
| Truncated | 3/3 | 3/3 |
| **Stale (yesterday's emails again)** | **0/3** ("4 emails came in overnight") | 3/3 |
| False alarms on 18 normal mornings | 0 | 0 |

- B's coverage line appeared on 30/30 mornings. On the stale morning (Oct 17) it read "Oct 15 … – Oct 16 …".

## The missed-run risk (this channel)
- The daily lesson is triggered by a session cron in the owner's open window. It expires after 7 days and only runs while the window is open; each run renews it.
- On 2026-10-08 the YouTube connection returned intermittent 401s mid-upload, and the run resumed with `yt_finish.py` (lesson 17 `production-audit.md`).
- The check we rely on: a final report every day; no report after a reasonable completion window = check the run and the delivery.

**Limits:**
- one model, one fictional inbox, four failure types we chose, 3 runs;
- no real trigger, connector or delivery tested;
- real automations can also fail in ways the AI step never sees.
