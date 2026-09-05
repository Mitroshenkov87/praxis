# Build stages (when code starts)

No code is in this repository yet. This is the order to implement later.

## Stage 0 — Alphabet and cards

- Latin letter cards with a Cyrillic sound hint.
- No account, no plot.
- Local storage of “seen / shaky / known.”

## Stage 1 — First words

- Bilingual cards (`верх` / `top` and the kindergarten set).
- Fast-forward if the person already matches them reliably.
- Stars start accruing; they can later become hints.

## Stage 2 — Kindergarten Q&A

- Up/down, left/right, day/night, morning/evening, clock/hours.
- Short question–answer only. No generated dialogue.

## Stage 3 — Skill engine

- Data files (or a small database) for skills: frames, substitutions, bans, review flags.
- One-skill lesson runner: assemble, substitute, listen, speak, fill-the-gap.
- Error view: which frame slot broke + the working phrase.
- Weak-item review.

## Stage 4 — Situation tracks

- Shop (price at checkout, detergent, discount card).
- Travel (airport, train, ticket, customs, suitcase).
- Household survival tasks as they fit A1 frames.
- Tech help on Linux/Windows and Android; Apple only as dismissed poor gear.

## Stage 5 — Reminders of the habit

- Short session, skill map, streak of days, `done` / `weak` / `review`.
- Notification that calls to **one action**, not a story.

## Stage 6 — Filtered generation

- Online model: new examples of an already accepted skill; check answers.
- Mini-dialogue only with an external goal.
- Hard discard filter + human editor queue.
- Optional **one-button** download of a local open model for offline, same filter.

## Stage 7 — Speech

- STT/TTS wrap. Compare to the expected frame.
- No friendly-character voice.

## Stage 8 — Second language pair

- Only after the pipeline and the fluff filter are stable on English-for-Russian.

## Done when

The two-week acceptance in the whitepaper is true on a device, not only on paper.
