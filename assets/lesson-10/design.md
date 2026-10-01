# Lesson 10 demo design (2026-10-01)

Question: can you trust AI meeting notes on who agreed to do what, and by when?
Material: `meeting.txt`, a fictional 2.5-minute planning call written for this lesson (371 words), with six planted traps and an answer key fixed before any run (`truth.md`): a task reassigned mid-call, a tentative offer, a task nobody took, a date proposed then left open, a task with no deadline, a wish nobody agreed to.
Arms (3 fresh runs each, `runs.json`): A "Summarize this meeting." B "List the action items with the owner and deadline." C owner + deadline + exact quote with timestamp, "not stated" when missing, suggestions listed separately.
Arm D (`runs-d.json`): prompt C on the same transcript with speaker names replaced by "Speaker 1–5" (`meeting-unlabeled.txt`), as auto-transcripts often are.
Quotes checked verbatim with `automation/check_quotes.py` (`quote-check-c.json`). Counts in `scores.json`.
Result in one line: no run fell into any of the six traps; the errors were small and confident — a deadline nobody stated (2/3 summaries), calendar dates before the meeting (1/3 action lists), and speaker names filled in without saying they were guesses (3/3 unlabeled runs; correct here).
Arm E (`runs-e.json`): arm D plus one line asking to keep speaker numbers and mark added names as guesses. All 3 disclosed the guesses (2 at each item or up front, 1 only in a note at the end); none put names next to timestamps.
