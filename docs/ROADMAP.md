# Build stages (when code starts)

No code is in this repository yet. This is the order to implement later.

**Concrete acceptance (“done when”) for every stage:** [BUILD.md](BUILD.md).  
**Architecture / data / screens:** [ARCHITECTURE.md](ARCHITECTURE.md) · [DATA.md](DATA.md) · [SCREENS.md](SCREENS.md).

## Stage 0 — Alphabet and cards

- Latin letter cards with a Cyrillic sound hint.
- No account, no plot.
- Local storage of “seen / shaky / known.”

**Done when:** cold install works offline; letter state persists; no character/league UI. Details: [BUILD.md](BUILD.md#stage-0--alphabet-and-cards-shell).

## Stage 1 — First words

- Bilingual cards (`верх` / `top` and the kindergarten set).
- Fast-forward if the person already matches them reliably.
- Stars start accruing; they can later become hints.

**Done when:** pairs match both ways; probe can skip easy cards; stars visible. Details: [BUILD.md](BUILD.md#stage-1--first-words).

## Stage 2 — Kindergarten Q&A

- Up/down, left/right, day/night, morning/evening, clock/hours.
- Short question–answer only. No generated dialogue.

**Done when:** coverage complete; zero LLM calls; gate opens situations. Details: [BUILD.md](BUILD.md#stage-2--kindergarten-qa).

## Stage 3 — Skill engine

- Data files (or a small database) for skills: frames, substitutions, bans, review flags.
- One-skill lesson runner: assemble, substitute, listen, speak, fill-the-gap.
- Error view: which frame slot broke + the working phrase.
- Weak-item review.

**Done when:** filled skills `price`, `refuse`, `unwell` run end-to-end; draft/rejected never shown. Details: [BUILD.md](BUILD.md#stage-3--skill-engine). Schemas: [DATA.md](DATA.md).

## Stage 4 — Situation tracks

- Shop (price at checkout, detergent, discount card).
- Travel (airport, train, ticket, customs, suitcase).
- Household survival tasks as they fit A1 frames.
- Tech help on Linux/Windows and Android; Apple only as dismissed poor gear.

**Done when:** shop/travel/tech roles load; Apple framing rule held in content. Details: [BUILD.md](BUILD.md#stage-4--situation-tracks). Roles: [ROLES.md](ROLES.md).

## Stage 5 — Reminders of the habit

- Short session, skill map, streak of days, `done` / `weak` / `review`.
- Notification that calls to **one action**, not a story.

**Done when:** map markers live; one-action notifications only. Details: [BUILD.md](BUILD.md#stage-5--habit-shell).

## Stage 6 — Filtered generation

- Online model: new examples of an already accepted skill; check answers.
- Mini-dialogue only with an external goal.
- Hard discard filter + human editor queue.
- Optional **one-button** download of a local open model for offline, same filter.

**Done when:** only `allowed_to_generate_from` seeds; fluff never reaches UI; offline button works. Details: [BUILD.md](BUILD.md#stage-6--filtered-generation). Filter: [PEDAGOGY.md](PEDAGOGY.md).

## Stage 7 — Speech

- STT/TTS wrap. Compare to the expected frame.
- No friendly-character voice.

**Done when:** speak-formula matches frames; voice is functional. Details: [BUILD.md](BUILD.md#stage-7--speech).

## Stage 8 — Second language pair

- Only after the pipeline and the fluff filter are stable on English-for-Russian.

**Done when:** two-week acceptance proven on first pair; schemas unchanged. Details: [BUILD.md](BUILD.md#stage-8--second-language-pair).

## Done when (product)

The two-week acceptance in the whitepaper is true on a device, not only on paper — checklist in [BUILD.md](BUILD.md#checklist-whitepaper-two-week-fluff-free-acceptance--dry-exam).
