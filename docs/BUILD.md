# Build stages — acceptance (“done when”)

**Docs only. No application code here.** Implement elsewhere against [ARCHITECTURE.md](ARCHITECTURE.md), [DATA.md](DATA.md), and [SCREENS.md](SCREENS.md). Stage index also lives in [ROADMAP.md](ROADMAP.md).

Signer when builds exist: **Aleksandr Mitroshenkov**. License: MIT.

## First content pack (size suggestion)

Ship with stage 3+:

| Area | Suggested minimum |
| --- | --- |
| Letters | Full Latin set used in English + Cyrillic sound hints |
| Word cards | Kindergarten set (≥ 10 pairs including `верх`/`top`) |
| Kindergarten Q&A | ≥ 20 fixed items |
| Skills fully filled | **`price`**, **`refuse`**, **`unwell`** (see [DATA.md](DATA.md)) plus stubs for remaining first-wave ids in [SKILLS.md](SKILLS.md) |
| Roles | ≥ 1 shop, ≥ 1 travel, ≥ 1 tech (Linux/Windows/Android working path) |
| Audio | ≥ 1 ref per filled skill |

Stubs may be `draft` and locked from Lesson runner until `accepted`.

---

## Stage 0 — Alphabet and cards shell

**Build:** Letters screen; local seen/shaky/known; no account; dry theme.

**Done when:**

- [ ] Learner can open Letters from a cold install with no network.
- [ ] Each letter shows Latin sign + Cyrillic sound hint.
- [ ] State persists across process death.
- [ ] No plot, character, or league UI exists on these screens.

## Stage 1 — First words

**Build:** Word cards; stars accrual; fast-forward probe.

**Done when:**

- [ ] `верх` / `top` and kindergarten pairs match in both directions.
- [ ] Probe set can skip remaining easy cards when reliability threshold is met.
- [ ] Stars increment; balance visible on Home (even if hints not yet spendable).

## Stage 2 — Kindergarten Q&A

**Build:** Fixed short Q&A; no AI dialogue.

**Done when:**

- [ ] Up/down, left/right, day/night, morning/evening, clock covered.
- [ ] Zero calls to any LLM on this path.
- [ ] Gate opens Situation picker only after threshold.

## Stage 3 — Skill engine

**Build:** Load skills from JSON; Lesson runner step types; Error/broken-slot; review queue.

**Done when:**

- [ ] `price`, `refuse`, `unwell` load from pack and run 4–6 step lessons.
- [ ] Fail path shows broken slot + working phrase (Russian chrome, English phrase).
- [ ] Review lists only items this device confused.
- [ ] Skills with `reviewStatus=draft|rejected` never appear in Lesson.

## Stage 4 — Situation tracks

**Build:** Situation picker; shop / travel / tech roles; Apple framing rule in content.

**Done when:**

- [ ] Shop role can start price/refuse/quantity drills.
- [ ] Travel role includes ticket/customs-style goals without romance.
- [ ] Tech role working path is Linux or Windows / Android; Apple lines only as dismissed poor gear.
- [ ] Role object matches schema in [DATA.md](DATA.md).

## Stage 5 — Habit shell

**Build:** Skill map markers; streak; one-action notifications.

**Done when:**

- [ ] Home shows `done` / `weak` / `review` / `unseen`.
- [ ] Notification copy names one action (skill), not a story continue.
- [ ] Session target remains a few minutes per skill.

## Stage 6 — Filtered generation

**Build:** Online LLM behind `ai-filter`; editor status gate; optional one-button offline open model.

**Done when:**

- [ ] Model may only generate examples of `allowed_to_generate_from` skills.
- [ ] Fluff filter discards lines with no checkable function, romance/sex, emotion-instead-of-action, character-building, private-life questions, hero praise, small talk — before UI display.
- [ ] Human editor statuses are respected (draft/rejected never shown).
- [ ] Settings downloads offline model with one primary button; same filter applies offline.
- [ ] No custom LLM training pipeline in the app.

## Stage 7 — Speech

**Build:** STT/TTS wrap; frame match; Error on mismatch.

**Done when:**

- [ ] Speak-formula step compares to expected frame.
- [ ] Voice UX is functional, not a friendly character.
- [ ] Works offline for TTS/STT engines that are on-device; network only if engine requires it (document per engine choice).

## Stage 8 — Second language pair

**Build:** Second UI/target pair (e.g. German) only after pipeline proof.

**Done when:**

- [ ] Fluff filter + editor queue proven stable on English←Russian for the two-week acceptance below.
- [ ] Content schemas unchanged; new packs only.

---

## Checklist: whitepaper two-week fluff-free acceptance + dry exam

Map product acceptance ([WHITEPAPER.md](WHITEPAPER.md) §10) to a device test after stages 3–7.

### A. Two weeks, zero fluff

| Check | Pass criterion |
| --- | --- |
| Daily study available | Short session path works offline for bundled content |
| No romance tasks | Manual audit of all shown prompts for 14 days of scripted use: zero courtship / sexual subtext / family-as-series / fictional hero personality |
| No character chrome | Screens audit: no avatars-as-cast, leagues, meme-as-product |
| AI path | If generation on: filter logs show discards; learner never sees discarded lines |

### B. Dry exam of everyday actions

After base catalog practice, in a training check the learner can:

| Action | Linked skills (minimum) |
| --- | --- |
| Get a price and a deadline | `price`, `deadline` |
| Understand an announcement | `announcement` |
| Ask a clarifying question | `clarify` |
| Refuse | `refuse` |
| Specify quantity and place | `quantity`, `place` |
| Report a simple object problem | `working` |
| State unwell / everyday mishap as fact | `unwell`, `everyday_mishap` |

**Pass:** dry UI + these actions more reliable than at start.  
**Fail:** entertaining plot with inaccurate actions — or fluff present.

### C. Architecture smoke

- [ ] Single-activity navigation matches [SCREENS.md](SCREENS.md).
- [ ] Offline progress survives reboot.
- [ ] Offline model button present in Settings (stage 6+).
- [ ] Signed build identity: Aleksandr Mitroshenkov (when releasing).

---

## Related docs

- Roadmap summary: [ROADMAP.md](ROADMAP.md)
- Pedagogy filter: [PEDAGOGY.md](PEDAGOGY.md)
