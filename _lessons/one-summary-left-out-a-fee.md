---
published: true
layout: lesson
title: "One of Three AI Summaries Left Out a Fee. How Would You Know?"
description: >-
  A fictional 20-page lease with twelve money and deadline clauses on known
  pages, summarized three times by the same model, then asked for pages and
  exact quotes. Every quote was checked against the lease.
date: '2026-09-25'
modified: '2026-09-25'
course: AI Tools and Workflows
level: Beginner
duration_label: 8 minutes
duration: PT8M24S
youtube_url: "https://youtu.be/SdX8YU0DYRs"
video_id: "SdX8YU0DYRs"
video_status: public
upload_date: "2026-09-25"
keywords:
  - summarize a long document with AI
  - can I trust an AI summary
  - AI summary missing information
  - ask AI for page numbers and quotes
  - check AI quotes against the source
  - AI read a contract or lease
  - check AI output
  - Zero to AI Expert
quick_answer: >-
  A summary shows what the model chose to include; it cannot show what it left
  out. In this test, three summaries of the same 4,102-word lease all caught the
  automatic renewal, the carpet charge and the two deposit deadlines, but one of
  the three never mentioned the $95 pest charge, and another stated the default
  rule wrongly with no quote to check. Asking instead "which clauses cost me
  money or set a deadline, with the page and the exact sentence" produced
  answers that mentioned all twelve listed clauses, and every quoted passage
  could be checked: of 129, 110 were whole sentences or clauses word for word,
  none was missing from the lease, and no page number was wrong. Check the
  quotes that matter to your decision, and read the section around the clause
  you act on.
learning_outcomes:
  - Replace "summarize this" with the question you actually need answered.
  - Ask for a page number and an exact quote for every point, so each one can be checked.
  - Check a quote by searching the document for a few distinctive words and reading around the match.
  - Know what a quote check cannot tell you, which is what the answer left out.
faq:
  - question: What exactly was tested?
    answer: >-
      A fictional residential lease written for this lesson: 4,102 words with 20
      page markers and twelve clauses about money or deadlines placed on known
      pages, two deposit-return clauses that differ in time limit and trigger,
      and no rules at all about guest parking. Three prompts, each run three
      times on Claude Sonnet as a plain assistant with no tools: "Summarize this
      lease", a request for every clause that costs money or sets a deadline with
      the page and exact sentence, and two direct questions with an instruction
      to answer "Not in this lease" when the lease is silent.
  - question: Did the plain summaries miss things?
    answer: >-
      Less than expected at this length. All three caught the automatic renewal,
      the $150 carpet charge and both deposit deadlines. One of the three did not
      mention the $95 pest charge at all, and gave no sign that anything was left
      out. One stated that default happens only after notice and a cure period;
      the lease makes unpaid rent a default on its own.
  - question: How were the quotes checked?
    answer: >-
      By a script that searched the lease for every quoted passage of at least
      25 characters in the three cited answers: 129 passages. 110 were whole
      sentences or clauses word for word; 9 were pieces of a sentence with the
      cut not marked; 7 marked a cut with an ellipsis; 2 dropped the opening
      words and capitalized the rest; 1 placed the model's own calculation,
      [$3,300], inside the quotation marks. None was missing from the lease
      apart from that bracket, and no page number was wrong.
  - question: Did asking for quotes make the answers complete?
    answer: >-
      No. All three cited answers mentioned the twelve clauses on the list, but
      the third left out that the early termination fee must be paid together
      with the notice. The cited prompt also changed several instructions at
      once, so this test cannot say which change produced the extra coverage.
  - question: Is this a general result?
    answer: >-
      No. One fictional document of clean text, one model, one day, three runs
      per prompt. Scanned PDFs, files over 100 pages, and files uploaded through
      a chat app's attachment feature were not tested and may be handled
      differently. No success rate is claimed.
sources:
  - label: The test lease (fictional, written for this lesson)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-04/test-lease.txt
  - label: The three prompts, verbatim
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-04/prompts.json
  - label: All nine recorded answers, verbatim
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-04/answers.json
  - label: Quote-by-quote check results
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-04/quote-check.json
---

