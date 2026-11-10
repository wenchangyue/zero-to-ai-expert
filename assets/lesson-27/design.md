# Demo design — lesson 27
Question: when you ask ChatGPT to rewrite your resume for a job post, does it add things you never did?
Setup: made-up resume with dates but no measured results (`ui/resume.txt`), made-up job post (`ui/job.txt`), logged-out ChatGPT, 2 prompts × 3 new chats, one session 2026-11-10 08:39–08:42 EST (run start times in meta.json). Key fixed first in `truth.md`; graded in `score.py` (every quote asserted verbatim).
Result: Plain prompt added items in 3 of 3 runs (1, 3, 6 counted), all echoing the job post; a years number in 2 of 3 ("4+ years", "2+ years ... social media"). No tool, title or degree added in any run. Rules prompt (facts only, [ADD NUMBER], list gaps): 0 counted in 3 of 3, all 5 real gaps listed in 3 of 3, 1–3 [ADD NUMBER] blanks.
Framework: Facts, Blanks, Gaps (+ check: underline any resume word that came from the job post and ask "did I do this?").
