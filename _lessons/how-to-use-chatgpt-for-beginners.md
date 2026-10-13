---
published: true
layout: lesson
title: "How to Use ChatGPT for Beginners: Your First Real Task"
description: >-
  A beginner's first real task in ChatGPT, tested on screen: what a short request
  gets back, what a request with context gets, how to refine in the same chat,
  and the one check ChatGPT got wrong about its own answer.
date: '2026-10-13'
modified: '2026-10-13'
course: AI Tools and Workflows
level: Beginner
duration_label: 8 minutes
duration: PT8M32S
youtube_url: "https://youtu.be/QEB_9AhZsQA"
video_id: "QEB_9AhZsQA"
video_status: public
upload_date: "2026-10-13"
keywords:
  - how to use ChatGPT
  - ChatGPT for beginners
  - ChatGPT tutorial
  - ChatGPT prompts
  - write an email with ChatGPT
  - Zero to AI Expert
quick_answer: >-
  Type the situation, not just the task: what happened, what you want, by when,
  how long and in what tone, and whose name goes on it. In a test on 2026-10-13
  (ChatGPT on the web, logged out), "Write an email to my landlord." got a
  question back in 3 of 3 new chats, while a request with the situation came back
  ready to send in 3 of 3. Then refine in the same chat and read every line: a
  "firmer" rewrite added an untrue "I'm writing to follow up", and ChatGPT
  reported its email as 77 words when a real count was 69.
learning_outcomes:
  - Start a first task in ChatGPT without an account.
  - Write a request that includes the situation, not just the task.
  - Refine an answer in the same chat and reread the whole result.
  - Check counts, dates and prices yourself instead of asking ChatGPT.
faq:
  - question: Do I need an account to use ChatGPT?
    answer: >-
      Not to try it. On 2026-10-13, chatgpt.com showed an "Ask ChatGPT" box to a
      logged-out visitor. The page footer says chats may be reviewed and used to
      improve the models, so leave out passwords, account numbers and anything
      private.
  - question: Why did ChatGPT ask me a question instead of writing the email?
    answer: >-
      The request didn't say what the email was about. In 3 of 3 new chats,
      "Write an email to my landlord." got back a question (a repair, rent, a
      noise complaint, a lease issue?) instead of a draft. Putting the situation
      in the first message produced a usable email in 3 of 3.
  - question: Can I trust ChatGPT's word count?
    answer: >-
      Check it yourself. Asked whether its email was still under 100 words,
      ChatGPT said yes, 77 words including subject, greeting and signature; a
      script counted 69 (64 without the subject). The verdict was right, the
      number wasn't. In Google Docs, use Tools > Word count.
  - question: Is this how ChatGPT always answers?
    answer: >-
      No guarantee. This was one task on one day, logged out; the model version
      isn't shown, and answers change between versions, plans and days.
sources:
  - label: Every prompt and answer (captured from the screen)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-19/all-runs.json
  - label: Answer key, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-19/truth.md
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-19/scores.json
  - label: OpenAI API docs, Concepts (tokens)
    url: https://developers.openai.com/api/docs/concepts
  - label: Google Docs Help, word count
    url: https://support.google.com/docs/answer/39003
---

## The problem

You open ChatGPT for the first time. What do you type, and how do you know the answer is any good?

## The test

One everyday task, asking a landlord to fix a leaking kitchen faucet, in ChatGPT on the web, logged out, on 2026-10-13. Each prompt ran in 3 new chats; the follow-ups ran once in the first chat. Details (faucet, three days, the name Alex) are made up.

| Request | Result |
| --- | --- |
| "Write an email to my landlord." | Asked a question back, **3 / 3** |
| The situation: what happened, how long, what you want, by when, under 100 words, sign it Alex | Ready to send, **3 / 3** (no blanks, signed Alex, 69–77 words with subject) |
| "Make it a little firmer, and ask them to reply by Friday." | Done ("Urgent", confirm by Friday), but added **"I'm writing to follow up"** |
| "Is it still under 100 words? Count them." | Said **77**; a real count was **69** (64 without the subject) |

## Context, Refine, Check

1. **Context** (must). Put in what happened, what you want, by when, length and tone, and your name. If ChatGPT asks you a question back, context was missing.
2. **Refine** (important). Stay in the same chat, say exactly what to change, then reread the whole answer. Start a new chat for a different job.
3. **Check** (must). Read every line for things you didn't say. Check counts, dates and prices yourself (Google Docs: Tools > Word count).

## Why the word count was off (likely)

Models read text in tokens, chunks that don't line up with words ([OpenAI docs](https://developers.openai.com/api/docs/concepts)), so a word count is closer to an estimate unless something actually counts. This is a likely reason, not something this test proves.

## Boundary

One task, one day, ChatGPT logged out; the model version isn't shown; answers change between versions and plans. For facts that aren't yours (medical questions, local laws), ChatGPT is a starting point, not the answer.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
