---
published: true
layout: lesson
title: "I Asked AI to Clean Up My Notes. It Added a Deadline Nobody Set."
description: >-
  A page of fictional planning notes with seven details that are easy to
  misread, turned into a report by the same model nine times under three
  prompts. Every report was checked against the notes in both directions.
date: '2026-09-26'
modified: '2026-09-26'
course: AI Tools and Workflows
level: Beginner
duration_label: 9 minutes
duration: PT8M46S
youtube_url: "https://youtu.be/5sHOMk28h7I"
video_id: "5sHOMk28h7I"
video_status: public
upload_date: "2026-09-26"
keywords:
  - turn messy notes into a report with AI
  - AI meeting notes to report
  - AI added information that is not in my notes
  - prompt for turning notes into a report
  - check an AI report against the source notes
  - check AI output
  - Zero to AI Expert
quick_answer: >-
  A tidy AI report can contain things your notes never said and leave out
  things they did, with nothing on the page to tell you which. In this test,
  three plain "turn these notes into a clean report" runs handled the changed
  date, the dropped plan and the unclear name, but all three added a
  "prepared" date with a year the notes do not contain, two added their own
  next-steps lists, and one gave the goal an owner and put a deadline a week
  earlier than the notes. A prompt with sections and "use only what the notes
  say" stopped most additions but dropped the $300 budget in all three runs and
  called a settled price change a disagreement. Adding "the notes are in time
  order: a later note replaces an earlier one unless it says otherwise" gave
  the current price in all three runs. Before you send the report, go from the
  notes to the report line by line, then check every name, number and date in
  the report against the notes, and read the lines that need judgment side by
  side.
learning_outcomes:
  - Tell the model which sections you want and to use only what the notes say.
  - Ask for "not in notes" when an owner or date is missing, instead of a guess.
  - Check the report against the notes in both directions before sending it.
  - Know why finding a word in the notes does not prove the report put it in the right place.
faq:
  - question: What exactly was tested?
    answer: >-
      Fictional planning notes for a food drive, written for this lesson: 217
      words from two meetings, a phone call and two text messages. Before any
      prompt was run, a checklist of 19 items was written. Seven details were
      chosen because they are easy to misread: a date that moved, a price that
      changed by text, an undecided goal, a task with no owner, an initial that
      could be Jen or Jordan, a dropped bake sale, and a sign-up sheet due "next
      week". Three prompts, each run three times on Claude Sonnet as a plain
      assistant with no tools.
  - question: What did the plain prompt add?
    answer: >-
      All three reports put "Prepared" and the test day, with a year, at the
      top; the notes have no year. Two added a "Next Steps" section of their
      own. One asked whether to "approve the extra $10?", which nobody raised.
      One listed Dana as owner of settling the goal, where the notes only say
      Dana questioned it, and placed the sign-up sheet in the "week of Sep 15",
      the week of the meeting where the notes say "next week".
  - question: Did the rules prompt fix it?
    answer: >-
      Partly. None of its three reports added a prepared date or a next-steps
      list, and all three wrote "not in notes" for missing owners and dates.
      One still added "Who is the treasurer?". The $300 budget was missing from
      all three and the truck capacity from two. All three listed the $85 versus
      $95 print quote as unresolved, although the last text says "$95 not $85";
      two of them also said elsewhere in the same report that the price went up
      to $95.
  - question: What did the extra time-order line change?
    answer: >-
      All three reports gave $95 as the current price and still left the food
      goal undecided. All three mentioned every checklist item, including the
      budget. The line was aimed at the price, and three runs cannot show why
      the budget came back. Two of these three reports still left out last
      year's total of about 1,400 pounds, which was not on the checklist.
  - question: How were the reports checked?
    answer: >-
      In two directions. Notes to report: every checklist item was searched for
      in each report and confirmed by reading. Report to notes: a script
      pulled every calendar date, year and number from each report and looked
      for it in the notes; it flagged September 26 and 2026 in each plain
      report and nothing in the six reports with rules. It did not check names,
      and it could not catch "week of Sep 15", because Sep 15 is in the notes.
  - question: Is this a general result?
    answer: >-
      No. One page of fictional notes, one model, one day, three runs per
      prompt. Longer notes, notes spread across several files and files uploaded
      through a chat app were not tested. No success rate is claimed. The
      checks compare the report with the notes; they cannot tell you whether
      the notes themselves are right.
sources:
  - label: The test notes (fictional, written for this lesson)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-05/test-notes.txt
  - label: The three prompts, verbatim
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-05/prompts.json
  - label: All nine recorded reports, verbatim
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-05/reports.json
  - label: The 19-item checklist and per-report coverage
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-05/checklist-coverage.json
  - label: Number and date check results
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-05/number-date-check.json
---

## The problem

You paste messy notes into an AI and ask for a clean report. It comes back tidy, with headings and a table. Before you send it to your team, you cannot tell from the report alone what it added and what it left out.

