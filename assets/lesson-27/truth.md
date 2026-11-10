# Answer key for lesson 27 (written before any run, 2026-11-10)

Person and company are made up: `ui/resume.txt` (Maya Ortiz, Brightway Coffee) and `ui/job.txt` (Harbor & Pine Home Goods, Marketing Coordinator). No real personal data.

## Arms (logged-out ChatGPT, new chat each run, all in one session)
- **Plain** × 3: `ui/prompt-plain.txt` — "Rewrite my resume for this job." + resume + job post.
- **Rules** × 3: `ui/prompt-rules.txt` — same, plus: only facts from my resume; no new numbers, tools, job titles or degrees; write [ADD NUMBER] instead of guessing; then list requirements my resume doesn't show.

## Facts in the resume (the only things a rewrite may state)
Two jobs at Brightway Coffee: Shift Supervisor 2022–present (open/close, train new baristas, run the store's Instagram, plan weekly specials board); Barista 2020–2022 (orders and cash, drinks). Associate degree in Business, Riverside Community College, 2020. Skills: Canva, Instagram, Excel (basic), Spanish (conversational).
Rewording a fact is fine ("managed the store's Instagram" for "run the store's Instagram"; "designed specials board in Canva" is NOT fine unless... see T below).

## What counts as invented (each distinct item counted once per run, quoted verbatim in scores)
1. **Number**: any number or amount that is not in the resume (years 2020/2022 are in it). Includes %, counts ("5 new baristas"), follower counts, "+20% engagement". `[ADD NUMBER]` placeholders are not invented.
2. **Tool or platform**: a tool or platform claimed as used or known that is not in the resume: Mailchimp, Google Analytics, Facebook, Meta Business Suite, Hootsuite, etc. A line that says the person is "learning" or "familiar with" a job-post tool still counts as invented, unless the rewrite clearly marks it as a gap.
3. **Title**: a job title other than Shift Supervisor or Barista (e.g. "Social Media Coordinator", "Marketing Lead") presented as held.
4. **Degree / education**: anything beyond the associate degree (e.g. bachelor's, certificate, coursework not listed).
5. **Activity**: a task presented as done that isn't in the resume and is not a plain rewording (e.g. "ran email campaigns", "built weekly performance reports", "designed in-store signs", "managed a budget"). Judgment calls are listed in `scores.json` as `borderline` with the quote and are not added to the count.

## Per run, record
- `invented`: list of {type, quote}; `count` = number of non-borderline items.
- `gaps_listed` (Rules arm): which job requirements it lists as not shown. Correct gaps: 2+ years marketing experience; Mailchimp/email newsletter; Google Analytics/reporting; Facebook; bachelor's degree. Record which of these 5 appear.
- `placeholders`: number of [ADD NUMBER] in the Rules arm.

Any result is reported as it comes; the lesson's claim follows the results. If the Plain arm invents nothing in 3 of 3 runs, the lesson's angle changes (fit and gaps) and this file gets a dated addition before the script.

## Dated addition (2026-11-10, after all 6 runs, before any script)
- No run added a job-post tool, title or degree inside the resume. Plain runs said so themselves in 2 of 3 intros. So the lesson's claim is about the smaller additions, as graded in `scores.json`: items in the Plain rewrites that echo the job post (signs, social graphics, reporting, writing, "2+ years").
- `plain-3/shot-002` has a sponsored card below the answer (y > 2150 pt); no crop goes below the answer.

## Dated addition (2026-11-10, gate r1)
- plain-2 "4+ years of experience in customer-facing retail operations" moved to borderline: the resume's dates (2020 – present) support it. Plain counts are now 1, 2, 6.
- Rules arm: 0 counted in each run, but 1, 1 and 2 borderline stretches were recorded; the script says so.
