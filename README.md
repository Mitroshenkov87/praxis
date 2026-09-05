# Praxis

**Docs only. No application code yet.**

Praxis is a planned Android app for self-study of a foreign language as a **practical tool** — not as a story, not as a social game, and not as a romance. The first language pair is **English for a Russian-speaking learner**. The interface and error explanations are in the learner’s language (Russian first). The target language appears in examples, listening, and speaking checks.

This repository is a whitepaper and a build map: what to make, in what order, and what must never enter the course. Anyone may read it, fork it, and later implement it under the MIT License.

## Why this exists

Mass self-study products often open with meeting characters, family, friendship, dating, and a love plot. Some people lose the will to study before grammar even starts. Praxis removes that false door. After practice the learner should **act** with the language: ask a price, refuse, understand an announcement, report that a thing is broken, say they feel unwell because they need a service — not perform someone else’s private life.

The European A1 label (or any other name for the same floor) is the first target: a functional minimum.

## What it looks like

The **outer shell** may feel familiar (short daily sessions, a skill map, review of weak spots — the Duolingo-shaped habit). The **inside** is a technical trainer of speech acts.

- Black-and-grey, dry, no character, no league, no memes as the product.
- Progress is a map of skills and how reliable each skill is (`done`, `weak`, `review`, a streak of study days).
- Reminders call you to drill one action, not to continue a story.

## Learner path (first version)

1. **Zero.** The person may know neither English nor the Latin alphabet. Flashcards: Latin letter + a Cyrillic hint of how it roughly sounds.
2. **First words.** Bilingual cards: `верх` / `top`, and the same for other kindergarten pairs.
3. **Kindergarten Q&A.** Up/down, left/right, day/night, morning/evening, hours/clock. Short questions and answers. No generated dialogue yet.
4. **Situations.** Roles that are life tasks, not characters: shop, travel, household, tech help.
5. **On-the-fly dialogue** only when there is an external goal (ticket, storage date, replacement, where to go, call for help, “I feel unwell”).

Someone who already knows some of the language should fly through the early cards and get to harder work sooner. Stars earned in practice can be spent on hints.

## Situation tracks (v1)

- **Shop / everyday:** household chemicals, detergent for two loads, price at the checkout, discount cards.
- **Travel:** airport, train, customs, tickets, packing a suitcase, packing a first-aid kit.
- **Tech:** computer problems, install a program, download an app. Working path is **Linux or Windows** and **Android phones**. If Apple hardware or software appears in a dialogue, it is framed as poor gear and dismissed; the person switches to the working path. Offline pieces (for example a local model) download with a simple button.

Slots of content always stay practical. Acquaintance-for-its-own-sake, family-as-series, dates, compliments on looks, and sexual subtext are out of the first wave. A name at a desk, if needed later, is given without biography.

## AI (subordinate)

Dialogues and answer variants are **constructed in flight**, not a bank of hardcoded scripts. A model may:

- invent new examples of an **already described** skill (change the object and the number);
- check an answer and name which piece of the phrase-frame broke;
- run a short goal-bound mini-dialogue.

It must not create characters, ask about private life, joke about relationships, praise the user as a hero, drift into small talk, or generate romantic/sexual scenes. Any generated line is thrown away before the learner sees it if it has no checkable function.

**Offline:** an open-source model can be downloaded into the app and used inside the same frames and bans. We do **not** train our own large language model. A human editor is mandatory: AI proposes, editor cuts. A template is not course material until it passes the filter.

## First-version acceptance

A new user who is sick of textbook romance can study every day for two weeks and never meet a task about courtship, sexual subtext, family-as-series, or a fictional hero’s personality. After the base catalog they can, in a training check: get a price and a deadline, understand an announcement, ask a clarifying question, refuse, specify quantity and place, report a simple problem with an object, and if needed briefly state feeling unwell or a concrete everyday mishap **as a fact**.

If the product entertains with plot but does not raise accuracy of these actions — fail. If it is dry but the actions become more reliable — pass.

## Documents in this repo

| File | What it is |
| --- | --- |
| [docs/WHITEPAPER.ru.md](docs/WHITEPAPER.ru.md) | Full original-language spec (the long cloth) |
| [docs/WHITEPAPER.md](docs/WHITEPAPER.md) | Same idea in English, structured |
| [docs/ROADMAP.md](docs/ROADMAP.md) | Step-by-step what to build, in order |
| [docs/SKILLS.md](docs/SKILLS.md) | First-wave skill catalog |
| [docs/ROLES.md](docs/ROLES.md) | Situation roles and tech rules |
| [docs/PEDAGOGY.md](docs/PEDAGOGY.md) | Frames, errors, fluff filter, AI rules |
| [docs/ONBOARDING.md](docs/ONBOARDING.md) | Letters → cards → kindergarten layer |

## Platform

Android first. Signed, when we build, as Aleksandr Mitroshenkov. No code lives here until a later decision.

## License

[MIT](LICENSE) — Copyright (c) 2026 Aleksandr Mitroshenkov. Anyone may use, change, and rebuild this for their own needs.
