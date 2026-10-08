# Lesson 17 demo design (2026-10-08)

**Question:** can AI answer customer messages for a small business, correctly and the same way for everyone?

- **Inputs** (fictional, written for this lesson):
  - `policy.md`: Hollow Oak Bakery, custom cakes;
  - `questions.json`: 21 messages, 7 topics × 3 phrasings.
- **Answer key:** `truth.md`, fixed before the runs.
- **Model and harness:** Claude Sonnet via `automation/run_demo.py` (restricted, no tools). Each message is answered in a fresh chat, 3 runs.

## Requests
- **A:** "write a short, friendly reply", no policy. Fixed before the runs.
- **B:** the same, with the policy pasted. Fixed before the runs.
- **C** (**added after seeing A and B**): give the policy plus the 21 real questions and ask for the gaps and unclear lines (3 runs).

## Checks
- `score.py` (rule flags).
- A full read of all 126 replies (`classified.json`): correct / placeholder / guess. A guess that breaks a "must not" rule is marked `hitsMustNot`.

## Results (`scores.json`)
- **A (no policy):** 0/63 correct.
  - 37 left the fact blank or offered options.
  - 26 asserted something they weren't given; 23 of those break the policy:
    - damaged cake: 9/9 promise a refund or replacement;
    - vegan: 8/9 "yes";
    - Sunday delivery: one phrasing got a yes 3/3;
    - cancellation: the terse phrasing got a promised refund 3/3.
  - The phrasing changed the answer.
- **B (policy pasted):** 63/63 correct; same key answer across the phrasings.
  - In T6 the policy's "within 24 hours" was read as "of the order" (formal phrasing, 3/3) and "of pickup" (others). This is an ambiguity in our policy.
  - T4: 2/9 refuse outright, beyond "can't guarantee".
- **C (gap check):** in 3/3 runs it flagged the missing vegan answer, "24 hours from what?", and the nut-allergy wording.

**Limits:**
- one model, one made-up bakery, short messages, 3 runs;
- the policy is short and tidy;
- real customers write messier messages and ask follow-ups;
- tone and customer satisfaction were not scored.
