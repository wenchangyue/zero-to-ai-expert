---
published: true
layout: lesson
title: "I Asked AI for the Same Email 4 Ways. It Wrote a Sentence I Never Said."
description: >-
  Four prompts for one email, with two controls, and every answer checked. The
  version that fit best also told the recipients I had already fixed the problem
  I was writing about.
date: '2026-09-24'
modified: '2026-09-24'
course: AI Tools and Workflows
level: Beginner
duration_label: 8 minutes
duration: PT8M3S
youtube_url: "https://youtu.be/8js2SGAgYSc"
video_id: "8js2SGAgYSc"
video_status: public
upload_date: "2026-09-24"
keywords:
  - how to prompt AI
  - prompt engineering for beginners
  - better AI prompts
  - AI writing emails
  - check AI output
  - AI mistakes
  - AI for work
  - Zero to AI Expert
quick_answer: >-
  Put five things in the request: who is involved, what has to happen, the
  context and especially the cause, the shape and length you want back, and an
  instruction to state its assumptions before answering. In this test the
  one-line prompt produced a generic memo, a hundred words of polite but vague
  context produced a longer generic memo, and the structured prompt produced an
  email that named the actual problem. It also wrote, in the sender's voice,
  that the tracker had already been relabelled — which had not happened, and
  which appeared in both structured runs. The assumptions list surfaced a wrong
  date but said nothing about that sentence, so you still have to read the draft.
learning_outcomes:
  - Write a request that supplies the context a model cannot infer.
  - Recognize that a longer prompt is not the same as a more informative one.
  - Spot a draft that claims, in your voice, that you have already done something.
  - Use an assumptions list as a checklist rather than as a safety net.
faq:
  - question: What exactly was tested?
    answer: >-
      One task — an email asking a team to fill in a shared project tracker —
      written four ways: a fourteen-word request, a hundred words of polite but
      vague context, a ninety-eight-word structured prompt, and the same
      structured prompt with the assumptions instruction removed. Two further
      pairs covered summarizing meeting notes and asking for pricing advice.
  - question: Does a structured prompt make the answer correct?
    answer: >-
      No. The structured answer named the real problem and was the shortest of
      the three, and it still stated a wrong date in its assumptions and made an
      untrue claim about the sender. Structure changed what the answer was about,
      not whether it was accurate.
  - question: What do the controls show, and what do they not show?
    answer: >-
      The long-but-vague control shows that in this test the extra words did not
      address the ownership problem. The minus-assumptions control shows that the
      invented labelling claim appeared in both structured runs, and that only
      the version asked for assumptions stated a calendar date. What the controls
      do not show is which of the five elements in the structured prompt did the
      work — that prompt changed the role, goal, context, format and length limit
      at once.
  - question: Is this a general result?
    answer: >-
      No. One model, one day, one run per prompt except the email, which was run
      four ways. Three tasks chosen because the difference could be checked
      afterwards. No success rate is claimed.
sources:
  - label: Recorded prompts and answers for all four email versions and both extra pairs
    url: https://github.com/wenchangyue/zero-to-ai-expert
---

## The task

A team has a shared project tracker and nobody is filling it in. The real reason is that nobody knows which column is theirs. Write the email.

## Four prompts, one task

| Prompt | Prompt words | Answer words | What came back |
| --- | --- | --- | --- |
| One line | 14 | 256 | Subject line, greeting, bulleted list of why trackers are good. Nothing in it is wrong; it never touches the ownership problem |
| Long but vague | 100 | 362 | Longer, still general. The prompt said the tracker existed and was underused, but not why |
| Structured | 98 | 218 | Opens by naming the cause: "it's not clear which row belongs to whom — that's on me for not making it clearer" |
| Structured, assumptions line removed | 85 | 73 | Still names the cause |

The five things in the structured prompt: who is writing and to whom; what the email has to achieve; the context including the cause; the shape and a length limit; and an instruction to state assumptions first.

## The sentence that was not true

The structured draft contains this line, in the sender's voice:

> I have gone back and labeled each row with your name so there is no guessing involved.

That had not happened. The prompt said nobody knows which column is theirs; it never said the problem had been fixed. Running the prompt again with the assumptions line removed produced the same claim in different words: "I have labeled each column with a name."

Both structured versions told six people that the tracker was already relabelled. Anyone opening it would find nothing labelled. It reads as helpful, which is what makes it easy to skim past.

## What the assumptions line did, and did not do

Asked to state its assumptions, the model opened with a list: six people have access; this is a nudge, not a crisis; and "Friday" means this coming Friday, September 26.

September 26, 2026 is a Saturday. The recording was made on Thursday the 24th, so the coming Friday was the 25th.

That date never reached the email, which only ever says "Friday". It was visible because the list put it in front of a reader who then checked a calendar. The same list said nothing about the labelling sentence.

So the list is worth asking for — it gives you specific things to check. It does not do the checking, and it does not cover everything the draft contains.

## Two more pairs

**Meeting notes.** Asked to summarize a committee paragraph, the answer was 66 words: the three proposals as bullets, plus the two facts that matter for what happens next — no vote was taken, and the chair asked for revised figures by the 15th.

Asked instead for three lines (decided, still open, my next action and its deadline) and to flag anything missing, the answer used that shape and added a fourth line: the text never says which month the 15th is, and never says the reader is the one who owes the figures. Both true. In the same reply, one line above, it had already written "What I have to do: provide revised figures by the 15th" — assigning the task before admitting it could not tell whose task it was.

**Pricing.** "How should I price my freelance editing work?" produced 499 words of pricing models and rate ranges, ending by asking what kind of editing the reader does. The same question plus "ask me the three questions that would change your advice most, and do not give the advice yet" produced 128 words and three questions. It asked first instead of last because it was told to. The rate ranges were not checked and are not endorsed here.

## What to write

1. Who is involved.
2. What has to happen.
3. The context, especially the cause — the background you would give a colleague.
4. The shape you want back, and how long.
5. Ask it what it is assuming.

Then read the draft itself, not only the assumptions.

## Boundary

One model, one day, one run per prompt except the email. Three tasks chosen because the difference could be verified afterwards. No success rate. None of this makes an answer true: the clearest version still stated a wrong date and made an untrue claim about the sender. A date goes against a calendar; a number goes against whoever publishes it.

Nothing here is financial or career advice.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
