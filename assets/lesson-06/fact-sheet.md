# Fact sheet — fixed 2026-09-27 before any run

Fictional household, written for this test. No real people.

## The facts (what is true for this cook)

| # | Fact | Scored as |
| --- | --- | --- |
| F1 | Cooking for three: me, my partner, our 6-year-old. | — (context) |
| F2 | My partner is vegetarian: no meat, no fish. Eggs and dairy are fine. No allergies in the house. | S1 |
| F3 | Kitchen: a two-burner stove and a microwave. No oven (broken), no air fryer, no slow cooker, no pressure cooker. | S2 |
| F4 | Monday–Thursday dinner must be on the table within 25 minutes of starting. Weekends: up to an hour is fine. | S3 |
| F5 | Our 6-year-old won't eat anything spicy. Otherwise eats most things. | S4 |
| F6 | Friday is takeout, so only Saturday–Thursday need dinners (six). | S5 |
| F7 | Shopping once a week, on Sunday. | — |
| F8 | Budget: cheap-ish, nothing fancy. No number. | — |
| F9 | Likes pasta, rice bowls and soups; no other strong preferences. | — |
| F10 | Can follow a recipe; nothing fancy. | — |

## How I answer the model's questions (interview condition)

- Answer only what each question asks, in one or two plain sentences, using only this sheet. Never volunteer a fact that was not asked for.
- "Dietary restrictions / allergies" → F2. "Preferences / dislikes / picky eaters / what do you like" → F5 and F9. A question naming both → both.
- "Who are you cooking for / how many" → F1. "Kitchen / equipment / appliances" → F3. "How much time / how long to cook" → F4. "Which days / how many dinners / eating out" → F6. "Shopping" → F7. "Budget" → F8. "Skill / experience" → F10.
- Anything else → "No strong preference."
- If the model asks follow-up questions instead of giving the plan, answer them by the same rules and let it continue. The plan it finally gives is the one scored.

## Scoring (applied to every final plan, all conditions; unit = one dinner)

- **S1 vegetarian** — fails if the dinner contains meat or fish and gives no vegetarian version for the partner.
- **S2 equipment** — fails if any step needs an oven, broiler, baking, sheet-pan roasting, air fryer, slow cooker or pressure cooker.
- **S3 weeknight time** — a Monday–Thursday dinner fails if its stated time is over 25 minutes. No stated time is counted separately as "no time given", not as a failure.
- **S4 spice** — fails if the dish is spicy by design (chili, jalapeño, sriracha, hot sauce, red pepper flakes, curry paste, chipotle, gochujang, "spicy") and does not make it mild or optional for the child.
- **S5 Friday** — the plan fails once if it plans a cooked Friday dinner.

The plain condition cannot know any of F2–F6. Counting its failures is not a verdict on the model; it measures how much a guess costs.

> Note added after gate round 1 (2026-09-27): the scoring rules above were applied with a fails/unclear split. The rules as applied are in `scores.json` → `rubric`. The facts and the answering rule are unchanged.
