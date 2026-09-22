---
published: true
layout: lesson
title: "What AI Can and Cannot Do Today: 6 Tasks Tested Live (1 Was Wrong)"
description: >-
  Six everyday tasks given to an AI model with no tools, every answer checked
  against a source or a calculator. The result is a one-page map: hand it over
  and read it, do it together, or check every line.
date: '2026-09-21'
modified: '2026-09-21'
course: AI Foundations
level: Beginner
duration_label: 10 minutes
duration: PT10M10S
youtube_url: "https://youtu.be/cy9g4Xat5Bg"
video_id: "cy9g4Xat5Bg"
video_status: public
upload_date: "2026-09-21"
keywords:
  - what AI can do
  - what AI cannot do
  - AI for beginners
  - how to use AI
  - check AI answers
  - AI mistakes
  - AI hallucination
  - AI limitations
  - Zero to AI Expert
quick_answer: >-
  Hand over rewriting, explaining and organizing, then read the result once and
  look for gaps the model filled. Do decisions and anything about your own
  situation together: the model lays out the trade-off, you decide. Check every
  fact, number, date, name, source and calculation by opening the source or using
  a calculator, because a wrong answer can sound exactly as confident as a right
  one. In the lesson's six recorded tests the model was wrong once, on a
  multiplication, and correct in five repeats of the same question.
learning_outcomes:
  - Sort a task into one of three columns before asking an AI for help.
  - Recognize a filled gap in an otherwise correct rewrite or table.
  - Check a cited statistic by opening the source and its data table, not only the headline page.
  - Explain why exact arithmetic from a model without a calculator tool must be verified.
faq:
  - question: Which AI model was tested?
    answer: >-
      Claude Sonnet, run as a plain assistant through a command-line interface on
      2026-09-21 with no calculator, web search or other tools, and with no
      project or user instructions. All six answers are quoted verbatim in the
      video and listed below.
  - question: Was the multiplication error a one-off?
    answer: >-
      The recorded answer to 48,271 × 9,384 was 453,047,064; the correct product
      is 452,975,064. The same prompt was then repeated five times under the same
      setup and all five were correct, so one wrong answer in six tries. The
      lesson does not turn this into a general accuracy rate.
  - question: Did the 23% figure turn out to be right?
    answer: >-
      Yes. The Pew article states 34% for 2025 and that use roughly doubled since
      2023. The 23% for 2024 appears in the topline data table linked from the
      article, not in the article text. The lesson uses this to show that a check
      sometimes has to go one level deeper than the headline page.
  - question: Is the narrator a person?
    answer: >-
      No. The narration is a synthetic voice, the script was written with an AI
      language model (Claude), fact-checked against the sources below, reviewed
      by an independent model, and published by Wenchang Yue.
sources:
  - label: Pew Research Center, "34% of U.S. adults have used ChatGPT, about double the share in 2023" (June 25, 2025)
    url: https://www.pewresearch.org/short-reads/2025/06/25/34-of-us-adults-have-used-chatgpt-about-double-the-share-in-2023/
  - label: Pew Research Center topline for the same survey (GPTUSE, 34% in 2025, 23% in 2024, 18% in 2023; n = 5,123 total, fielded Feb 24 – Mar 2, 2025)
    url: https://www.pewresearch.org/wp-content/uploads/sites/20/2025/06/SR_25.06.24_chat-gpt_topline.pdf
---

## The question

Which tasks should you hand to an AI right now, and which ones do you have to check line by line? The lesson answers with six recorded tests rather than a list of opinions.

## How the tests were run

Six prompts were sent to Claude Sonnet on 2026-09-21 as a plain assistant: no calculator, no web search, no project or user instructions, only the words in each prompt. Every answer was saved verbatim and then checked by a person or a calculator. Nothing was edited for the video.

## The six tasks and what the checks found

**Task 1, rewrite.** A blunt tenant message ("the heater has been broken for nine days, I've emailed twice, nothing. Fix it this week or I'm calling the city") was rewritten as a polite, firm 68-word note with placeholders for names. The check found two interpretations that were not in the original: "nothing" became "without receiving a response," and "calling the city" became "file a complaint with the city." Both are reasonable; both should be confirmed before sending.

**Task 2, explain.** A mortgage interest rate was explained in three sentences ("like a rental fee for using the bank's money") followed by a check question about higher versus lower rates. The check question tests one part of the explanation for the same loan; being able to say why is the better test.

**Task 3, organize.** Four lines of messy meeting notes became a four-row table with "unknown" where the notes said nothing and "tentative" where the notes said "maybe." One cell went beyond the notes: "Friday" became "Friday (2026-09-25)." The notes never said which Friday, so that date is a fill, not a fact.

**Task 4, facts.** Asked for the share of U.S. adults who had used a generative AI tool by 2025 with a source, the model cited a Pew Research Center survey from June 2025: 34% of U.S. adults had used ChatGPT, up from 23% the year before, and it warned that this measures ChatGPT rather than all generative AI. The check: 34%, the June 25, 2025 publication date, and the 5,123-adult sample fielded February 24 to March 2, 2025 all match the article. The 23% did not appear in the article text; it appears in the topline data table linked from the article (23% in February 2024, 18% in July 2023). The answer also mentioned a broader range "from about one-third to over half" across other surveys; that range was not verified.

**Task 5, exact numbers.** "strawberry" contains three r's: correct. 48,271 × 9,384 was answered as 453,047,064; a calculator gives 452,975,064, so the model was off by 72,000. The prompt was repeated five more times under the same setup and all five answers were correct. Six tries, five right, one wrong, all delivered in the same tone.

**Task 6, a decision.** For a job offer of $85,000 with 20 vacation days against a current $78,000 with 25 days, the model computed +$7,000 and −5 days, about $1,400 per lost vacation day, listed what it did not know (career growth, whether days can be negotiated, how much $7,000 matters now), and gave a conditional answer: take it if money matters more, stay or negotiate if balance matters more. The $1,400 is the raise divided by the days, not the value of a day off. The model cannot see health, family, commute or fatigue.

## The map

| Hand it over, then read it | Do it together | Check every line |
| --- | --- | --- |
| Rewriting, explaining, organizing | Decisions, plans, anything about your specific situation | Facts, numbers, dates, names, sources, arithmetic |
| Read once; look for filled gaps | The model structures, you choose | Open the source; use the calculator |

Any answer in any column can contain a fact or a number, and those get checked wherever they sit. Confidence is not evidence; the check is.

## Boundary

These are results from one model, in one setup, on one day. Results may differ across apps, model versions and even repeated runs, as the multiplication showed. Apps that give the model tools such as a calculator or web search can move tasks between columns. The three columns are a working habit, not a fixed ranking of what AI can do.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
