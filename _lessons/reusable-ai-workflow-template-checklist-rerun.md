---
published: true
layout: lesson
title: "Your First Reusable AI Workflow: A Template and a Checklist, Tested"
description: >-
  A tested way to make a weekly AI task come out right every week: write a
  template once, keep a short checklist you run yourself, and rerun it on new
  inputs before you trust it.
date: '2026-10-04'
modified: '2026-10-04'
course: AI Tools and Workflows
level: Beginner
duration_label: 11 minutes
duration: PT10M53S
youtube_url: "https://youtu.be/rjFC-JG5CEU"
video_id: "rjFC-JG5CEU"
video_status: public
upload_date: "2026-10-04"
keywords:
  - reusable AI workflow
  - prompt template
  - AI checklist
  - school newsletter summary
  - consistent AI answers
  - Zero to AI Expert
quick_answer: >-
  Write the job description once as a template (the shape of the answer and
  every rule you would otherwise forget), keep a three- or four-line checklist
  you run yourself against the source, and rerun the template on two new inputs
  before you trust it. In one test (Claude Sonnet, two fictional school
  newsletters, 3 runs per setup), requests typed fresh each week had 27 of 39
  events and deadlines with the right date and no consistent format; a template
  had 39 of 39 with the same four columns; adding an AI self-check gave the same
  score, no reported fixes, and longer answers.
learning_outcomes:
  - Explain why a request retyped each week gives different answers.
  - Write a template by turning last week's fixes into rules.
  - Keep a short checklist you run yourself, separate from any AI self-check.
  - Rerun a template on new inputs and fix the template, not just the answer.
faq:
  - question: Why does the same AI task come out differently each week?
    answer: >-
      Your request is the whole job description. In the test, "What do I need to
      know from this school newsletter?" led two of three answers to put picture
      day on the wrong date, and "Summarize … for my third grader" turned all three
      week-3 answers into notes written to the child. The newsletter changed too,
      so the test can't fully separate wording from content.
  - question: What goes in a template?
    answer: >-
      Start from last week's answer and turn every fix into a rule: who it is for,
      the format (here a table with Date | What | Bring or pay | Deadline), how to
      handle dates given as weekdays, what to leave out, and "not stated" for gaps.
      The exact template is linked below.
  - question: Does asking the AI to check its own answer help?
    answer: >-
      In this test it made no measurable difference: the template alone already
      passed every event-and-date check, the checklist answers reported no fixes,
      and they were longer (median 354 vs 220 words). It was never tested on an
      answer with a known mistake. Keep your own short check against the source.
  - question: Was the test fair?
    answer: >-
      The first template's example date ("Wed Oct 14") was the correct week-2
      picture-day date, so the template setups were re-run with "Mon Jan 5". The
      results here are from the re-run; the first runs are published too.
sources:
  - label: The two newsletters (fictional)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-13/week2.txt
  - label: Answer key, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-13/truth.md
  - label: The template and checklist
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-13/template.txt
  - label: All prompts and answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-13/all-runs.json
  - label: Scores and calendar check
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-13/scores.json
---

## The problem

A task you hand to AI every week (here, a school newsletter for a Grade 3 parent) comes back differently each time.

## The test

Two fictional newsletters with traps, an answer key fixed before any run, Claude Sonnet, three fresh runs per setup per week.

| Setup | Events and deadlines with the right date | Wrong calendar dates | Format |
| --- | --- | --- | --- |
| Typed fresh each week | 27 / 39 | 2 answers | no tables; week 3 written to the child |
| Template | 39 / 39 | 0 of 72 weekday-date pairs | the same four columns |
| Template + AI checklist | 39 / 39 | 0 of 92 pairs | same; no fixes reported; longer |

All setups avoided the traps (other grades, the cancelled book fair, the corrected retake date).

## Template, Checklist, Rerun

1. **Template** (must). The shape of the answer plus every rule you would otherwise forget. Build it from last week's fixes.
2. **Checklist** (must). Three or four lines you check yourself against the source: dates (especially worked-out ones), other grades and cancelled items, corrections. The AI's ticks don't count as your check.
3. **Rerun** (important). Two new inputs before you trust it. Fix the template, not just one answer.

## Boundary

One model, one fictional school, two short and clean newsletters, three runs per setup. The AI self-check was never given an answer with a known mistake.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
