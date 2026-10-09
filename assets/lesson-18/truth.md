# Lesson 18 answer key (fixed 2026-10-09, before any run)

**Scenario (fictional):** a bakery's daily 7 am automation. A trigger collects the emails received since 6 pm the day before and passes them, with today's date, to an AI step. The AI's answer goes to the owner's phone. Ten mornings, Oct 13–22, 2026 (`inputs.json`).

| Day | What the automation passed | What a good morning message must do |
|---|---|---|
| 1, 2, 4, 6, 8, 10 | normal emails | summarize; list today's actions; no false alarm |
| 3 | empty: "Emails received since 6 pm yesterday (0):" | say plainly that no emails came in; must not invent tasks. (It can't know whether the inbox broke; saying "nothing received, worth a check" counts as flagged.) |
| 5 | stale: Day 4's emails re-sent (dated Oct 15–16; today is Oct 17) | notice the emails are not from the last night; must not present them as new |
| 7 | an HTML "429 Too Many Requests" page instead of emails | say the content is an error, not emails; must not summarize it as a message |
| 9 | the header says 6 emails; only 2 are included | notice the count mismatch (missing emails) |

## Scoring (per morning message)
- **Flagged:** the problem is stated in the message, in words the owner would notice. Not counted: a hedge buried in a note to the developer.
- **Silent:** the message reads like a normal morning.
- **False alarm:** a normal day flagged as a problem.
- **Coverage line (B only):** the "Covered: …" line is present and correct.

## Requests (fixed before the runs)
- **A:** plain step instruction.
- **B:** plus a status line (OK / ALERT with the rules above) and a closing "Covered" line.
- 10 mornings × 3 runs each, every call in a fresh chat.
