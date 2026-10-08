---
published: true
layout: lesson
title: "Customer Replies with AI: Give It the Facts, Then Check What It Promises"
description: >-
  A tested way for a small business to use AI for customer replies: one policy
  page with the facts and the promises staff never make, pasted into every
  reply, probed for gaps with real questions, and a three-question check before
  sending.
date: '2026-10-08'
modified: '2026-10-08'
course: AI Tools and Workflows
level: Beginner
duration_label: 11 minutes
duration: PT10M37S
youtube_url: "https://youtu.be/vv3Wx8MVFAw"
video_id: "vv3Wx8MVFAw"
video_status: public
upload_date: "2026-10-08"
keywords:
  - AI customer replies
  - small business AI
  - customer service policy
  - FAQ with AI
  - consistent answers
  - Zero to AI Expert
quick_answer: >-
  Write your facts on one page (including what you don't do and the promises
  staff never make), paste it into every request for a reply, and before relying
  on it, ask a fresh chat which customer questions it doesn't answer and where it
  is unclear. In one test (Claude Sonnet, a fictional bakery, 21 messages, 3
  runs), replies written without the policy passed 0 of 63 checklist items and 26
  invented something, including refunds and Sunday delivery; with the policy, 63
  of 63 passed, but a close read still found a too-soon pickup suggestion, a
  leftover placeholder and one vague line read two ways.
learning_outcomes:
  - Explain why a "friendly reply" without your facts can invent promises.
  - Write a one-page policy that includes the "no"s and the hand-offs.
  - Use a fresh chat to find gaps and unclear lines in the policy.
  - Check a draft for promises, unsupported facts and leftover placeholders.
faq:
  - question: What did AI write without the policy?
    answer: >-
      Mostly placeholders or alternative drafts (37 of 63), which are honest but
      can be sent unfilled. The other 26 asserted something it wasn't given:
      every damaged-cake reply offered a remedy, most vegan replies said yes, and
      some versions of the Sunday and cancellation questions got a yes or a
      promised refund.
  - question: Did pasting the policy make replies consistent?
    answer: >-
      It made the checklist answers match across message versions (63 of 63
      passed), but not every detail: the policy's "within 24 hours" was read as
      "of the order" for one message and "of pickup" for the others, and some
      replies went beyond "can't guarantee nut-free" to "can't make one". One
      draft suggested a pickup that was also too soon, and one left a placeholder
      pronoun. Read every reply before sending.
  - question: How do I find gaps in my policy?
    answer: >-
      Give a fresh chat the policy and real customer messages and ask what it
      doesn't answer and where two people could read it differently. In 3 of 3
      runs it flagged vegan cakes, "24 hours from when?" and the nut wording. Some
      suggestions change the policy (one proposed refunding all amounts paid, not
      just the deposit); those are the owner's decisions. The revised policy was
      not re-tested.
sources:
  - label: The policy and messages (fictional)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-17/questions.json
  - label: Checklist, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-17/truth.md
  - label: All prompts and replies
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-17/all-runs.json
  - label: Per-reply classification
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-17/classified.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-17/scores.json
---

## The problem

Ask AI for a "friendly reply" to a customer and it may answer questions you never answered: refunds, delivery days, what you can bake.

## The test

A fictional bakery's [policy](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-17/policy.md), 21 customer messages (7 topics × 3 styles; some versions also change a detail), a checklist fixed before any run, Claude Sonnet, each message in a fresh chat, 3 runs.

| Request | Passed the checklist | Notes |
| --- | --- | --- |
| No policy | 0 / 63 | 37 blanks or options; 26 made something up |
| Policy pasted | 63 / 63 | close read: a too-soon pickup, a placeholder, "24 hours of the order" vs "of pickup" |

## Policy, Paste, Probe

1. **Policy** (must). One page: prices, notice, deposits, cancellations, delivery, allergens; the things you don't do; the promises staff never make, and the hand-off for those.
2. **Paste** (must). Give AI the page with every reply, or save it as project instructions.
3. **Probe** (important). A fresh chat plus real messages: what doesn't the page answer, and where is it unclear? Decide each change yourself.

Before sending: any promise about money, time or safety must match a line on the page; every fact must be on the page; nothing left in brackets.

## Boundary

One model, one fictional bakery, a short policy, 3 runs. Facts were checked, not tone; follow-ups and push-back were not tested; the gap check was added after the first results and the revised page was not re-tested.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
