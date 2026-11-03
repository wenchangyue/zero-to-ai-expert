---
published: true
layout: lesson
title: "How to Use NotebookLM to Study (Now Gemini Notebook)"
description: >-
  One page of class notes in three new Gemini Notebook (formerly NotebookLM) notebooks:
  an out-of-notes question, a study guide, a one-question-at-a-time quiz with a wrong
  answer, and the Studio quiz, scored against an answer key fixed before the runs.
date: '2026-11-03'
modified: '2026-11-03'
course: AI Tools and Workflows
level: Beginner
duration_label: 5 minutes
duration: PT4M44S
youtube_url: "https://youtu.be/bwKUkeKQBec"
video_id: "bwKUkeKQBec"
video_status: public
upload_date: "2026-11-03"
keywords:
  - how to use NotebookLM to study
  - NotebookLM for studying
  - Gemini Notebook
  - NotebookLM quiz
  - AI for students
  - Zero to AI Expert
quick_answer: >-
  Make a notebook whose only source is your class notes (Add sources → Copied text, or
  upload a file), ask it to quiz you one question at a time, answer before you look, and
  click the small citation number to see the line in your notes. In a test on 2026-11-03
  (Gemini Notebook, three new notebooks, one 230-word page of fictional biology notes): a
  question the notes don't cover got "your notes don't explain that" plus an offer to
  search the web in 3 of 3; a deliberately wrong quiz answer was caught in 3 of 3 with the
  exact notes line quoted; the study guide covered 10 of 10 key points and did not teach
  RuBP (ChatGPT's guides on the same notes did, 3 of 3), but added textbook words and ran
  1,682–2,003 words.
learning_outcomes:
  - Set up a notebook whose only source is your own notes.
  - Make it quiz you one question at a time, and use the Studio quiz.
  - Check an answer by clicking its citation number.
  - Know what a generated study guide adds beyond your notes.
faq:
  - question: Is NotebookLM the same as Gemini Notebook?
    answer: >-
      Yes. Google renamed NotebookLM to Gemini Notebook in July 2026; it is the same
      product and the old address still works.
  - question: Does NotebookLM answer questions my notes don't cover?
    answer: >-
      In this test it didn't, from the chat: asked about photorespiration, which the
      notes never explain, all three notebooks said the notes don't explain it, pointed
      to the exam-scope line, and offered to search the web instead.
  - question: Does the NotebookLM study guide stick to my notes?
    answer: >-
      Mostly the topics, not the words. All three guides covered every key point and none
      taught RuBP, but every guide added textbook terms the notes never use (for example
      "photolytic", "glyceraldehyde") and ran about 7 to 9 times the notes' length. Each
      guide also included ten practice questions with an answer key.
  - question: How do I check an answer?
    answer: >-
      Click the small number next to the answer. The source panel opens your notes with
      the cited passage highlighted.
  - question: Can it give away quiz answers?
    answer: >-
      In one of three runs, the suggested reply buttons under the first question included
      "It comes from water", the right answer. Answer in your head before you look down.
sources:
  - label: The notes (same as lesson 22)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-25/notes.txt
  - label: Answer key (hash recorded before the first chat turn)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-25/truth.md
  - label: Hashes and time
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-25/fixed-before-runs.sha256
  - label: Every answer and study guide
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-25/all-answers.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-25/scores.json
  - label: Design and results
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-25/design.md
  - label: Google, "NotebookLM is now Gemini Notebook"
    url: https://blog.google/innovation-and-ai/products/gemini-notebook/notebooklm-gemini-notebook/
---

## The problem

You have class notes and an exam. An AI study tool can turn them into a guide or a quiz, but will it stay inside your class, and how do you check it?

## The test

Gemini Notebook (formerly NotebookLM) on the web, a paid account, 2026-11-03 between 08:45 and 09:55 New York time. Three new notebooks, each with the same one-page fictional BIO 101 notes (230 words, from lesson 22) as the only source. In each notebook the same four chat turns ran in order, then the Studio quiz. The answer key was fixed and hashed before the first chat turn. A pilot notebook used to learn the interface is not scored.

| Request | Result (3 notebooks) |
| --- | --- |
| "Make me a study guide from these notes." | Created a Studio report instead of a chat answer; 10 of 10 key points; no RuBP; textbook words not in the notes in every guide; 1,682–2,003 words; ten practice questions with an answer key |
| "What is photorespiration, and why does it matter for C4 plants?" (not in the notes) | Said the notes don't explain it, pointed to "C4 and CAM plants are NOT on this exam", offered web research, 3 of 3 |
| "Quiz me … one question at a time. Start with where the oxygen that plants release comes from …" | Asked and waited, 3 of 3; in run 3 the suggested reply buttons included "It comes from water" |
| "Carbon dioxide." (deliberately wrong) | "Not quite", water, the exact notes line quoted with a citation number, 3 of 3 |
| Studio → Quiz → Generate now | Ten multiple-choice questions, 3 of 3 |

Same notes in ChatGPT (lesson 22): study guides of 1,132–1,299 words, RuBP in 3 of 3.

## Source, Quiz, Click

1. **Source** (must). Put in only your class notes, so you know what you're checking against.
2. **Quiz** (must). One question at a time, or the Studio quiz. Answer before you look.
3. **Click** (important). Click the small number next to an answer and read the highlighted lines in your notes.

## Boundary

One page of notes on standard biology, three notebooks, one morning, a paid account. Long PDFs, messy notes and free accounts can behave differently. A quote can match your notes and still be wrong, if your notes are.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
