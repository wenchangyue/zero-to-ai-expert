---
published: true
layout: lesson
title: "Fifty Product Descriptions in One Go, With Quality Control"
description: >-
  A tested way to check a batch of AI-written product descriptions without
  reading them all: sweep for words your sheet never uses, sample a few rows
  at random plus every row with a warning, and widen the check when you find one.
date: '2026-10-05'
modified: '2026-10-05'
course: AI Tools and Workflows
level: Beginner
duration_label: 12 minutes
duration: PT11M45S
youtube_url: "https://youtu.be/kQFYG5zZJAE"
video_id: "kQFYG5zZJAE"
video_status: public
upload_date: "2026-10-05"
keywords:
  - AI product descriptions
  - batch content quality control
  - random sample check
  - AI invented claims
  - ecommerce copy
  - Zero to AI Expert
quick_answer: >-
  Search the whole batch for words your product sheet never uses (handmade,
  eco-, renewable, airtight, outdoor, -free, warranty, resistant, limited) and
  check every hit; then read five to ten descriptions at random plus every row
  with a warning; when you find one problem, check every row like it, fix the
  request and check the new batch again. In one test (Claude Sonnet, a 50-row
  fictional sheet, 3 runs per request), a request for persuasive, SEO-friendly
  copy invented claims in 9, 3 and 2 of 50 rows; the word search found 13 of the
  14 counted problem rows, while a random five would have caught the 3-row case
  about 28% of the time.
learning_outcomes:
  - Explain why persuasive copy requests can add claims your product data never made.
  - Run a word sweep for claims your sheet never uses, with whole-word matching off.
  - Explain why a clean random sample does not show the batch is clean.
  - Decide when to widen a check, and why to fix the request rather than one row.
faq:
  - question: Did the AI make mistakes with a plain request?
    answer: >-
      Rarely. "Write a product description for each of these 50 products" gave
      short, factual descriptions; across three answers we counted one problem
      (a "hand-finished-look gold rim"). The invented claims came with the
      request for engaging, persuasive, SEO-friendly copy, which was added after
      seeing the plain results.
  - question: What kinds of mistakes did it make?
    answer: >-
      Additions, not omissions. In all 12 answers it kept every warning and
      changed no size, price or color. The counted problems were claims the
      sheet never made: handmade wording, eco and sustainable wording, an
      airtight seal, outdoor use on a row with no care information, and one
      durability claim. Some answers also said stock was limited; that kind was
      outside the answer key and is listed separately.
  - question: Why isn't a random sample enough?
    answer: >-
      Rare problems are easy to miss. With 3 bad rows out of 50, a random five
      hits at least one about 28% of the time (exact hypergeometric). And if 5 of
      50 rows were bad, a random ten would still come back clean about 31% of
      the time. Sampling is good at showing there is a problem, not at showing
      there is none.
  - question: Did adding rules to the request fix it?
    answer: >-
      It helped in these runs: counted problem rows fell from 9, 3, 2 to 0, 1, 1.
      The two that remained ("relaxed, handcrafted feel", "handmade-style charm")
      were the same kind, and the word search found both. That is a reason to try
      a revised request and check it again, not a promise for another batch.
sources:
  - label: The product sheet (fictional)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-14/products.csv
  - label: Answer key, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-14/truth.md
  - label: All prompts and answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-14/all-runs.json
  - label: Counted errors and adjudication
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-14/adjudication.md
  - label: Scores and sampling math
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-14/sampling.json
---

## The problem

You ask AI for fifty product descriptions at once. They read well, but some may say things your product sheet never said, and you can't read all fifty every time.

## The test

A fictional shop sheet (50 rows: material, size, colors, care, price, notes), an answer key fixed before any run, Claude Sonnet, the whole sheet in one message, three fresh runs per request.

| Request | Rows with a counted invented claim (runs 1, 2, 3; of 50) |
| --- | --- |
| Plain: "Write a product description for each…" | 0, 0, 1 |
| Short template, facts only | 1, 1, 1 |
| Engaging, persuasive, SEO-friendly | 9, 3, 2 |
| Persuasive + three rules | 0, 1, 1 |

No answer dropped a warning or changed a size, price or color.

## Sweep, Sample, Widen

1. **Sweep** (must). Search the whole batch for words your sheet never uses: handmade, handcraft, hand-poured, hand-finished, eco-, sustainab, renewable, organic, airtight, outdoor, -free, warranty, resistant, limited. Turn whole-word matching off, and don't search "hand" alone ("hand wash" is in the sheet). Check every hit against its row. In the three persuasive answers this found 13 of the 14 counted problem rows; it missed "built for little hands and the occasional drop".
2. **Sample** (must). Read five to ten descriptions at random (different random row numbers) against their rows, plus every row with a warning. A clean sample is a spot check, not proof.
3. **Widen** (important). One problem means checking every row like it, fixing the request and checking the new batch again. Anything that could hurt someone or cost a refund gets checked on every row. A new product type, request, tool or a much bigger batch gets a full read first.

## Boundary

One model, one fictional shop, a short and tidy sheet, three runs per request. The persuasive request and the extra rules were added after seeing earlier results. The sweep words fit this sheet; yours will differ, and a word search can't find a missing warning or a claim with no keyword.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
