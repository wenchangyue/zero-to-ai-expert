# Answer key (fixed before the runs, 2026-10-13)

For each email the model writes (the email body only; ignore any text outside the email):

1. **Placeholders**: number of bracketed blanks like `[Your Name]`, `[Date]`. Count `[...]` spans.
2. **Signed Alex**: the sign-off contains "Alex".
3. **Says the problem**: mentions the kitchen faucet leak.
4. **Says how long**: mentions three days (only possible in arm C; in arm V the model has no way to know).
5. **Asks for this week**: asks for the repair this week (arm C) — arm V: whether it invents a timeframe.
6. **Under 100 words** (arm C asks for it): body word count by `score.py` (whitespace tokens, subject line excluded).
7. **Invented facts** (arm V): any specific fact not in the prompt (an appliance, a date, a duration). Judged by reading; quoted in `scores.json`.

Follow-up turn 2 (c1): firmer tone and a Friday reply request → check "Friday" appears.
Follow-up turn 3 (c1): the model's own word count vs `score.py`'s count. Report both numbers as they are.
"Good enough to send" = placeholders 0, signed Alex, says the problem, ≤ 100 words.


Note (2026-10-13, after gate round 1): `score.py` judges "≤ 100 words" on the count including the subject line (stricter than body-only); every email is far below 100 either way, so no verdict depends on this choice.
