# Praxis whitepaper

A practical A1 trainer. Android. First pair: English for Russian speakers.

## 1. Product sentence

Praxis teaches a person to **do things** in a foreign language at the first functional floor (A1 or the same idea under another name). It does not teach them to inhabit a fictional life.

## 2. What “acting” means

After the base catalog the learner can:

- ask, clarify, name, compare;
- refuse, confirm;
- understand a short announcement;
- ask to repeat or speak slower;
- report the state of an object (fresh, broken, open, closed);
- when needed, briefly report their own state **as a service fact** (I feel unwell, this place hurts, I cannot walk further) — for a cashier, a pharmacy, a certificate, transport, or a service, not as drama.

Every phrase in the course has a checkable function: what the person wants, what the other person must understand, what counts as success. If a line exists only for atmosphere, character, warmth, flirt, jealousy, confession, holiday romance, sexual hint, or small talk about feelings — it does not enter.

Allowed “state” lines are the ones without which a practical task cannot be solved (broken cup ruined the morning as a **reason at a desk**, not a novella).

## 3. Core object: the skill, not the chapter

The nucleus is a **catalog of skills**, not chapters and not heroes.

Each skill record:

- task being solved;
- external success (what a stranger would accept);
- 2–4 obligatory phrase frames;
- which words can be swapped in the frame;
- typical errors;
- forbidden topics for this skill.

Content is stored as skills, frames, substitutions, audio references, and bans — not a book with plot chapters. Each item has a review status and a flag: may new examples be generated from it.

## 4. Shell vs inside

**Take from the familiar habit apps:** short session, visible skill path, review of what the person actually misses.

**Do not take:** tone of a series, characters, memes, friend leagues, narrative lessons, “you are the hero.”

## 5. Layers of mechanics

| Layer | What the learner does | AI dialogue? |
| --- | --- | --- |
| 0 Letters | See a Latin sign, hear/see a Cyrillic sound hint | No |
| 1 Word cards | Match `верх` ↔ `top` and the same pattern | No |
| 2 Kindergarten Q&A | Up/down, left/right, day/night, morning/evening, clock | No |
| 3 Situation drills | One skill, a few minutes: assemble, substitute, listen, speak | Only examples of a described skill |
| 4 Goal dialogue | A few turns with an outside goal | Yes, filtered |

A person who already knows some language skips 0–2 quickly.

**Stars → hints.** Progress rewards can be converted into a hint when stuck.

## 6. A lesson

A few minutes. One skill. Task shown in Russian. Then, in the target language:

- build the phrase from parts;
- put another object into the same frame;
- pick the answer that matches the task;
- listen to a short line and pull out price / deadline / place / condition;
- speak the working formula;
- fill a missing service word.

On error: no story, no comfort. Show which frame element broke and what the correct working phrase looks like. Review is built from the skills and words this user actually confuses.

Speech loop is the same: speak the formula or answer in a narrow scene (cashier, counter, desk, announcement, malfunction, wellbeing-as-fact). The system matches the frame and says whether the line is understandable and what was lost. It does not pretend to be a friend.

## 7. AI rules (hard)

Allowed: new examples of an already described skill; change object and number; check; short error note; mini-dialogue **only** with an external goal (ticket, storage period, replace an item, where to go, call for help, “I feel unwell”).

Forbidden: characters; private-life questions; relationship jokes; praising the user as a hero; small talk; romantic or sexual scenes.

Discard before display if: no checkable function; romantic/sexual fluff; feeling offered instead of action.

Until a template passes the filter **and** a human editor, it is not course material.

Offline: optional download of an open model into the app (one button). Same frames. We do not train our own LLM. We wrap ready STT / TTS / text-check models under the pedagogical filter. Not a chatting tutor — a **task tutor**.

## 8. Roles (not characters)

Roles are situations you walk through: I am buying detergent; I am at customs; this computer will not install the program.

See [ROLES.md](ROLES.md).

## 9. Platform and later pairs

- v1: Android. One pair: English ← Russian UI.
- A second pair (e.g. German) only after the content pipeline and the fluff filter have proven stable on the first pair.

## 10. Acceptance (repeat)

Two weeks of daily study, zero romance/plot/sex/family-serial/hero tasks. Then a dry exam of everyday actions. Dry + accurate = pass. Fun + inaccurate = fail.

## 11. What v1 does not include

- Imitating mass apps in tone, characters, memes, leagues, narrative lessons.
- Building our own large language model.
- A universal chatting tutor.
- iPhone/Mac as the **working** path (they may appear only as the bad gear that gets dropped).

## 12. What v1 does include

- Short session + visible skill progress.
- Careful wrapping of ready speech and text models.
- A human editor in the loop.
- The first-wave skill list in [SKILLS.md](SKILLS.md).
