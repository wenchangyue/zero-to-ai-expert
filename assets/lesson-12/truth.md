# Answer key and scoring — fixed 2026-10-03 before any run

Scenario (fictional, written for this lesson): Dana Okafor, volunteer coordinator at Riverside Food Bank. Her context is in `context.txt` (6 lines). Tasks: T1 shift reminder, T2 thank-you note, T3 reply to a donor asking when chairs can be picked up, T4 an unrelated personal request (gift ideas for her dad).

Arms (3 fresh runs each, Claude Sonnet via `automation/run_demo.py`, no tools):
- A: task only, no context (T1–T3).
- B: the 6 context lines pasted above the task in the message (T1–T3).
- B2: the paste with the "never promise a date" line left out (T3 only).
- C: the 6 lines saved as instructions (appended to the system prompt, where apps put custom/project instructions), message = task only (T1–T3).
- D: same saved instructions, unrelated task T4.

## Automatic checks (score.py), per answer to T1–T3
| id | Check | Rule |
|---|---|---|
| K1 | signed "Dana" | the last 3 non-empty lines contain "Dana" |
| K2 | no placeholders | no `[...]` bracket placeholder (counter fixed after gate r1 to count placeholders of any length: 49, not 45) |
| K3 | under 120 words | body word count < 120 |
| K4 | no exclamation marks | no "!" |
| K5 | shift facts right (T1 only) | mentions Saturday, 9, noon/12, Elm Street |
| K6 | no promised pickup date (T3 only) | no weekday name, "tomorrow", "this week", "next week" or numeric date as a pickup time |

Without context, K1, K5 cannot be met except by chance (the model does not know the name or the shift); that is expected and is the point of arm A, not a trap.

## Leak check (D, T4)
An instruction leaks if the gift answer mentions the food bank, volunteers or shifts, or is signed "Dana". The word limit or plain style carrying over is recorded but not counted as a leak (harmless).

No results are predicted here; whatever the runs show is reported.

## Added after the main runs (2026-10-03)
- E: control for the leak check, T4 with no saved instructions, 3 runs. Same leak rule.

## Correction after gate round 2 (2026-10-03)
The phrase "where chat apps place / where apps put custom/project instructions" above is not verified. For this simulation, the six lines were appended to the system prompt; no app implementation was tested. Help pages only say saved instructions apply to every chat (or every chat in a project).
