---
published: true
layout: lesson
title: "Before You Automate a Daily AI Summary: Checks for Silent Failures"
description: >-
  A tested way to make the AI step of a daily automation tell you when its input
  broke: a status line, a coverage line, and a heartbeat for runs that never
  happen.
date: '2026-10-09'
modified: '2026-10-09'
course: AI Tools and Workflows
level: Beginner
duration_label: 10 minutes
duration: PT10M19S
youtube_url: "https://youtu.be/NClaBwp-IuQ"
video_id: "NClaBwp-IuQ"
video_status: public
upload_date: "2026-10-09"
keywords:
  - AI automation
  - no-code automation
  - silent failures
  - AI email summary
  - monitoring automations
  - Zero to AI Expert
quick_answer: >-
  Make every automated AI message start with a status line (OK or ALERT, with
  rules for the failures you can name), end with a coverage line (dates and
  count), and know when it should arrive so a missing message prompts a check.
  In one test (Claude Sonnet, a fictional bakery inbox, ten mornings, 3 runs), a
  plain instruction caught an empty inbox, an error page and missing emails every
  time, but summarized a re-sent, two-day-old batch as new in every run; with the
  status and coverage lines, all four broken mornings got an ALERT and none of
  the normal mornings did. No trigger, connection or delivery was built.
learning_outcomes:
  - Describe the three parts of a daily automation (trigger, AI step, output).
  - Explain why stale input can pass silently while obvious failures don't.
  - Write a status line and a coverage line for an automated AI message.
  - Use a heartbeat and deliberate broken inputs to test an automation.
faq:
  - question: Did this lesson build a no-code automation?
    answer: >-
      No. The previous lesson promised a daily task running on its own; doing that
      properly needs an account on an automation service, which this channel
      doesn't create. The lesson tests the AI step with simulated inputs, the way
      an automation would pass them.
  - question: Which failures did the plain AI step miss?
    answer: >-
      It flagged an empty inbox, an error page and a list with missing emails in
      3 of 3 runs each. It missed a stale re-send in 3 of 3: emails from Thursday
      and Friday were summarized on Saturday as if new ("4 emails came in
      overnight"), even though each run noticed one email was sent Thursday.
  - question: Is the coverage line a guarantee?
    answer: >-
      No. The AI writes it too, so it can be wrong, and it can't show emails that
      never reached the step. It gives you a quick claim to check; compare it with
      the inbox when accuracy matters.
  - question: What catches an automation that never runs?
    answer: >-
      A heartbeat: know when the message should arrive and treat a missing one as
      a reason to look (it may not have started, may still be running, or may not
      have been delivered). Status and coverage only help when a message arrives.
sources:
  - label: The ten mornings of input (fictional)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-18/inputs.json
  - label: The two instructions
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-18/instructions.md
  - label: Answer key, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-18/truth.md
  - label: All replies
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-18/all-runs.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-18/scores.json
---

## The problem

A daily automation (trigger → AI step → message) can keep sending normal-looking messages after its input has quietly broken, or stop sending anything at all.

## The test

Ten mornings of a fictional bakery inbox, four of them broken; an answer key fixed first; Claude Sonnet, each morning in a fresh chat, 3 runs, two instructions written before the runs. No trigger, connection or delivery was built.

| Broken morning | Plain step flagged | With status + coverage |
| --- | --- | --- |
| Nothing arrived | 3 / 3 | 3 / 3 |
| Error page instead of emails | 3 / 3 | 3 / 3 |
| Header promises more emails | 3 / 3 | 3 / 3 |
| Yesterday's batch re-sent | **0 / 3** | 3 / 3 |
| Normal mornings flagged | 0 / 18 | 0 / 18 |

## Status, Coverage, Heartbeat

1. **Status** (must). First line: OK or ALERT and why. Name the failures: nothing arrived, old, not what you expected, count mismatch. ([wording used](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-18/instructions.md))
2. **Coverage** (important). Last line: date range and count. The AI writes it too; check against the inbox when it matters.
3. **Heartbeat** (must). Know when the message should arrive; a missing message is a reason to look.

Before switching it on, break it on purpose: paste an empty input, last week's emails with today's date, an error message, and a half-missing list into a chat with the same instruction.

## Boundary

One model, one fictional inbox, four failure types chosen by us, run in one batch; the normal mornings had no genuinely quiet night; real automations can also break before the AI step (wrong account, filters).

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
