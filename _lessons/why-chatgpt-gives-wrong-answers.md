---
published: true
layout: lesson
title: "Why ChatGPT Gives Wrong Answers (and How to Catch Them)"
description: >-
  A letter count, a grocery total and a citation request, each run in three fresh
  ChatGPT chats against an answer key fixed before the runs, plus three checks a
  beginner can do: spot the risky answer, ask again, verify with a tool or the source.
date: '2026-10-27'
modified: '2026-10-27'
course: AI Tools and Workflows
level: Beginner
duration_label: 6 minutes
duration: PT5M38S
youtube_url: "https://youtu.be/PiRxOTFrYNg"
video_id: "PiRxOTFrYNg"
video_status: public
upload_date: "2026-10-27"
keywords:
  - why ChatGPT gives wrong answers
  - is ChatGPT accurate
  - ChatGPT wrong information
  - fact check ChatGPT
  - AI for beginners
  - Zero to AI Expert
quick_answer: >-
  Check the answers that are counts, sums, dates or sources. In a test on
  2026-10-27 (ChatGPT, logged out, three fresh chats per request), asking how many
  times the letter "e" appears in one sentence gave 38, 36 and 36; the answer is
  44. "Go word by word" gave 38, 48 and 44, and every run had wrong per-word
  counts. "Use Python" gave 45, 44 and 44; the 45 appeared under code that returns
  44. A 15-item grocery total was right twice and one cent short once. Citations
  with DOIs were real and matched in all three runs (with web search). Ask again
  in a fresh chat, then verify with a tool or the source.
learning_outcomes:
  - Recognize answers that need checking (counts, sums, dates, sources).
  - Use a second fresh chat as a warning sign, not as proof.
  - Check numbers with a spreadsheet formula or calculator.
  - Check a citation by opening it and matching title and authors.
faq:
  - question: Why does ChatGPT give wrong answers?
    answer: >-
      For counting letters, probably because it reads text in chunks rather than
      one letter at a time. In this test it gave a confident wrong number in all
      three bare-count runs, and showing its work did not reliably fix it.
  - question: Does asking ChatGPT to show its work fix it?
    answer: >-
      Not here: word-by-word counting gave 38, 48 and 44, and every run had wrong
      per-word counts (for example "evening: 3"; it has 2). The run that ended at
      44 listed counts that add up to 43. Showing the work made the mistakes easy
      to see, not absent.
  - question: Can I trust it if it shows Python code?
    answer: >-
      Only if you can see that the code ran. In one run it printed "Output: 45"
      under code that returns 44, with no sign on the page that the code ran.
  - question: Are ChatGPT's citations fake?
    answer: >-
      Not in this test: with web search, all DOIs resolved to the papers it
      described (title, authors, journal). Year differences were online-first vs
      print dates. Still open the link and check the title and authors.
  - question: How do I count letters or add numbers reliably?
    answer: >-
      In a spreadsheet, with the text in A1, =LEN(A1)-LEN(SUBSTITUTE(LOWER(A1),"e",""))
      counts the letter e (44 here); =SUM() adds a column (66.81 here). Both were
      run in LibreOffice.
sources:
  - label: The sentence
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-23/sentence.txt
  - label: The receipt
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-23/receipt.txt
  - label: Answer key (hash recorded before the first run)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-23/truth.md
  - label: Hashes and time
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-23/fixed-before-runs.sha256
  - label: Every answer (ads removed)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-23/all-answers.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-23/scores.json
  - label: Spreadsheet check results (LibreOffice)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-23/check-results.json
---

## The problem

ChatGPT answers in the same confident tone whether it is right or wrong. Which answers should a beginner check, and how?

## The test

ChatGPT on the web without logging in, three fresh chats per request, 2026-10-27 between 08:43 and 08:51 New York time. The answer key was fixed and hashed before the first run. Requests D and E were added after seeing the first results.

| Request | Answers | Real |
| --- | --- | --- |
| A. How many times does "e" appear? Just the number. | 38 · 36 · 36 | 44 |
| D. Same, word by word, then add | 38 · 48 · 44 (every run had wrong per-word counts; the 44 run's counts sum to 43) | 44 |
| E. Same, use Python and show the code | 45 · 44 · 44 (the 45 under code that returns 44; no sign code ran) | 44 |
| B. Grocery receipt, 15 items: total? | $66.81 · $66.80 · $66.81 | $66.81 |
| C. Three studies on afternoon naps and memory in older adults, with DOIs | all DOIs real and matching (web search) | — |

## Spot, Repeat, Verify

1. **Spot** (must). Notice when the answer is a count, a sum, a date or a source.
2. **Repeat** (important). Ask again in a fresh chat. Different answers mean at least one is wrong; matching answers can still be wrong (two runs both said 36).
3. **Verify** (must). Use a tool for numbers and open the source for facts. Don't ask ChatGPT to check itself and stop there.

## Boundary

One sentence, one receipt and one research question, ChatGPT without logging in, a few runs each, one morning. Signed-in versions with tools that run code may count better. Web search helped the sources here, but it is not always available.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
