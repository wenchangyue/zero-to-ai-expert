---
published: true
layout: lesson
title: "How to Use ChatGPT to Study: Make It Quiz You on Your Notes"
description: >-
  Three ways to study one page of notes with ChatGPT, three runs each, checked
  against an answer key fixed before the runs: a study guide, practice questions
  that quote your notes, and a one-question-at-a-time quiz, plus the check you do
  yourself.
date: '2026-10-23'
modified: '2026-10-23'
course: AI Tools and Workflows
level: Beginner
duration_label: 6 minutes
duration: PT6M16S
youtube_url: "https://youtu.be/MpFi8aBIlyk"
video_id: "MpFi8aBIlyk"
video_status: public
upload_date: "2026-10-23"
keywords:
  - how to use ChatGPT to study
  - ChatGPT for studying
  - study for exams with ChatGPT
  - ChatGPT quiz
  - AI for students
  - Zero to AI Expert
quick_answer: >-
  Paste your own notes, say what is on the exam, and ask ChatGPT to quiz you one
  question at a time and to quote the line from your notes after each answer.
  In a test on one page of made-up biology notes (ChatGPT, logged out,
  2026-10-23): a plain study guide covered all 10 must-know items and respected
  the exam scope, but ran 1,132–1,299 words (notes: 230) and added terms the
  notes never mention; practice questions with quoted note lines matched the
  notes word for word in all 24 questions; a one-at-a-time quiz caught a
  deliberately wrong answer in 3 of 3 runs, quoting the exact note line.
learning_outcomes:
  - Turn your own notes into a quiz instead of a reading guide.
  - Ask for the line from your notes after every answer.
  - Check a quoted line with Ctrl F / Cmd F in your notes.
  - Spot study-guide content that is not from your class.
faq:
  - question: How do I use ChatGPT to study for an exam?
    answer: >-
      Paste your notes and say what is on the exam. Then ask it to quiz you one
      question at a time, wait for your answer, tell you if you are right, and
      quote the line from your notes. Answer before you look. Practice testing
      is one of the two study methods rated "high utility" in a large review
      (Dunlosky et al., 2013); rereading and summarization were rated low.
  - question: Is a ChatGPT study guide accurate?
    answer: >-
      In this test the guides were accurate for the 10 preset items and kept the
      teacher's exam scope, but they were about five times longer than the notes
      and added terms the notes never mention (RuBP in 3 of 3 guides). Those
      terms are not wrong, just not from the class.
  - question: Can ChatGPT tell me which parts of its guide are not in my notes?
    answer: >-
      It gave a long list each time and always included RuBP, but in 2 of 3
      runs the list missed "ATP synthase", which the guide had used as a wrong
      option in its own quiz. Search your notes for any term you don't recognize.
  - question: How do I check the quoted lines?
    answer: >-
      Search your notes for a few words of the quote with Ctrl F (Cmd F on a
      Mac). If there is no match, ask which line of your notes says that.
sources:
  - label: The notes
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-22/notes.txt
  - label: Answer key (hash recorded before the first run)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-22/truth.md
  - label: Hashes and time
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-22/fixed-before-runs.sha256
  - label: Every answer (ads removed)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-22/all-answers.json
  - label: Self-check runs (study guide, then "which terms are not in my notes?")
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-22/self-check-runs.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-22/scores.json
  - label: "Dunlosky et al. (2013), Psychological Science in the Public Interest 14(1):4–58"
    url: https://doi.org/10.1177/1529100612453266
---

## The problem

ChatGPT can turn your notes into a study guide in seconds. But reading a guide feels like studying without testing you, and you can't easily tell which parts came from your class.

## The test

One page of made-up biology notes (230 words, with a professor's exam tip and an exam-scope line), ChatGPT on the web without logging in, fresh chats, 2026-10-23 between 08:48 and 09:01 New York time. The 10 must-know items were fixed and hashed before the first run. Requests C and D were added after seeing the first results.

| Request | Result (3 runs each) |
| --- | --- |
| A. "Make me a study guide from these notes." | 10 of 10 items, exam scope kept, ended with a practice quiz; 1,132–1,299 words; added terms not in the notes (RuBP 3/3) |
| B. 8 practice questions using only my notes, quoting the line each answer comes from | 10 of 10 items; 24 of 24 quote blocks match the notes word for word; 563–717 words; several questions ask two things at once |
| C. Quiz me one question at a time; I answered "Carbon dioxide." | 3 of 3: "Not quite", gave water, quoted the exact note line, then asked the next question and waited |
| D. Study guide, then "Which terms or facts in your study guide are not in my notes?" | RuBP listed 3/3; "ATP synthase" (a wrong option in its own quiz) missing from the list in 2/3 |

Labeled ads appeared under every study guide and on some other pages. They are not part of the answers and are removed from the published files.

## Feed, Quiz, Check

1. **Feed** (must). Paste your own notes and say what is on the exam. Your notes give it the material to work from, and give you something to check its answers against.
2. **Quiz** (must). One question at a time; answer before you look.
3. **Check** (important). Ask for the line from your notes after every answer; search your notes for anything that surprises you.

## Boundary

One short page of made-up notes on standard biology, ChatGPT without logging in, a few runs per request, one morning. Long notes and PDFs can behave differently. It quotes your notes faithfully, so errors in your notes can carry into the quiz.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
