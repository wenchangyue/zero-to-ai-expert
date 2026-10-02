---
published: true
layout: lesson
title: "How to Check the Sources in an AI Research Answer (Open, Find, Trace)"
description: >-
  A tested way to check the sources in an AI research answer: open every link,
  find the exact sentence behind every number, and trace the numbers you will
  repeat back to the original report.
date: '2026-10-02'
modified: '2026-10-02'
course: AI Tools and Workflows
level: Beginner
duration_label: 11 minutes
duration: PT10M30S
youtube_url: "https://youtu.be/1Y0RqEZ8t70"
video_id: "1Y0RqEZ8t70"
video_status: public
upload_date: "2026-10-02"
keywords:
  - AI research sources
  - check AI citations
  - fake links AI
  - verify AI answer
  - web search AI
  - statistically significant
  - Zero to AI Expert
quick_answer: >-
  Open every link the AI gives you; a dead link means you cannot check the claim
  through it. Ask for the exact sentence behind every number, with its link, and
  search the page for it. For numbers you will repeat, trace them to the original
  study and read how they were measured. In one test (Claude Sonnet, 3 runs per
  setup, one question about the UK's 2022 four-day week trial), 8 of 13 links
  given without web search returned "page not found"; with search no link
  returned 404 but no number was tied to a page; asking for the exact sentence
  gave 37 of 37 quotes found word for word. None of the 9 answers mentioned that
  the report says its staff-turnover drop is not statistically significant.
learning_outcomes:
  - Check whether an AI answer's links open, and what a dead link does and does not tell you.
  - Use one request that ties every number to a link and an exact sentence.
  - Find the caveat a summary leaves out by tracing a number to the original report.
faq:
  - question: Does AI make up sources?
    answer: >-
      In this test, without web search, 8 of 13 links in three answers returned
      "page not found" (HTTP 404) while real pages on the same sites opened with the
      same checker. A 404 does not prove a page never existed, but you cannot check
      anything through it. The numbers in those answers were mostly right; two of
      three answers attached a number to the wrong measure.
  - question: Does web search fix it?
    answer: >-
      Partly. With search, none of 20 links returned 404 (5 sites blocked the
      checker), but the sources sat in a list at the end and no number was tied to a
      page. Of the 15 links that opened, 7 stated the trial's headline results
      (92%, 71% and 57%); others covered the one-year follow-up or opinion. One answer
      put the 1.4% revenue figure on the wrong comparison.
  - question: What request makes sources checkable?
    answer: >-
      "For every number, give the link you got it from and copy the exact sentence
      from that page that contains it. Use the original report where you can. If you
      couldn't open a page, say so." In three runs, 37 of 37 quoted passages were found
      word for word on the linked page, and all three answers said they could not read
      the report PDF and used the publisher's results page instead.
  - question: Is an exact quote enough?
    answer: >-
      No. All three quote answers copied the summary sentence that staff leaving
      "decreased significantly, dropping by 57%". The report body says the researchers
      "are unable to say that these three trends are statistically significant",
      pointing to the small number of companies and job-market conditions. None of the
      nine answers mentioned it. Trace numbers you will repeat to the original.
  - question: Is this a general result?
    answer: >-
      No. One question, one model, three runs per setup. A different topic, tool or
      model could do better or worse, and some links could not be checked because the
      sites blocked automated requests.
sources:
  - label: "Autonomy: The results are in: The UK's four-day week pilot (February 2023, PDF)"
    url: https://autonomy.work/wp-content/uploads/2023/02/The-results-are-in-The-UKs-four-day-week-pilot.pdf
  - label: "Autonomy: results page for the pilot"
    url: https://autonomy.work/portfolio/uk4dwpilotresults/
  - label: Answer key, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-11/truth.md
  - label: All prompts and answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-11/all-runs.json
  - label: Link and quote checks, and scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-11/scores.json
---

## The problem

An AI research answer comes with a tidy list of sources. The question is whether those sources say what the answer says.

## The test

One question: did the UK's 2022 four-day week trial work? The answer key was written from the original report before any run. Claude Sonnet, three fresh conversations for each of three setups.

| Setup | Links | Returned 404 | What went wrong |
| --- | --- | --- | --- |
| No web search | 13 | 8 | numbers mostly right; 2 of 3 answers put a number on the wrong measure |
| Web search | 20 | 0 (5 blocked the checker) | sources listed at the end, no number tied to a page; 1 answer swapped the two revenue comparisons, 1 gave the researchers a caveat no page I could open says |
| Search + exact sentence for every number | 7 | 0 | 37 of 37 quotes found word for word; 0 numbers on the wrong measure |

None of the nine answers said that the report body calls the drop in staff leaving not statistically significant.

## Open, Find, Trace

1. **Open** (must). Click every link. If it is dead, you cannot check the claim through it: find another source or leave it out.
2. **Find** (must). Ask for the exact sentence behind every number, then search the page for it (Ctrl-F or Command-F; it works in a browser PDF viewer too).
3. **Trace** (important, for the numbers you will repeat). Open the original study and read how the number was measured: how many, compared with what, and whether the authors call it significant or only large.

The request used in the lesson:

> For every number, give the link you got it from and copy the exact sentence from that page that contains it. Use the original report where you can. If you couldn't open a page, say so.

## Summary versus body

- Summary: "The number of staff leaving participating companies decreased significantly, dropping by 57% over the trial period."
- Body, same report: "we are unable to say that these three trends are statistically significant."

Both revenue figures (+1.4% start to end of the trial; +35% against an earlier comparable six months) come from 23 and 24 of the 61 companies.

## Boundary

One question, one model, three runs per setup; links checked on 2026-10-02. This lesson says nothing about whether a four-day week is a good idea.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