## The test notes

Fictional planning notes for a small team's food drive, 217 words, [published here](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-05/test-notes.txt) so you can run the same test. A checklist of 19 items was written before any prompt was run. Seven details were chosen because they are easy to misread:

| Detail | What the notes say |
| --- | --- |
| Date moved | "sat oct 10??" then "gym booked oct 10 (wedding). oct 17 open, took it" |
| Price changed | "print shop quote $85", then a text: "print shop now says $95 not $85" |
| Goal undecided | "goal 2000 lbs", then "dana: 2000 too high? maybe 1500. didn't decide" |
| No owner | "someone has to call the food bank re truck pickup" |
| Unclear name | "J to ask about folding tables (jen or jordan?? forgot)" |
| Dropped plan | "bake sale - dropped, not enough people" |
| Relative date | "dana sets up sign-up sheet next week", written at the Sep 15 meeting |

## Prompt 1: "Turn these notes into a clean report I can send to the team."

All three reports mentioned every checklist item, used Oct 17, showed the bake sale as dropped, left the goal undecided, left the food-bank call without an owner, and said J could be Jen or Jordan. They also added:

| Added (not in the notes) | Reports |
| --- | --- |
| "Prepared: Sep 26, 2026", the day of the test; the notes contain no year | 1, 2, 3 |
| A "Next Steps" section of its own | 1, 3 |
| "approve the extra $10?", a question nobody raised | 3 |
| Dana as the owner of settling the goal | 1 |
| Sign-up sheet "Planned for week of Sep 15", a week earlier than "next week" at the Sep 15 meeting | 1 |

Reports 2 and 3 mentioned the sign-up sheet but left out when it was due.

## Prompt 2: rules in the prompt

> Turn these notes into a report I can send to the team. Use these sections: Decisions, Action items (a table with task, owner, due date), Open questions, and What changed since the first meeting. Use only what the notes say. If a task has no owner or no date in the notes, write "not in notes". If the notes disagree, or a name is unclear, say so instead of picking one. Do not add advice or steps of your own.

None of the three added a prepared date or a next-steps list. All three wrote "not in notes" for missing owners and dates and kept the sign-up sheet due "next week". One still added "Who is the treasurer? Not named in notes."

Two other problems appeared. The $300 budget was missing from all three reports and the truck capacity from two; the one that kept the capacity put it under What Changed. These runs do not show why the others left it out. And all three listed the print quote as unresolved ("Print shop quote: is it $85 or $95?"), although the last text settles it. Two of them also wrote elsewhere in the same report that the quote went up to $95.

## Prompt 3: one more line

Prompt 2 plus: *The notes are in time order: a later note replaces an earlier one unless it says otherwise. Call something a disagreement only if the notes leave it unresolved.*

All three reports gave $95 as the current price, still left the goal undecided, and mentioned every checklist item including the budget. The line was aimed at the price, not the budget; three runs cannot say why the budget came back. Two of the three left out last year's total of about 1,400 pounds, which was not on the checklist (all three prompt-2 reports left it out too).

## Two checks before you send it

**Notes to report.** Go down the notes one line at a time and find each line in the report. This is the check that shows what went missing; none of the reports said anything was left out. Use the notes themselves, even if you also keep a checklist.

**Report to notes.** Take every name, number and date in the report and find it in the notes. A script did this for numbers and dates in all nine reports: it flagged September 26 and 2026 in each plain report and nothing in the six reports with rules. It did not check names.

A search shows that a word is in the notes, not that the report put it in the right place. "Week of Sep 15" passed because Sep 15 is in the notes. A name search would show Dana is in the notes, not that Dana owns the goal. For anything that changed, is undecided, or has no owner, put the report line next to the note and read both.

## The prompt from the last test

Use these sections: … Use only what the notes say. If a task has no owner or no date in the notes, write "not in notes". If the notes disagree, or a name is unclear, say so instead of picking one. Do not add advice or steps of your own. The notes are in time order: a later note replaces an earlier one unless it says otherwise. Call something a disagreement only if the notes leave it unresolved.

Use the time-order line only if your notes really work that way. A later suggestion does not always replace an earlier decision.

## Boundary

One page of fictional notes, one model, one day, three runs per prompt. The notes were written for the test, so every item was known; your notes will hold things only you know, such as who J is. Longer notes, notes across several files and chat-app uploads were not tested. The two checks compare the report with the notes; they cannot tell you whether the notes are right.

How the runs were made: Claude Sonnet through the Claude Code CLI (2.1.280) with no settings or instruction files, all built-in tools disabled and no MCP servers, a plain system prompt, a fresh temporary folder and stdin closed. An earlier attempt the same day left some tools available (two reports tried to publish themselves as a web page); those runs were discarded and all nine shown here were made after the fix. The model can see the current date, which is where the "prepared" date came from. The `mode` field inside the published reports file was written by the older harness text and does not list the two added flags; the runs were made with them.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
