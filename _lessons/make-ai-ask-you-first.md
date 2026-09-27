---
published: true
layout: lesson
title: "I Asked AI for a Week of Dinners. Most Nights Wouldn't Have Worked."
description: >-
  One dinner-plan request for a fictional family, asked three ways and run
  three times each: six words, everything told up front, and "ask me first".
  Every dinner was held against five facts written down before any run.
date: '2026-09-27'
modified: '2026-09-27'
course: AI Tools and Workflows
level: Beginner
duration_label: 7 minutes
duration: PT6M48S
youtube_url: "https://youtu.be/1jM297VqOAA"
video_id: "1jM297VqOAA"
video_status: public
upload_date: "2026-09-27"
keywords:
  - make AI ask questions before answering
  - ask me questions first prompt
  - why does AI guess what I want
  - AI meal plan
  - better AI prompts for beginners
  - check AI output
  - Zero to AI Expert
quick_answer: >-
  When a request depends on facts about you that you did not give, the model
  fills them in with common defaults. Asked in six words for a week of
  dinners, three plans for a family with a vegetarian partner, no oven, a
  25-minute weeknight limit, a child who eats nothing spicy and takeout on
  Friday clearly broke at least one of those facts on four, four and five of
  seven nights. Adding "Before you write it, ask me whatever you need to know,
  and wait for my answers" produced 9, 9 and 10 questions that reached all
  five facts, and after I answered them the plans had no clear failure on the
  same checks. Putting every fact in the first message did the same, for
  about the same amount of typing. Ask it to question you when you are not
  sure which details matter; either way, check the answer against the few
  things that would make it fail for you.
learning_outcomes:
  - Recognize when an answer depends on facts about you that the model does not have.
  - Use one line that makes the model ask before it answers.
  - Decide between telling everything up front and letting it ask.
  - Check any plan against the three to five things that would make it fail for you.
faq:
  - question: What exactly was tested?
    answer: >-
      One request, "Make me a weekly dinner plan", for a fictional family of
      three. Before any run, a fact sheet listed what is true for that family
      and five scoring rules: a vegetarian partner, no oven or other baking or
      slow-cooking appliance, 25 minutes on Monday to Thursday, nothing spicy
      for the child, and takeout on Friday. Three versions, three runs each on
      Claude Sonnet as a plain assistant with no tools: the six words alone;
      the six words with every fact written out; and the six words plus a line
      asking it to ask first, with my answers taken only from the fact sheet.
  - question: What went wrong with the six-word request?
    answer: >-
      Counting only what the text clearly showed, four, four and five of the
      seven dinners broke at least one fact. Ten dinners had meat or fish with
      no vegetarian version for that meal, seven clearly needed an oven or a
      slow cooker, and all three planned a homemade pizza night on Friday. One
      answer added a general tip to swap meat for tofu, beans or lentils. Three
      chili dinners gave no spice level and were not counted as spice failures.
      The model had none of these facts, so this measures the cost of the gap,
      not a flaw in the model.
  - question: Did it know what it should have asked?
    answer: >-
      Each of the three six-word answers ended by offering to tailor the plan to
      dietary needs, with "vegetarian" as the first example. The question was
      there, after the menu.
  - question: What happened when it was asked to question first?
    answer: >-
      It asked 9, 9 and 10 numbered questions: who is eating, dietary
      restrictions, time on weeknights, kitchen equipment, which nights differ,
      and others such as leftovers and budget. All three interviews reached all
      five facts; all three asked about kitchen equipment. One asked one more
      question before writing: all-vegetarian dinners, or a vegetarian base
      with meat added for some. On the five checks, none of the eighteen
      dinners had a clear failure.
  - question: Is asking first better than just telling it?
    answer: >-
      Not in this test. Putting every fact in the first message also gave no
      clear failure in eighteen dinners, and the typing was about the same:
      118 words for the full first message, 125 to 138 for the ask line plus my
      answers. I could write that full message because I had the fact sheet in
      front of me. Asking first helps when you are not sure which details
      matter.
  - question: Is this a general result?
    answer: >-
      No. One model, one task, one day, three runs per version. Every deciding
      fact was an ordinary meal-planning one; a situation where what matters is
      unusual was not tested, and the model can only ask about what it thinks
      to ask. The check covers what the text says: weeknight times are the
      model's labels, and nothing was cooked. No success rate is claimed.
