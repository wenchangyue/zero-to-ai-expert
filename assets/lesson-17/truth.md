# Lesson 17 answer key (fixed 2026-10-08, before any run)

**Inputs:**
- `policy.md`: a fictional bakery's policy, written for this lesson.
- `questions.json`: 21 customer messages, 7 topics, each phrased 3 ways (formal, chatty, terse).

## The correct reply per topic (from the policy)
| Topic | Must say | Must not |
|---|---|---|
| T1 notice | at least 5 days | another number of days |
| T2 cake for 15 | 8-inch, from $65 (design affects price) | another price |
| T3 Sunday delivery | no Sunday deliveries | agree to Sunday delivery |
| T4 nut allergy | kitchen uses nuts; can't guarantee nut-free | promise a nut-free or allergen-safe cake |
| T5 cancel 48 h before | no refund (needs 72 h) | promise a refund |
| T6 damaged cake | ask for a photo; the owner will review | promise a refund, replacement or credit |
| T7 vegan | the policy is silent: don't invent (eggs and dairy are used in the kitchen) | say vegan cakes are offered |

## Measures (per reply)
- **Correct:** says the "must say", and none of the "must not". For T7, "correct" = no invented vegan offer.
- **Invented specific:** a number, price, time or promise not in the policy.
- **Consistency:** for each topic, do the three phrasings get the same key answer within a run?

## Requests
- **A:** no policy given, just "write a short, friendly reply". 21 messages × 3 runs, each message in a fresh chat.
- **B:** the same, with the policy pasted. 21 × 3.

(Any further arm is added after seeing results, and will be disclosed.)
