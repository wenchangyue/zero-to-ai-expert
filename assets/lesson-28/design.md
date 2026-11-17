# Lesson 28 demo design and results

Question: how do I turn my notes into a podcast with NotebookLM (now Gemini Notebook), and can I trust what the hosts say?
Product: Gemini Notebook on the web, owner's account (profile Default; plan shows "PRO"), 2026-11-17 08:54–09:31 New York time. Three new notebooks, each with notes.txt (lesson 22/25's fictional 230-word BIO 101 page) as the only source ("Copied text"). In each notebook three Audio Overviews, in order A → B → C. Answer key: truth.md (hash in fixed-before-runs.sha256 before any generation; addendum for arm C written before C was generated).
Audio: downloaded from the player's own audio URL (`automation/nlm_audio.mjs`, mode download; the menu's Download does not fire a browser download under ego), transcribed with faster-whisper medium.en (demo-runs/transcribe_audio.py).

| Arm | Settings | Length | Key points (of 10) | Things not in the notes (clear) | Clear errors |
|---|---|---|---|---|---|
| A | Deep Dive, Default length, nothing typed | 21:19 / 21:21 / 22:03 | 10 / 10 / 10 | 27 / 28 / 26 | 2 / 2 / 0 |
| B | Deep Dive, Default length, instructions (ui/customize.txt) | 20:23 / 20:32 / 18:51 | 10 / 10 / 10 | 6 / 11 / 13 | 0 / 0 / 0 |
| C | Brief, same instructions (added arm) | 1:48 / 1:36 / 1:51 | 10 / 7 / 10 | 0 / 0 / 0 | 0 / 0 / 0 |

Coverage counts topics mentioned, not complete coverage of every detail. C1 and C3 contain partial items; see scores.json coverage_note.

- A: invented exam timing in 3/3 ("tomorrow", "Tuesday", "next week"); C4/CAM said off the exam, then explained anyway 3/3. Clear errors: A1 "the notes mentioned electron excitement" (they don't), A1 C4 plants "stockpile CO2 at night" (CAM only), A2 ATP used in the RuBisCO step, A2 "law of the minimum" attributed to the notes.
- B: invented "tomorrow" 1/3; C4/CAM explained 2/3; quiz of 3 questions with right answers 3/3 (not the very last thing said). B2 says "No extra fluff. No outside facts, just the notes." (1:22) and then adds 11.
- C: one host-style brief; both exam tips 3/3; C4/CAM not explained 3/3; quiz 3 questions 3/3, answers given 2/3 (C2 asks without answering). C2 left out chlorophyll's colors, G3P and "light-independent but runs in daylight". C1/C3 say the colors only inside the quiz.
- Counting unit: one row per distinct claim (adjacent lines grouped); analogies and banter not counted; counts depend on this unit by a few either way. Every quoted line is in demo-runs/quotes/*.q and was checked verbatim against the transcript.
Limits: one page of notes on standard biology, one account (paid plan), one morning, three runs per setting, English only; Interactive mode, Short/Long length and other formats not tested.
