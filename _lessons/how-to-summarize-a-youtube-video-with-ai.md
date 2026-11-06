---
published: true
layout: lesson
title: "How to Summarize a YouTube Video with AI (and Catch Fakes)"
description: >-
  One 5:38 video whose every word is known, tested with ChatGPT (link only, then the
  transcript pasted in) and Gemini Notebook, formerly NotebookLM (link as the source):
  the same follow-up questions, scored against an answer key fixed before the runs.
date: '2026-11-06'
modified: '2026-11-06'
course: AI Tools and Workflows
level: Beginner
duration_label: 5 minutes
duration: PT4M42S
youtube_url: "https://youtu.be/ykK3miO8F2s"
video_id: "ykK3miO8F2s"
video_status: public
upload_date: "2026-11-06"
keywords:
  - how to summarize a YouTube video
  - summarize YouTube video with AI
  - summarize YouTube video with ChatGPT
  - NotebookLM YouTube video
  - YouTube transcript
  - Zero to AI Expert
quick_answer: >-
  Give the AI the video's words: paste the transcript into ChatGPT, or add the link to a
  Gemini Notebook (formerly NotebookLM). Then ask about something you know isn't in the
  video; the right answer is that it isn't mentioned. In a test on 2026-11-06 with one
  5:38 video and three runs each, logged-out ChatGPT with only the link said it couldn't
  get the video in 3 of 3 chats, yet follow-up questions drew invented answers in 2 of 3.
  With the transcript pasted, and in Gemini Notebook, every run named the right steps and
  said what the video didn't contain.
learning_outcomes:
  - Get a summary from a pasted transcript or a Gemini Notebook source.
  - Recognize when a chatbot doesn't have the video.
  - Use a trap question to check that the tool is reading the video.
  - Know what a transcript-based summary can't contain.
faq:
  - question: Can ChatGPT summarize a YouTube video from a link?
    answer: >-
      In this test, logged out, it couldn't: all three chats said they couldn't get the
      video and asked for the transcript. A signed-in account may handle links differently.
  - question: What happens if I keep asking after it says it can't get the video?
    answer: >-
      In two of three chats it then gave invented answers, including "Direction, Location,
      Execution" for a method that is really called Spot, Repeat, Verify, and a sentence
      about "strawberry" that the video never uses. One chat declined every time.
  - question: How do I get the transcript of a YouTube video?
    answer: >-
      Open the video's description and click Show transcript, then copy the text. Videos
      without captions may have no transcript.
  - question: Can NotebookLM read YouTube videos?
    answer: >-
      Yes in this test. In Gemini Notebook (formerly NotebookLM), Add sources, then Websites,
      took the link, and all three notebooks answered from the transcript. Clicking a
      citation number opened the transcript with the lines highlighted.
  - question: What does an AI summary of a video miss?
    answer: >-
      Anything shown but not spoken isn't in the transcript. Summaries also dropped details:
      only one of six kept the video's main number, one notebook said the method
      "guarantees reliability", and another stated a "probably" as fact.
sources:
  - label: The video tested (lesson 23)
    url: https://youtu.be/PiRxOTFrYNg
  - label: Answer key
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-26/truth.md
  - label: Hash and time
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-26/fixed-before-runs.sha256
  - label: Every answer
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-26/all-answers.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-26/scores.json
  - label: Design
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-26/design.md
  - label: Google, "NotebookLM is now Gemini Notebook"
    url: https://blog.google/innovation-and-ai/products/gemini-notebook/notebooklm-gemini-notebook/
---

## The problem

You want a video's main points without watching it. An AI will often give you a summary, but is it a summary of that video?

## The test

One video whose every word we hold: our own lesson 23 (5:38). The same four turns on 2026-11-06, three runs each: a five-bullet summary, the method's three steps, an exact sentence that appears only on screen, and a trap question about Claude, which the video never mentions.

| Question | ChatGPT, logged out, link only | ChatGPT, logged out, transcript pasted | Gemini Notebook, link as source |
| --- | --- | --- | --- |
| Summarize in 5 bullets | Said it couldn't get the video, 3 of 3 | Summary of the right video, 3 of 3 | Summary of the right video, 3 of 3 |
| The three steps | Invented 1, declined 2 | Right, 3 of 3 | Right, 3 of 3 |
| The exact on-screen sentence | Invented 2 ("strawberry"), declined 1 | Said it isn't in the transcript, 3 of 3 | Said it isn't in the transcript, 3 of 3 |
| What it says about Claude | Invented 1, declined 2 | Said it isn't mentioned, 3 of 3 | Said it isn't mentioned, 3 of 3 |

Of the six real summaries, all six named the method, and one kept the main number (44). One notebook wrote that the method "guarantees reliability", while the video says matching answers can still be wrong. Another stated the video's "probably" as fact. Gemini's own app was not tested: its page raised a browser permission prompt that only the account owner can answer.

## Words, Trap, Watch

1. **Words** (must). Paste the transcript, or add the link to a notebook. If it says it can't get the video, start again with the transcript.
2. **Trap** (must). Ask about something you know isn't in the video. The right answer is that it isn't mentioned. If it answers anyway, it's guessing. Passing doesn't prove the rest is right.
3. **Watch** (important). Watch the part you'll quote or rely on, and anything shown on screen.

## Boundary

One short video with clean captions, three runs each, one morning. ChatGPT was logged out, and a signed-in account may handle links differently. Gemini Notebook was on a paid plan. A video with no captions may have no transcript to use.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
