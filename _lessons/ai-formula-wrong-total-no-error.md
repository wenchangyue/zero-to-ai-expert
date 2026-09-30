---
published: true
layout: lesson
title: "Fix a Spreadsheet Formula With AI: My Total Was $1,120 Short and Showed No Error"
description: >-
  Why an AI-written SUMIFS formula can return a wrong total with no error, why
  pasting your sheet does not show the AI every problem, and a five-step routine
  with check formulas that caught a trailing space and a number stored as text.
date: '2026-09-30'
modified: '2026-09-30'
course: AI Tools and Workflows
level: Beginner
duration_label: 14 minutes
duration: PT13M53S
youtube_url: "https://youtu.be/yokPCVrn_KI"
video_id: "yokPCVrn_KI"
video_status: public
upload_date: "2026-09-30"
keywords:
  - AI spreadsheet formula wrong
  - SUMIFS wrong total no error
  - Excel numbers stored as text
  - SUMIFS trailing space
  - check AI formula
  - ChatGPT Claude Excel formula
  - Zero to AI Expert
quick_answer: >-
  A formula can return a number with no error and still be wrong, because
  SUMIFS simply skips rows that do not match. On a 20-row practice sheet with a
  trailing space in one region cell and one amount stored as text, the SUMIFS
  formula Claude wrote returned 3,060 instead of 4,180. Pasting the whole sheet
  helped the model spot the space, but two of three answers wrongly said SUMIFS
  would ignore it, and none could see the text-stored number. Ask for a check
  formula next to the first one, make the AI explain every dollar of any gap,
  check its explanation in the cell (LEN, ISTEXT), test against a total you know,
  and then fix the data.
learning_outcomes:
  - Explain why SUMIFS can return a wrong total without any error.
  - Recognize why an AI cannot see cell types or your layout from a question or a paste.
  - Ask for a check formula and use disagreement between two calculations to find a problem.
  - Check an AI's explanation of a problem in the cell itself before accepting a fix.
faq:
  - question: Why did the formula give a wrong total without an error?
    answer: >-
      SUMIFS adds the amount from each row that meets every condition and skips
      the rest; skipping is not an error. In this sheet the region "East " (with a
      trailing space) did not match "East", and the amount 480 was stored as text,
      so both rows were left out in LibreOffice Calc: 3,060 instead of 4,180.
  - question: What did the AI get wrong?
    answer: >-
      With no data, all three answers assumed dates were in column C (the result
      on my sheet was 0) and gave a formula before checking the layout. With the
      whole sheet pasted, all three noticed the trailing space, but two said SUMIFS
      would ignore it. None saw the text-stored 480, which looks identical to a
      number in a paste. One answer also added its own list wrong (4,050).
  - question: What caught the problems?
    answer: >-
      A second formula that trims spaces and multiplies the cells returned 4,180
      next to the SUMIFS 3,060. The 1,120 gap was 640 (the space row) plus 480.
      Asked to explain every dollar, all three conversations found the 480 row;
      one named the right cause (text), one wrongly claimed a hidden space, one
      guessed a non-breaking space and gave tests. LEN(B7) = 4 and ISTEXT(D7) =
      TRUE settled it.
  - question: Does this apply to Excel?
    answer: >-
      Every formula was run in LibreOffice Calc; Excel itself was not run.
      Microsoft documents that SUM ignores text values and that TRIM does not
      remove the non-breaking space character. The SUMIFS help page does not
      describe these cases, so run the same checks on your own sheet.
  - question: Is this a general result?
    answer: >-
      No. One model (Claude Sonnet), one small sheet with two planted problems,
      three fresh conversations per setup. It shows how these failures happen,
      not how often.
