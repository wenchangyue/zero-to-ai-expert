---
published: true
layout: lesson
title: "Stop Repeating Yourself to AI: Custom Instructions and Projects, Tested"
description: >-
  A tested way to stop re-explaining your background to AI: save it once as short
  rules, scope work rules to a project, and test each rule in a fresh chat.
date: '2026-10-03'
modified: '2026-10-03'
course: AI Tools and Workflows
level: Beginner
duration_label: 11 minutes
duration: PT10M54S
youtube_url: "https://youtu.be/2f_CKzQAXfs"
video_id: "2f_CKzQAXfs"
video_status: public
upload_date: "2026-10-03"
keywords:
  - custom instructions
  - ChatGPT projects
  - Claude projects
  - Instructions for Gemini
  - AI keeps forgetting
  - save prompt context
  - Zero to AI Expert
quick_answer: >-
  Save your background once as short rules (context, how answers should look,
  what never to do), put rules for one job in a project for that job, and test
  each rule in a fresh chat by asking the question that tempts the mistake. In one
  test (Claude Sonnet, 3 runs per setup, a fictional volunteer coordinator): with
  no background the answers were templates with 49 blanks across 9 answers; with
  her six rules pasted or saved, every answer passed every check; leaving one line
  out of the paste led 2 of 3 replies to promise a pickup date; and the saved rules
  signed a personal gift list "Dana" in 2 of 3 runs (0 of 3 without them).
learning_outcomes:
  - Explain why a fresh chat without memory needs your background every time.
  - Write saved instructions as context, how, and never rules.
  - Decide what belongs in global instructions and what belongs in a project.
  - Test saved instructions in a fresh chat, including the "never" rules.
faq:
  - question: Why does AI keep asking for the same details?
    answer: >-
      In this test each fresh chat had no past conversations and no memory, so the
      model only had what was in the chat. Asked for a shift reminder with no
      background, it returned templates with blanks for the date, time, place and
      names: 49 blanks across 9 answers, none signed, none with the right shift.
  - question: Is pasting my background every time enough?
    answer: >-
      When the paste was complete, all 9 answers passed every check. With the line
      "never promise a pickup date" left out, 2 of 3 replies promised the donor a
      specific Saturday. Pasting works until you forget a line.
  - question: Where do saved instructions go?
    answer: >-
      ChatGPT custom instructions apply to all chats; ChatGPT and Claude project
      instructions apply only to chats in that project, and in ChatGPT they override
      your global custom instructions. Gemini's "Instructions for Gemini" apply to
      every chat (personal accounts). In the test, saved instructions were simulated
      by adding them to the model's instructions; no app was tested.
  - question: Can saved instructions cause problems?
    answer: >-
      Yes. Dana's rule said "sign every message". With it saved, 2 of 3 gift-idea
      lists for her father were signed "Dana"; without saved instructions, 0 of 3.
      Rules for one job belong in a project for that job.
  - question: Is this a general result?
    answer: >-
      No. One model, one fictional person, three runs per setup; saved instructions
      simulated, app memory features not tested.
sources:
  - label: "OpenAI Help Center: ChatGPT Custom Instructions"
    url: https://help.openai.com/en/articles/8096356-chatgpt-custom-instructions
  - label: "OpenAI Help Center: Projects in ChatGPT"
    url: https://help.openai.com/en/articles/10169521-projects-in-chatgpt
  - label: "Claude Help Center: How can I create and manage projects?"
    url: https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects
  - label: "Gemini Apps Help: Customize Gemini's responses with your instructions"
    url: https://support.google.com/gemini/answer/16598625
  - label: Dana's six rules and the scoring rules, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-12/truth.md
  - label: All prompts and answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-12/all-runs.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-12/scores.json
---

## The problem

Every request needs the same background, and a fresh chat does not have it.

## The test

Dana (fictional) coordinates volunteers at a small food bank. Six rules, written before any run. Claude Sonnet, three fresh conversations per setup.

| Setup | Answers | Result |
| --- | --- | --- |
| No background | 9 | templates: 49 blanks, none signed, none with the right shift |
| Rules pasted every time | 9 | every answer passed every check (one added a date nobody gave) |
| Paste with "never promise a pickup date" left out | 3 | 2 promised a pickup date |
| Rules saved as instructions (simulated) | 9 | every answer passed every check |
| Saved rules, personal gift request | 3 | 2 signed "Dana" |
| No saved rules, same gift request | 3 | 0 signed |

## Save, Scope, Test

1. **Save** (must). Write it once as short rules: context (who you are, who you write for, the facts the task needs), how the answer should look, and what it must never do.
2. **Scope** (important). Rules for one job go in a project for that job. Global instructions hold only what is true in every chat.
3. **Test** (must). Open a fresh chat in the right place, give one real task, check each rule, and ask the question that tempts the mistake. Test again after every change.

Dana's saved rules:

> I'm Dana Okafor, volunteer coordinator at Riverside Food Bank, a small nonprofit.
> Most of what I write goes to volunteers: plain words, no jargon, no exclamation marks.
> Keep messages under 120 words.
> Volunteer shifts are Saturdays, 9 a.m. to noon, at our Elm Street warehouse.
> Sign every message "Dana".
> Never promise a delivery or pickup date; say we'll confirm one.

## Boundary

One model, one fictional person, three runs per setup. Saved instructions were simulated by adding them to the model's instructions; no app and no memory feature was tested. Product settings change; check your app's current help page.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
