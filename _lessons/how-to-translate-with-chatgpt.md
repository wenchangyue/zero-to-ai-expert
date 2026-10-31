---
published: true
layout: lesson
title: "How to Translate with ChatGPT Without Losing Your Tone"
description: >-
  A casual text and a firm invoice email translated into Spanish in fresh ChatGPT
  chats, scored against checks fixed before the runs, plus a check you can run
  without speaking the language: translate it back in a new chat, then ask
  "formal or informal?"
date: '2026-10-31'
modified: '2026-10-31'
course: AI Tools and Workflows
level: Beginner
duration_label: 5 minutes
duration: PT5M20S
youtube_url: "https://youtu.be/yY98JCQwxcs"
video_id: "yY98JCQwxcs"
video_status: public
upload_date: "2026-10-31"
keywords:
  - how to translate with ChatGPT
  - ChatGPT translation prompt
  - ChatGPT Spanish translation
  - translate with AI
  - AI for beginners
  - Zero to AI Expert
quick_answer: >-
  Tell ChatGPT who the reader is and the tone you want, name the formal or familiar
  "you" when the language has both, and check the result in a new chat. In a test on
  2026-10-31 (ChatGPT, logged out, three fresh chats per request), a plain "translate
  this into Spanish" kept the tone, idioms and emoji of a casual text in 3 of 3 runs.
  A firm invoice email was not softened, but every run used the familiar "tú" for the
  client, even when told the client is in Mexico and the writer has never met them;
  adding "use the formal usted" gave usted in 3 of 3. Six of twelve invoice translations
  turned "by Friday" into "antes del viernes" (before Friday). A back-translation
  showed the deadline change; only a direct "formal or informal?" question showed the "you".
learning_outcomes:
  - Write a translation prompt that names the reader, the tone and the "you".
  - Check a translation without speaking the language.
  - Know what a back-translation can and can't show.
faq:
  - question: How do I translate with ChatGPT without losing my tone?
    answer: >-
      Say who it's for and the tone you want, name the formal or familiar "you" if
      the language has both, and ask it not to add or soften anything. In this test
      the plain request already kept the tone of a casual text; the line that
      changed the result was naming the "you".
  - question: Does ChatGPT use tú or usted in Spanish?
    answer: >-
      In this test it used the familiar tú for a client in all 9 invoice runs that
      didn't name it, including "a client in Mexico whom I have never met". With
      "use the formal usted" it used usted in 3 of 3. Which one is right depends on
      the reader and the country.
  - question: How can I check a translation if I don't speak the language?
    answer: >-
      Open a new chat, paste the translation, and ask for a word-for-word
      translation back into English; compare dates, deadlines and numbers. Then ask
      one direct question about what English can't show, such as "formal or
      informal?". Here the back-translation showed "before Friday" (the original
      said "by Friday"), and the direct question named "Informal (tú)" in 3 of 3.
  - question: Why doesn't a back-translation show formal or informal?
    answer: >-
      English has one "you", so tú and usted both come back as "you". The
      difference disappears on the way back unless you ask about it.
  - question: Can I rely on ChatGPT to check its own translation?
    answer: >-
      The back-check is ChatGPT checking ChatGPT. It caught both changes here, but
      for anything that really matters, a native speaker is the better check.
sources:
  - label: The casual text
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-24/friend.txt
  - label: The invoice email
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-24/invoice.txt
  - label: Answer key (hash recorded before the first run; later additions dated)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-24/truth.md
  - label: Hashes and times
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-24/fixed-before-runs.sha256
  - label: Every answer (ads removed)
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-24/all-answers.json
  - label: Scores
    url: https://wenchangyue.github.io/zero-to-ai-expert/assets/lesson-24/scores.json
  - label: Spanish personal pronouns (tú familiar, usted polite; varies by region), Wikipedia
    url: https://en.wikipedia.org/wiki/Spanish_personal_pronouns
---

## The problem

You want to send a message in a language you don't speak. ChatGPT will translate it, but will it still sound like you, and how would you know?

## The test

ChatGPT on the web without logging in, three fresh chats per request, 2026-10-31 between 08:45 and 09:00 New York time. The checks for the first four requests were fixed and hashed before the first run. Requests E, F and G were added after seeing earlier results, and the deadline change was found after scoring; `truth.md` records when.

| Request | Result (3 runs each) |
| --- | --- |
| A. "Translate this into Spanish:" a casual text to a friend (3 idioms, a smiley) | 5 of 5 checks in every run: no literal idiom ("Muchísima/Mucha suerte", "invito yo / corren por mi cuenta"), familiar tú, smiley kept |
| C. Same text; prompt names the reader and tone, asks for natural expressions, nothing added | 5 of 5 in every run |
| B. "Translate this into Spanish:" a firm invoice email | Not softened; invoice number, date and consequence kept; "by Friday" → "antes del viernes" (before Friday); familiar tú |
| D. Invoice; "a client who has not paid", polite but firm | Same as B, plus a subject line the email didn't have |
| E. Invoice; "a client in Mexico whom I have never met" | Familiar tú in 3 of 3; deadline "a más tardar el viernes" (no later than Friday) |
| F. New chat: translate run B1 back word for word, then "formal or informal?" | Back-translation says "before Friday"; "Informal (tú)" in 3 of 3 |
| G. E plus "Use the formal usted." | usted ("Le he enviado", "realice") in 3 of 3; deadline "no later than Friday" |

Labeled ads appeared under some answers (tutoring, translation services). They are not part of the answers and are removed from the published files.

## Reader, Register, Read back

1. **Reader** (nice to have). Say who it's for and the tone you want. In this test it didn't change the "you".
2. **Register** (must). If the language has a familiar and a polite "you", name the one you want.
3. **Read back** (must). In a new chat, translate it back and compare dates, deadlines and numbers. Then ask "formal or informal?", because English has one "you" and the difference disappears on the way back.

The prompt:

```
Translate this into [language].
It's for [reader].
Keep my tone: [two or three words].
Use the formal "you." (or: the familiar one)
Don't add or soften anything.

[paste your message]
```

## Boundary

One language (Spanish), two short messages, ChatGPT without logging in, one morning. Longer or more emotional writing may lose more of your voice. The back-check is ChatGPT checking ChatGPT; for anything that matters, ask a native speaker.

## Page status

This page is a reviewed lesson companion. It follows the final narration and caption track but reorganizes the material for reading; it is not a verbatim transcript.