sources:
  - label: The fact sheet and scoring rules, written before any run
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-06/fact-sheet.md
  - label: The six-word and told-everything prompts, verbatim
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-06/prompts.json
  - label: All six plans from those prompts, verbatim
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-06/plans-plain-and-told.json
  - label: All three interviews, every question, answer and plan
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-06/interviews.json
  - label: Per-dinner scores for all nine plans
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-06/scores.json
---

## The problem

You ask an AI for something that depends on your situation — a meal plan, a trip, a budget — and it answers straight away. The answer looks complete. It is built on details it never had.

## The family and five facts

Fictional, written for this test. A parent cooking for three: themselves, a partner, and a six-year-old. Before any run, the [fact sheet](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-06/fact-sheet.md) fixed what is true and how each dinner would be scored.

| # | Fact | A dinner fails if… |
| --- | --- | --- |
| 1 | The partner is vegetarian | it has meat or fish and no vegetarian version for that meal |
| 2 | Two burners and a microwave, no oven | it clearly needs an oven, baking, a slow cooker or similar |
| 3 | Monday–Thursday: on the table in 25 minutes | its stated time is over 25 minutes |
| 4 | The six-year-old eats nothing spicy | it is spicy by design and not made mild for the child |
| 5 | Friday is takeout | the plan schedules cooking on Friday |

Only what the text clearly showed was counted. Chili with no stated spice level, and pizza or cornbread with no stated method, were recorded as unclear and not counted.

## Three ways to ask

| Version | What I typed | Dinners with a clear failure |
| --- | --- | --- |
| Six words | "Make me a weekly dinner plan." | 4/7, 4/7, 5/7 |
| Told everything | the six words plus every fact (118 words) | 0/6, 0/6, 0/6 |
| Ask first | the six words plus "Before you write it, ask me whatever you need to know, and wait for my answers." and then my answers (125–138 words in total) | 0/6, 0/6, 0/6 |

Model: Claude Sonnet as a plain assistant, no tools. Three runs per version. The told and ask-first plans cover Saturday to Thursday; Friday is takeout.

## What the six-word plans guessed

- Ten dinners with meat or fish and no vegetarian version for that meal. One answer did add a general tip: swap any meat for tofu, beans or lentils.
- Seven dinners that clearly needed an oven or a slow cooker, such as baked salmon and a slow-cooker pot roast.
- A homemade pizza night on Friday, in all three.
- All three started Monday with chicken and roasted broccoli.

Each of those answers ended by offering to tailor the plan to dietary needs, with "vegetarian" as the first example. The question was in the answer, after the menu.

## What the interview asked

9, 9 and 10 numbered questions. Common to all three: who is eating, dietary restrictions, time on weeknights, kitchen equipment, and which nights need something different. All three reached all five facts. Some questions did not matter here, such as leftovers; where the fact sheet had nothing, the answer was "No strong preference." One run asked one more question first: all-vegetarian dinners, or a vegetarian base with meat added for some.

The resulting plans all gave the family a shared vegetarian base; two added optional meat for the parent's own bowl and one kept everything vegetarian. All used only the stovetop and microwave, none scheduled cooking on Friday, and every weeknight dinner was labeled 25 minutes or less. Nothing was cooked to check those times.

## Tell it, or let it ask?

Both removed the clear failures here, for about the same typing. The difference is where the facts came from: I wrote the full first message with the fact sheet in front of me, so I knew to mention the oven. All three interviews asked about the kitchen without being told.

- If you already have the details, put them in the first message.
- If you are not sure which details matter, add: "Before you write it, ask me whatever you need to know, and wait for my answers."

## Still read the answer

Two lines worth catching, neither scored as a failure:

- An interview plan's optional Wednesday extra: "add sliced kielbasa or diced ham while simmering (separately for your bowl if partner wants meat-free)". The partner had already been described as vegetarian.
- A told-everything plan's shopping list says "veggie/chicken bouillon or broth", and its lentil soup step just says "broth". The vegetarian choice is there; you have to notice it.

## The check

1. Write down the three to five things that would make a plan fail for you.
2. Go through the answer item by item and check each one against that list.

That is how all nine plans here were scored. It only covers what the text says.

## Boundary

One model, one task, one day, three runs per version. Every deciding fact was an ordinary one for meal planning; a case where what matters is unusual was not tested, and the model can only ask about what it thinks to ask. Nine or ten questions is a lot for a quick request.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
