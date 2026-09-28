---
published: true
layout: lesson
title: "AI Kept What I Told It Through 180,000 Tokens. A New Chat Had None of It."
description: >-
  Four facts given in the first message of a chat, then one dinner question,
  with twelve unrelated requests, a huge pasted log, a new chat, or a new chat
  with a short note in between. Three runs each, token counts from the tool.
date: '2026-09-28'
modified: '2026-09-28'
course: AI Tools and Workflows
level: Beginner
duration_label: 6 minutes
duration: PT6M27S
youtube_url: "https://youtu.be/fYA2ThOWiTE"
video_id: "fYA2ThOWiTE"
video_status: public
upload_date: "2026-09-28"
keywords:
  - does AI forget what you told it
  - why AI forgets mid-conversation
  - context window explained for beginners
  - tokens explained
  - AI new chat does not remember
  - how to give AI context
  - Zero to AI Expert
quick_answer: >-
  In this test it did not forget inside the chat. Four facts given in the first
  message were used in every answer after twelve unrelated requests, and, in a
  separate test, after a pasted 4,000-entry log that brought the input to about
  180,000 tokens. In a new chat that never contained the facts, 7 of 23 listed
  options clearly broke one. Pasting a 61-word note of the facts at the top of
  a new chat brought them back in every answer. When AI seems to have
  forgotten something, first check whether the chat you are in actually
  contains it. What happens past an app's limit, and cases where the facts are
  present but overlooked, were not tested.
learning_outcomes:
  - Understand that each reply is produced with the conversation so far as its input.
  - Know what a token and a context window are, and that limits differ by model and app.
  - Keep a short note of your situation and paste it at the top of a new chat.
  - Check first whether the chat actually contains what you told it.
faq:
  - question: What exactly was tested?
    answer: >-
      A fictional family's facts (vegetarian partner; two burners, no oven; 25
      minutes on weeknights; a six-year-old who eats nothing spicy; Friday
      takeout) in the first message, and the same last message: "What should I
      make for dinner tonight? It's Tuesday." Four versions, three runs each on
      Claude Sonnet as a plain assistant with no tools: twelve unrelated
      requests in between; a pasted 4,000-entry log in between; a new chat with
      only the question; a new chat with the facts pasted above the question.
      Everything was fixed before any run.
  - question: What are tokens and the context window?
    answer: >-
      A token is roughly a short word or part of one. The context window is how
      much the model can work with at once, counting both the input and the
      reply it writes. In this tool the model was reported as claude-sonnet-5
      with a window of 1,000,000 tokens. The long chat reached about 2,600 input
      tokens by the question; the long-paste chat about 180,000.
  - question: What happened in the new chat?
    answer: >-
      With only the question, the three answers listed 23 options between them;
      7 clearly broke a fact, such as sheet-pan chicken, salmon with roasted
      asparagus and pasta with red pepper flakes. Each answer ended by asking
      about dietary preferences. Those facts were never in that chat.
  - question: What did the note do?
    answer: >-
      A 61-word note of the same facts, pasted above the question in a new chat,
      gave all three answers all four facts, with under 800 input tokens
      reported before each reply.
  - question: What about the pasted log question?
    answer: >-
      None of the three answered it. Each returned only a sentence saying it
      would count the entries programmatically; tools were turned off. That is
      a separate problem from the one tested here.
  - question: Is this a general result?
    answer: >-
      No. One model, one day, three runs per version. The facts were short and
      came first. A fact buried mid-chat, a chat past the context window, other
      apps and app memory features that carry notes between chats were not
      tested. No success rate is claimed.
sources:
  - label: Design, facts, question and scoring rules, fixed before any run
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/design.md
  - label: All 57 recorded turns with token usage (session ids removed)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/all-turns.json
  - label: The synthetic 4,000-entry maintenance log (seed 42)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/maintenance-log.txt
  - label: The 61-word note and question used in the new-chat-with-note version
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/brief-plus-final.txt
  - label: Per-answer scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/scores.json
---

## The question

You tell AI something early in a chat, and later it seems to have lost it. Is that forgetting, and what should you do about it?

## The test

The same fictional family as [lesson 06](https://wenchangyue.github.io/zero-to-ai-expert/lessons/make-ai-ask-you-first/). Four facts decide whether a dinner works: a vegetarian partner, two burners and no oven, 25 minutes on weeknights, a six-year-old who eats nothing spicy. The [first message](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/setup.txt) states them (75 words). The last message is always "What should I make for dinner tonight? It's Tuesday."

| Version | Between the facts and the question | Input at the question (tool report) | Result, 3 runs |
| --- | --- | --- | --- |
| 1 · long chat | twelve unrelated requests ([list](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/filler-requests.txt)) | 2,623–2,698 tokens | all four facts used in every answer |
| 2 · long paste | a pasted [4,000-entry log](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-07/maintenance-log.txt) | 176,810–182,221 tokens | all four facts used in every answer |
| 3 · new chat | nothing; the facts were never given | 642–646 tokens | 7 of 23 listed options clearly broke a fact |
| 4 · new chat + note | the facts pasted above the question (61 words) | 774–777 tokens | all four facts used in every answer |

Model reported by the tool: claude-sonnet-5, context window 1,000,000 tokens.

## What goes in each time

In this tool, each reply is produced with the conversation so far as its input, and the input can be watched growing: the long chat started at 773–780 input tokens and reached about 2,600 by the question. The first message was still part of it. The context window is the limit on how much the model can work with at once, counting the input and the reply it writes.

## A note for a new chat

The note used in version 4, verbatim:

> Some facts about my household: I'm cooking for three: me, my partner and our 6-year-old. My partner is vegetarian, so no meat or fish; eggs and dairy are fine. Our kitchen has two burners and a microwave, and no oven. On weeknights, dinner has to be on the table within 25 minutes. Our 6-year-old won't eat anything spicy. Friday is takeout.

Keep one like it for your own situation: who the answer is for, what you have to work with, and any limits on time or money. Paste it first when you start a new chat.

## When it seems to forget

1. Check whether the chat you are in actually contains the information. A new chat does not, unless your app carries notes between chats. Paste your note.
2. If the chat is very long, remember there is a limit. Your app's may differ from the one here, and what happens past it depends on the app. Not tested here.
3. These runs do not explain cases where the facts are in the chat and the answer still overlooks them.

## Boundary

One model, one day, three runs of each version. The facts were short and came first. Not tested: a fact buried mid-chat, a chat past the context window, other apps, memory features. In the long-paste version the model never answered the question about the log itself; each run returned one sentence saying it would count the entries programmatically, with tools turned off.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