sources:
  - label: "Herndon, Ash & Pollin (2013), Does High Public Debt Consistently Stifle Economic Growth? PERI Working Paper 322"
    url: https://peri.umass.edu/wp-content/uploads/joomla/images/WP322.pdf
  - label: "Microsoft Support: SUM function"
    url: https://support.microsoft.com/en-us/office/sum-function-043e1c7d-7726-4e80-8f32-07b23e057f89
  - label: "Microsoft Support: TRIM function"
    url: https://support.microsoft.com/en-us/office/trim-function-410388fa-c5df-49c6-b16c-9e5630b479f9
  - label: "Microsoft Support: Convert numbers stored as text to numbers"
    url: https://support.microsoft.com/en-us/excel/convert-numbers-stored-as-text-to-numbers-in-excel
  - label: The practice workbook (two planted problems)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-09/orders.xlsx
  - label: Test design
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-09/design.md
  - label: All recorded prompts and answers
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-09/all-runs.json
  - label: Every formula the model wrote, with its result in LibreOffice Calc
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-09/eval-all-libreoffice.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-09/scores.json
---

## The problem

You ask AI for a spreadsheet formula, paste it in and get a number. No error appears. On the practice sheet for this lesson, that number was $1,120 short.

## Why no error is not the same as right

SUMIFS walks down the rows and adds the amount from every row that matches all conditions. A row that fails a condition is skipped, and skipping is not an error. Think of a self-checkout that skips an item with a smudged barcode: the receipt looks normal, only the total is lower. (A real scanner sometimes beeps; SUMIFS gives no warning.)

The same kind of silent miss happens outside beginner sheets. Herndon, Ash and Pollin (2013), reproducing Reinhart and Rogoff's 2010 result from the authors' working spreadsheet, found an average that covered rows 30–44 instead of 30–49, leaving 5 of 20 countries out. It was one of several problems they reported; with them corrected, average real growth for countries with public debt above 90% of GDP was 2.2%, not the published −0.1%.

## What the AI did (3 fresh conversations per setup)

| Setup | Result on the sheet (LibreOffice Calc) | What the answers said |
| --- | --- | --- |
| Question only, no data | 0 | 3/3 assumed dates in column C; formula given before checking the layout (1 invited my real columns afterwards) |
| Sheet name, column letters, first 3 rows | 3,060 | same sensible SUMIFS in 3/3; no warnings |
| Whole sheet pasted as plain text | 3,060 | 3/3 noticed "East " with a space; 2/3 said SUMIFS ignores it (it did not); 0/3 saw the text 480 |
| Whole sheet + "what could make it silently wrong, and give me check formulas" | SUMIFS 3,060 · check 4,180 | 3/3 said the space row would be dropped; each gave a trimming check |

The right total, summed from the seven planted East/March orders: 320 + 480 + 275 + 640 + 1,150 + 905 + 410 = 4,180.

Why the AI could not see the second problem: in a paste, the text "480" and the number 480 are the same three characters. Inside Excel a green triangle or left alignment may hint at it; a paste carries neither. Like a photo of a banknote: you can read the number, not whether it is real paper.

## The routine

1. Show the AI the real shape of your sheet: column letters and rows.
2. Ask for the formula, what could make it give a wrong total without any error, and a check formula.
3. Put the check next to the formula and compare the two numbers.
4. If they disagree, give the AI both numbers and ask it to explain every dollar of the difference — then check its explanation in the cell.
5. Test the final formula against a total you worked out yourself.

Then fix the data (retype text numbers, remove stray spaces), not only the formula.

## Explaining the gap

| Answer | Cause named | Checked in the cell |
| --- | --- | --- |
| 1 | amount stored as text (clue: its count check found 6 orders, not 7) | ISTEXT(D7) = TRUE ✓ |
| 2 | a hidden space in the region cell, stated with no hedge | LEN(B7) = 4, no space ✗ |
| 3 | a non-breaking space, called likely, with two test formulas | both tests returned 0 ✗ |

All three final formulas returned 4,180. After D7 was retyped as a number and the space in B10 deleted, the plain SUMIFS also returned 4,180.

Two calculations that disagree tell you something is wrong before you know which; two that share a flaw can agree and both be wrong. Here the trimming check caught the text 480 only because multiplying turns text into a number — nobody designed it for that.

## Boundary

One model (Claude Sonnet), one 20-row practice sheet with two planted problems, three fresh conversations per setup. Every formula the model wrote (16 distinct) was run in LibreOffice Calc 26.2; Excel itself was not run. A hand-checked total works on a small sheet; on a large one, check a filtered slice and compare counts as well as totals.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
