# Demo design — fixed 2026-09-28 before any run

Question: when AI seems to forget something you told it earlier, what is actually going on, and what fixes it?

Model and harness: Claude Sonnet via `automation/run_turn.py --usage` (plain assistant, no tools, no settings files, stdin closed; later turns use `--resume` so the model sees real conversation history). The CLI reports the model as `claude-sonnet-5` with a context window of 1,000,000 tokens (probe 2026-09-28). Overflowing that window would cost about a million tokens per turn, so this test does not try to.

## The facts (turn 1 of every conversation that has a setup)

Same fictional household as lesson 06, written as one message (`setup.txt`):
cooking for three (me, partner, 6-year-old); partner vegetarian; two burners and a microwave, no oven; weeknight dinner in 25 minutes; child eats nothing spicy; Friday takeout. It ends "Just reply OK for now."

## Final question (last turn everywhere)

"What should I make for dinner tonight? It's Tuesday." (`final.txt`)

## Four versions, three runs each

| Version | Turns | What sits between the facts and the question |
| --- | --- | --- |
| A long chat | 14 | 12 ordinary requests with nothing about food, cooking or the family (`filler-01.txt` … `filler-12.txt`) |
| D long paste | 3 | one pasted synthetic maintenance log (seed 42, ~4,000 entries, no food or kitchen words) with a counting task (`paste.txt`) |
| B new chat | 1 | nothing: the question alone, in a new conversation |
| C new chat + brief | 1 | the same facts pasted above the question in one new message (`brief-plus-final.txt`) |

## Scoring the final answer (unit = one answer; a failure counts only when the text clearly shows it)

- **F1 vegetarian** — suggests meat or fish with no vegetarian version for the partner.
- **F2 no oven** — clearly needs an oven, baking, roasting, air fryer, slow cooker or pressure cooker.
- **F3 25 minutes** — a stated time over 25 minutes. No stated time is recorded as "no time given", not a failure.
- **F4 not spicy** — spicy by design (chili pepper, jalapeño, sriracha, hot sauce, red pepper flakes, curry paste, chipotle, gochujang, "spicy") and not made mild for the child. Spice level not stated → "unclear", not a failure.
- Also recorded, not scored: whether the answer names any of the facts explicitly, and whether it asks a question instead of answering.
- Token usage per turn is recorded from the CLI's own report.