## The problem

You ask an AI to summarize a long document. The summary reads as complete. What it cannot show you is whether it skipped the page that costs you money.

## The test document

A fictional 20-page lease, 4,102 words, written for this lesson so every answer could be marked against a known list. It is [published here](https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-04/test-lease.txt) so you can run the same test.

| Clause | Page |
| --- | --- |
| Late fee: $75 if rent is not received by the 5th, plus $10 a day, up to $175 | 3 |
| Deposit back within 30 days after you move out and return all keys | 4 |
| Early termination: 60 days' written notice and a fee of two months' rent | 7 |
| $95 per pest treatment after the first 30 days, unless two or more neighboring units have the same pest | 13 |
| Default: unpaid rent is a default when due; notice and time to cure apply to other terms | 13 |
| $150 carpet cleaning deducted from the deposit regardless of the carpet's condition | 16 |
| The only mention of parking: "parking or access cards" returned at move-out | 16 |
| Automatic renewal for another year unless notice 75 days before the end | 18 |
| Deposit back within 45 days after the lease ends | 19 |

## Prompt 1: "Summarize this lease."

Three runs, 436 to 530 words each.

| | Run 1 | Run 2 | Run 3 |
| --- | --- | --- | --- |
| Automatic renewal | yes | yes | yes |
| $150 carpet charge | yes | yes | yes |
| Both deposit deadlines | yes | yes | yes |
| $95 pest charge | yes | **not mentioned** | yes |

Run 2 left the pest charge out without saying anything was left out. Run 1 contained the line "Default triggers after notice + cure period", with no quote and no page. Section 18.1 on page 13 says otherwise for unpaid rent, and the only way to find that was to read the section.

## Prompt 2: ask the question, get the page and the sentence

> I'm about to sign this lease. List every clause that can cost me money or sets a deadline I have to meet. For each one, give the page number and quote the exact sentence from the lease. If two parts of the lease disagree with each other, say so. Do not include anything the lease does not say.

Answers averaged about 1,600 words. All three mentioned the twelve listed clauses, including the pest charge, and all three flagged the two deposit deadlines. The third still left out that the early termination fee is due with the notice.

## Checking the quotes

To check a quote, take a few distinctive words from it, search the document, and read the text around the match on the page it names. A script did this for every quoted passage of 25 or more characters in the three answers:

| Result | Passages |
| --- | --- |
| Whole sentence or clause, word for word | 110 |
| Piece of a sentence, cut not marked | 9 |
| Cut marked with an ellipsis | 7 |
| Opening words dropped, first word capitalized | 2 |
| Model's own words in [brackets] inside the quote | 1 |
| **Total** | **129** |

No passage was missing from the lease apart from the bracketed addition, and no page number was wrong. The bracket read "two (2) months' Monthly Rent [$3,300]": the arithmetic is right, but it is the model's number inside a quote. In the carpet quote, the dropped opening was the reason for the charge; the charge and its conditions were unchanged.

## Prompt 3: a question with no answer

Asked about guest parking, with the instruction to write "Not in this lease" when the lease is silent, all three answers said "Not in this lease" and pointed to the single mention of parking cards on page 16. Asked about moving out after eight months, all three gave 60 days' written notice and a fee of two months' rent, $3,300, quoting page 7, and noted that rent is due until move-out and other charges can still apply. The question was not run without the "Not in this lease" line, so what that line changes is unknown.

## The three lines to add

1. Ask the question you actually have. For this lease: which clauses cost me money or set a deadline.
2. For each point, give me the page and quote the exact sentence.
3. If the document does not say, write "Not in this document." If two parts disagree, say so.

Then check the quotes that matter to your decision, and read the whole section around the clause you will act on, because a quote can start halfway through a sentence.

## Boundary

One fictional document of clean text, one model, one day, three runs per prompt. Scanned PDFs, 100-page files and chat-app uploads were not tested. A checked quote confirms the words are there; it does not tell you what the answer left out. Omissions could be counted here only because the clauses were planted. With your own document you need your own checklist, or someone who reads the source.

Nothing here is legal advice. The lease is a test document.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
