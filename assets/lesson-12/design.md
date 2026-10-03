# Lesson 12 demo design (2026-10-03)

**Claim to test:** each new chat starts without your context; pasting it works until you forget a line; saving it once makes fresh chats follow it; global saved instructions also reach unrelated chats.

- Scenario (fictional): Dana Okafor, volunteer coordinator, Riverside Food Bank; 6 context lines (`context.txt`); tasks T1 shift reminder, T2 thank-you note, T3 reply to a donor asking when chairs can be picked up, T4 unrelated (gift ideas for her dad).
- Claude Sonnet via `automation/run_demo.py` (restricted, no tools, plain system prompt, stdin closed), 3 fresh runs per setup. "Saved instructions" = the 6 lines appended to the system prompt with the label "The user's saved instructions:", which is where chat apps place custom/project instructions. This simulates the placement; it is not a test of any app.
- Rules and checks fixed before the runs (`truth.md`); E (control without instructions) added after the main runs and labelled so.

## Results (`scores.json`, `runs-e.json`)
| Setup | Answers | Result |
|---|---|---|
| A no context | 9 | templates with blanks: 49 bracket placeholders in total; 0 signed Dana; 0/3 shift reminders with the right shift; median 169 words; 8/9 with "!" |
| B pasted every time | 9 | all six checks met in 9/9; median 83 words |
| B2 pasted, "never promise a date" line left out | 3 | 2/3 promised the donor "this Saturday, October 10" |
| C saved instructions, task only | 9 | all six checks met in 9/9; median 59 words |
| D saved instructions, unrelated gift request | 3 | 2/3 signed "Dana"; 0 mentioned work |
| E no instructions, same gift request (control) | 3 | 0/3 signed |

Limits: one model, one fictional person, 3 runs per setup; saved-instruction placement simulated; app memory features not tested.

## Correction after gate round 2 (2026-10-03)
The phrase "where chat apps place / where apps put custom/project instructions" above is not verified. For this simulation, the six lines were appended to the system prompt; no app implementation was tested. Help pages only say saved instructions apply to every chat (or every chat in a project).
