# Lesson 15 demo design (2026-10-06)

**Question:** AI can draft a teacher's lesson pack fast. What do you check so the bar doesn't drop?

- **Inputs:** `inputs.md` (fictional). A Grade 7 syllabus line about Moon phases; an exit-ticket question; three student answers:
  - A correct;
  - B the Earth's-shadow misconception;
  - C with waxing and waning swapped.
- **Answer key:** `truth.md`, fixed before any run. Facts checked against NASA pages (`../sources.md`).
- **Model and harness:** Claude Sonnet via `automation/run_demo.py` (restricted, no tools, plain system prompt, stdin closed).

## Arms
- **A** (3 runs): one request for the whole pack. A 45-minute lesson plan, a 10-question multiple-choice quiz with key, and feedback on the three answers.
- **B** (2 runs per pack): a fresh chat is given each whole A pack and asked to list every factual error, quoting it. **Added after reading A's results.**
- **C** (2 runs per quiz): a fresh chat answers each A quiz without the key (the blind retake), flagging items with more than one defensible answer. **Planned in `truth.md` before the runs.**

## Results (`scores.json`)
- **Drafting time:** 24, 27, 20 seconds per pack.
- **Feedback:** right in 9 of 9 cases. A was not given an invented error; B's shadow idea was corrected 3/3; C's swap was caught 3/3.
- **Quizzes:** 30 items, 0 key errors on reading. Blind retake: 60/60 answers matched the keys; all 6 retakes flagged Q2 ("How much of the Moon is lit by the Sun?"; in quizzes 1 and 3 the option "It depends on the phase", in quiz 2 "All of it during a full moon, none during a new moon") as possibly two-answer. That is wording worth a look, not a key error.
- **Lesson plans:**
  - packs 1 and 2 said the Moon *orbits* Earth in about 29.5 days (orbit ≈ 27 days; 29.5 is the phase cycle — NASA);
  - pack 1 also had an answer-key note whose wording could suggest that "quarter" refers to the lit area (NASA: a quarter of the way through the cycle). This was classified as potentially misleading wording, not a definite factual error;
  - I missed that note on my own read; check B found it and I verified it;
  - pack 3 was correct.
- **Fact-check B:** orbit slip 4/4; quarter note 2/2; the clean pack got "no errors" 2/2; 0 false error claims.
- **Missed by everyone until the script review:**
  - pack 1's activity tip says the head blocks the light at the "new moon" position;
  - in the lamp-and-ball model the head's shadow falls on the ball at the full-moon position (the eclipse geometry, NASA);
  - both B checks of pack 1 missed it (0/2), and so did my read;
  - the GPT-6 gate found it.

**Limits:**
- one model, one topic, one grade, three runs;
- correctness only, not teaching quality or fit for a class;
- teacher time was not measured;
- B uses the same kind of model as the writer and could share its blind spots.
