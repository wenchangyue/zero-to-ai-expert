---
published: true
layout: lesson
title: "AI for Teachers: Draft a Lesson Pack Fast, Then Check It"
description: >-
  A tested routine for checking an AI-made lesson plan, quiz and feedback before
  class: a fresh chat reads it for errors, another takes the quiz blind, and you
  check every number and named fact against a source.
date: '2026-10-06'
modified: '2026-10-06'
course: AI Tools and Workflows
level: Beginner
duration_label: 11 minutes
duration: PT10M50S
youtube_url: "https://youtu.be/MEg85iH_bPg"
video_id: "MEg85iH_bPg"
video_status: public
upload_date: "2026-10-06"
keywords:
  - AI for teachers
  - AI lesson plan
  - AI quiz answer key
  - checking AI feedback
  - Moon phases lesson
  - Zero to AI Expert
quick_answer: >-
  Let AI draft the pack, then run three checks: paste the whole pack and the
  student answers into a new chat and ask for every factual error, quoted; give
  the quiz without its key to another new chat and look at every mismatch and
  wording flag; and check every number and named fact you will say against a
  trusted source. In one test (Claude Sonnet, a Grade 7 Moon-phases pack, 3
  runs), the packs took 20 to 27 seconds and the feedback was right in 9 of 9
  cases, but 2 of 3 plans said the Moon orbits Earth in about 29.5 days (the
  orbit is about 27; 29.5 is the cycle of phases). The fresh-chat check caught
  that 4 of 4 times but missed an activity tip that put the head's shadow at
  new moon.
learning_outcomes:
  - Explain why a mostly-correct AI lesson pack still needs line-by-line checks.
  - Run a fresh-chat fact check and a blind retake of a quiz.
  - Explain why agreement between two chats is not proof.
  - Check numbers and named facts, and walk through activities, before class.
faq:
  - question: How good was the AI's lesson pack?
    answer: >-
      Mostly good. Each pack had a sensible 45-minute plan with a lamp-and-ball
      model, a 10-question quiz with no wrong keys on reading, and feedback that
      praised the correct answer, corrected the Earth's-shadow idea and caught
      the swapped waxing and waning in all three runs. The problems were in
      lines that are easy to skim: two plans gave 29.5 days as the Moon's orbit,
      and one pack had a misleading note about the name "first quarter" and an
      activity tip with the shadow at the wrong position.
  - question: Does asking a fresh chat to check it work?
    answer: >-
      It helped here. It caught the orbit slip in 4 of 4 checks, flagged the
      quarter note, and reported no errors for the clean pack. But it missed the
      head-shadow tip in both checks of that pack, and it is the same kind of
      model as the writer, so it is a second reader, not a source. This check
      was added after seeing the first results.
  - question: What does a blind retake of the quiz show?
    answer: >-
      Whether a second chat, answering without the key, picks the same letters.
      All 60 answers matched here, and every retake flagged the wording of one
      question. Matching shows agreement, not proof; a mismatch could be a wrong
      key, an unclear question or the second chat's mistake. With no wrong keys
      in these quizzes, how reliably a retake catches one was not tested.
  - question: Can a teacher really do this in an hour?
    answer: >-
      Not measured. Drafting took seconds and each check under a minute; the
      teacher's own reading, source checking and adapting was not timed, and the
      test checked correctness, not teaching quality.
sources:
  - label: NASA Science, Moon Phases
    url: https://science.nasa.gov/moon/moon-phases/
  - label: NASA Science, Moon Facts
    url: https://science.nasa.gov/moon/facts/
  - label: NASA Science, eclipse types
    url: https://science.nasa.gov/eclipses/types/
  - label: NASA Space Place, What Are the Moon's Phases?
    url: https://spaceplace.nasa.gov/moon-phases/en/
  - label: Inputs, answer key, all prompts and answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-15/all-runs.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-15/scores.json
---

## The problem

AI can draft a lesson plan, a quiz and feedback in seconds. The risk is a confident wrong line you then say to a class.

## The test

A fictional Grade 7 lesson on Moon phases and three made-up student answers ([inputs](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-15/inputs.md)). The [answer key](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-15/truth.md) was fixed before the runs. One request to Claude Sonnet, three fresh runs.

| What | Result |
| --- | --- |
| Time per pack | 24, 27, 20 seconds |
| Feedback (3 students × 3 packs) | 9 / 9 right |
| Quiz keys (30 items) | 0 wrong on reading; blind retake 60 / 60 matched |
| Lesson plans | 2 of 3 said the orbit takes ~29.5 days (orbit ~27; phases ~29.5) |
| Pack 1 extras | misleading "quarter" note; head's shadow placed at new moon |
| Fresh-chat check | orbit slip 4 / 4; quarter note flagged 2 / 2; clean pack "no errors" 2 / 2; shadow tip missed 2 / 2 |

## Fresh Eyes, Blind Retake, Source It

1. **Fresh eyes** (must). Paste the whole pack and the student answers into a new chat: "Check this before it's used in class. List every factual error, quote it exactly, and say what's wrong." Check each flag yourself.
2. **Blind retake** (important). Give the quiz without the key to another new chat; ask for a letter and a short reason per question, and which questions could have two answers. Treat any mismatch as a reason to check the question, the key and the reasoning.
3. **Source it** (must). Check every number and named fact you'll say against a source you trust, and walk through any activity yourself.

Whether the lesson fits your students is still your judgment.

## Boundary

One model, one topic, one grade, three runs. Correctness only, not teaching quality; teacher time not measured. The fresh-chat check was added after seeing the first results; the head-shadow error was found by an independent review of this lesson's script.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
