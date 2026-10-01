---
published: true
layout: lesson
title: "Turn a Meeting Transcript Into Action Items With AI (and Catch the Small Errors)"
description: >-
  A tested way to get action items from a meeting transcript with AI: ask for the
  owner, the deadline and the exact words with a time stamp, write "not stated"
  when missing, then check the quote, the date and any guessed names.
date: '2026-10-01'
modified: '2026-10-01'
course: AI Tools and Workflows
level: Beginner
duration_label: 11 minutes
duration: PT10M32S
youtube_url: "https://youtu.be/w2ssHiei67Q"
video_id: "w2ssHiei67Q"
video_status: public
upload_date: "2026-10-01"
keywords:
  - AI meeting notes
  - action items from transcript
  - meeting summary prompt
  - who agreed to what
  - check AI output
  - speaker labels transcript
  - Zero to AI Expert
quick_answer: >-
  Ask the AI for each action item's owner, deadline and the exact words where it
  was agreed, with a time stamp; write "not stated" when the owner or deadline was
  not said; list suggestions separately. Then search the transcript for the quotes
  that matter and follow each topic to the end of the meeting, check every
  calendar date against the meeting date, and if the transcript has only speaker
  numbers, ask the AI to mark any name it adds as a guess. In a test on one short
  fictional transcript (15 runs of Claude Sonnet), the model avoided all six planted
  traps; the errors were a deadline nobody said, a date before the meeting, and
  names filled in without saying they were guesses.
learning_outcomes:
  - Explain why meeting decisions are hard to summarize (the decision can come late).
  - Use a "no quote, no task" request to get action items you can check.
  - Check relative dates against the meeting date.
  - Handle transcripts that label speakers only by number.
faq:
  - question: Did the AI get the action items wrong?
    answer: >-
      Not the big things. Across 15 runs on one short, clean, fictional transcript,
      it never fell into the six planted traps (a reassigned task, a maybe, a task
      nobody took, an undecided date, a task with no deadline, a wish). The errors
      were small: 2 of 3 plain summaries added a deadline nobody said, 1 of 3 action
      lists turned "Friday" into October 2 for a meeting on October 6, and all 3
      runs on a transcript with speaker numbers filled in names without saying
      they were guesses.
  - question: What is "no quote, no task"?
    answer: >-
      A request that asks for owner, deadline and the exact words with a time stamp
      for every action item, "not stated" when something was not said, and a
      separate list for suggestions. With it, all three runs followed the format,
      and an automatic check found all 31 longer quoted passages in the transcript.
  - question: Is a quote enough?
    answer: >-
      No. A quote shows the transcript contains the words, not that they were the
      final decision. In the test meeting, one person offered to call the caterer
      and later handed it to someone else. Follow each topic to the end of the
      meeting, and check dates yourself.
  - question: What about transcripts without names?
    answer: >-
      Some tools label speakers by number until you tag them (Otter describes
      this). With speaker numbers, the AI put names back from how people
      addressed each other; the guesses were right here but unmarked. Adding
      "mark any name you add as a guess" made all three runs say so.
  - question: Is this a general result?
    answer: >-
      No. One model, one short meeting written for the lesson, three runs per
      setup. Longer, messier meetings and transcripts with misheard words were
      not tested.
sources:
  - label: "Otter.ai Help Center: Speaker Identification Overview"
    url: https://help.otter.ai/hc/en-us/articles/21665587209367-Speaker-Identification-Overview
  - label: The meeting transcript (fictional, written for this lesson)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-10/meeting.txt
  - label: Answer key, fixed before the runs
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-10/truth.md
  - label: All prompts and answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-10/all-runs.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-10/scores.json
---

## The problem

AI meeting notes look finished. The question is whether each "who will do what, by when" was actually agreed.

## Why meetings are hard to summarize

A meeting is people thinking out loud. On one topic the decision can come long after the first thing said, and a late suggestion is not automatically agreed. Like a document with tracked changes, the real version is what is left after the accepted edits, except that a meeting marks no edits.

## The test

A 2½-minute fictional planning call with six planted traps and an answer key fixed before any run. Claude Sonnet, three fresh conversations per setup, 15 in total.

| Setup | Traps fallen into | What went wrong |
| --- | --- | --- |
| "Summarize this meeting." | 0 | 2 of 3 added a deadline nobody said |
| Action items with owner and deadline | 0 | 1 of 3 put "Friday" on Oct 2, before the Oct 6 meeting |
| Owner, deadline, exact words + time stamp, "not stated", suggestions separate | 0 | none found; 31 longer quotes all found in the transcript |
| Same, transcript with speaker numbers | 0 | 3 of 3 filled in names without saying they were guesses |
| Same + "mark any name you add as a guess" | 0 | 3 of 3 marked the guesses (one only in a note at the end) |

## No quote, no task

1. Ask for the owner, the deadline, and the exact words with a time stamp. "Not stated" when missing. Suggestions in a separate list.
2. Search the transcript for the quotes behind the items that matter, and follow each topic to the end of the meeting.
3. Check every calendar date against the meeting date.
4. If speakers have no names, ask the AI to mark any name it adds as a guess.

A quote is a receipt: it shows the words are in the transcript. It does not show they were the last word, and a misheard word in an auto-transcript still "matches".

## Boundary

One model, one short, clean meeting written for the lesson, three runs per setup. Longer and messier meetings were not tested.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
