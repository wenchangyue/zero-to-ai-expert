---
published: true
layout: lesson
title: "Screen 200 Research Papers with AI, and Check What It Missed"
description: >-
  A tested way to use AI for title-and-abstract screening without losing the
  relevant paper: exact criteria and a decision for every record, a rescue rule
  for records with no abstract, and a second look at the excluded pile.
date: '2026-10-07'
modified: '2026-10-07'
course: AI Tools and Workflows
level: Beginner
duration_label: 11 minutes
duration: PT10M52S
youtube_url: "https://youtu.be/wKexd8nnqRI"
video_id: "wKexd8nnqRI"
video_status: public
upload_date: "2026-10-07"
keywords:
  - AI literature screening
  - systematic review AI
  - title and abstract screening
  - recall check
  - SYNERGY dataset
  - Zero to AI Expert
quick_answer: >-
  Let AI take the first pass with your exact criteria (exceptions included) and
  a decision for every record; send every record with no abstract that could be
  relevant to full text; and give a fresh chat the excluded pile for a second
  look. In one test (Claude Sonnet; 200 records from the SYNERGY Oud_2018
  dataset, 20 labeled included), pasting all 200 at once kept 17 or 18 of the 20
  per run; three known papers were kept in all 6 runs while others were missed;
  a no-abstract title filter (14 records) brought back two misses and a second
  look brought back one; one miss was never recovered.
learning_outcomes:
  - Explain why dropped papers are harder to catch than invented claims.
  - Run AI screening with a decision for every record and count them.
  - Explain why a small known-paper check can pass while papers are missed.
  - Use a no-abstract rescue rule and a second look at excluded records.
faq:
  - question: How well did AI screen the 200 records?
    answer: >-
      Asked once with all 200, Claude Sonnet kept 17, 17 and 18 of the 20
      records the reviewers labeled included, in 25 to 33 seconds per run. Asked
      for a decision on every paper (with "unsure" kept), it kept 18, 18 and 17
      but about twice as many records for full reading (50 to 52).
  - question: Does checking with papers I already know work?
    answer: >-
      As a smoke test only. Three included papers picked at random before the
      runs were kept in all 6 runs, while 2 or 3 other included papers were
      missed each time. With 2 or 3 misses out of 20, three random known papers
      are all kept about 72% or 60% of the time.
  - question: What found the missed papers?
    answer: >-
      Two checks added after seeing the results. A rule with no AI (excluded
      records with no abstract whose title names one of the therapies, 14
      records) brought back the two no-abstract misses. A fresh chat's second
      look at the excluded pile flagged 14 to 16 records and rescued one of them
      in all 3 runs. Neither recovered a paper whose abstract described a shorter
      treatment and a mixed population; my criteria summary had left out the
      review's exception for trials with separate data, and I did not test
      whether restoring it changes the decision.
  - question: Can AI replace a second human screener?
    answer: >-
      Not by this test. Cochrane's MECIR standard C39 calls independent double
      screening of titles and abstracts desirable but not mandatory, and requires
      two people working independently for final eligibility decisions.
sources:
  - label: Oud et al. 2018, systematic review (PMC)
    url: https://pmc.ncbi.nlm.nih.gov/articles/PMC6151959/
  - label: SYNERGY dataset (ASReview, CC0)
    url: https://github.com/asreview/synergy-dataset
  - label: The 200-record sample (titles, labels; no abstracts)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-16/sample.json
  - label: Requests and all answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-16/all-answers.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-16/scores.json
---

## The problem

AI can sort hundreds of search results in seconds. A dropped paper leaves no trace, so you need checks aimed at what's missing.

## The test

[Answer key](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-16/truth.md): the reviewers' own labels from the SYNERGY `Oud_2018` dataset. All 20 labeled-included records plus 180 labeled-excluded at random (seed 42); 61 have no abstract. Criteria paraphrased from the review's methods ([requests](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-16/requests.md)).

| Request | Kept of the 20 (runs 1–3) | Records kept |
| --- | --- | --- |
| All 200 at once | 17, 17, 18 | 18, 26, 29 |
| A decision per paper, unsure kept | 18, 18, 17 | 50, 52, 51 |

Known-paper check: passed in 6 of 6 runs, while other included papers were missed.

## Screen, Rescue, Recheck

1. **Screen** (must). Exact criteria copied from your protocol, exceptions included; a decision for every record, and count them.
2. **Rescue** (must, in this suggested workflow). Records with no abstract that could be relevant go to full text. A title filter helps find them; a title without your keywords is not automatically safe to drop.
3. **Recheck** (important). A fresh chat's second look at the excluded pile; keep known-paper checks as a smoke test, not proof.

## Boundary

One review, one model, three runs per request; the sample is enriched (10% vs 1.9%); labels are full-text decisions and not a full list of every report the review used; the rescue rule and the second look were added after seeing results, and the complete workflow was not tested end to end.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript. Abstracts are not republished here.
