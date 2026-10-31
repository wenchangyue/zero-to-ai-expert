# Answer key (fixed before the first run, 2026-10-31)

Product: ChatGPT on the web, logged out, fresh chat per run, 3 runs per request.
Requests: A = bare translation of friend.txt; B = bare translation of invoice.txt;
C = friend.txt with reader + tone + "natural expressions" + "do not add or soften";
D = invoice.txt with the same template (reader = client who has not paid; tone = polite but firm).
Only the first Spanish translation in each answer is scored; notes or alternatives after it are recorded, not scored.

## friend.txt (A, C): 5 checks, each pass/fail
1. Break a leg: FAIL if the translation contains "pierna" (literal). Pass otherwise.
2. Don't sweat the small stuff: FAIL if it contains "sud" (sudar/sudes/sudéis). Pass otherwise.
3. Drinks are on me: FAIL if it contains "en mí" or "sobre mí". Pass otherwise.
4. Register: PASS if the reader is addressed with tú (e.g. te, tu, vas, estarás, preocupes); FAIL if usted forms address Lucia (usted, se preocupe, le irá).
5. Emoji: PASS if 😄 is present.

## invoice.txt (B, D): 5 checks, each pass/fail
1. Facts kept: "dos veces" (or "2 veces"), "4471", "3 de marzo", "viernes" all present.
2. Consequence kept: a verb meaning pause/stop work (pausar, pausaré, detener, detendré, suspender, suspenderé, parar, pararé) is present.
3. Not softened: FAIL if it adds any of: "si es posible", "si puede", "si pudiera", "cuando pueda", "agradecería", "lamento", "disculp", "molestia", "quizá", "tal vez". Pass otherwise.
4. Request stays a direct request: PASS if the payment request uses an imperative or present-tense request (e.g. "pague", "paga", "por favor, pague", "le pido que", "te pido que", "realice el pago"); FAIL if it is turned into a conditional/question ("podría", "podrías", "¿").
5. Nothing added: FAIL if a sentence appears whose meaning is not in the source (judged and quoted in scores.json).

## Added after seeing A–D (2026-10-31T12:50:03Z); disclosed in the lesson
Observed in A–D (not a pre-set check): all 6 invoice translations (B, D) address the client with tú (te, realiza).
E = invoice.txt; reader = "a client in Mexico whom I have never met and who has not paid"; no "natural expressions" line.
  Checks: invoice checks 1–5 above, plus 6. Register: PASS if usted forms address Daniel (usted, le he, realice, su pago); FAIL if tú (te he, realiza, tu).
F = back-check of run b1's translation in a fresh chat (prompt-f.txt). PASS if the one-line answer says informal / tú.
Key-wording note: invoice check 1 asks for "dos veces"; A–D runs write "dos correos (electrónicos)" = "two emails", which keeps the fact. Scored as kept, and this note says so.

## Added after seeing E and F (2026-10-31T12:52:14Z); disclosed in the lesson
E result: tú in 3 of 3 despite "client in Mexico whom I have never met". F result: back-check named it informal (tú) in 3 of 3.
G = E prompt plus "Use the formal usted." Checks: invoice checks 1–5 and check 6 (usted) as for E.

## Found after scoring (2026-10-31, GPT-6 gate round 1); disclosed
Invoice check 1 only required "viernes". Deadline wording: B and D wrote "antes del viernes" (before Friday) 6/6; E and G wrote "a más tardar el viernes" (no later than Friday) 6/6. F back-translations say "before Friday" 3/3. Recorded as `deadline` in scores.json.
