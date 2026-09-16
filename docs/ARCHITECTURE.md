# Architecture (planned Android app)

**Docs only. No application code in this repository.**

Target: Kotlin, Android, **single-activity** app. First language pair: English for Russian speakers. UI and error copy in Russian; target language in drills, listening, and speaking checks.

## Design principles

1. **Offline-first content and progress.** Bundled skill packs and local progress work without network.
2. **Network is optional.** Used for online LLM generation/check and for downloading an offline open model (one button).
3. **Skill engine, not story engine.** Content is skills → frames → slots → bans. Roles are situations with goals.
4. **AI is subordinate.** Generation and checks pass through `ai-filter` before anything reaches the learner.
5. **Dry black-and-grey shell.** Habit UX (short session, skill map, review) without characters, leagues, or plot.

## Layers

| Layer | Responsibility |
| --- | --- |
| `ui` | Compose (or View) screens, navigation, dry theme, Russian chrome |
| `domain` | Lesson orchestration, skill progress rules, stars→hints, review scheduling |
| `data` | Content packs (JSON), local progress store, optional remote download of packs/models |
| `speech` | STT / TTS wrappers; compare utterance to expected frame; no “friend” voice |
| `ai-filter` | Prompt construction within frames; hard fluff discard; editor-status gate |

```mermaid
flowchart TB
  subgraph ui_layer [ui]
    Nav[NavHost single Activity]
    Screens[Screens]
    Theme[Black-grey theme]
  end
  subgraph domain_layer [domain]
    Lesson[LessonRunner]
    Progress[ProgressRules]
    Review[ReviewScheduler]
    Stars[StarsHints]
  end
  subgraph data_layer [data]
    Content[ContentRepository]
    LocalDB[(Local progress)]
    Packs[Bundled JSON packs]
    Net[Optional network]
  end
  subgraph speech_layer [speech]
    STT[STT]
    TTS[TTS]
    Match[Frame matcher]
  end
  subgraph ai_layer [ai-filter]
    Gen[Example generator]
    Check[Answer checker]
    Filter[Fluff filter]
    Editor[Editor status gate]
  end
  Nav --> Screens
  Screens --> Lesson
  Screens --> Progress
  Lesson --> Content
  Lesson --> STT
  Lesson --> TTS
  Lesson --> Gen
  Lesson --> Check
  Progress --> LocalDB
  Content --> Packs
  Content --> Net
  Gen --> Filter
  Check --> Filter
  Filter --> Editor
  STT --> Match
  Match --> Lesson
```

## Module boundaries (implementation intent)

- **`ui`** depends on **`domain`** only (not on raw network or model SDKs).
- **`domain`** depends on **`data`**, **`speech`**, **`ai-filter`** interfaces.
- **`data`** owns serialization of schemas in [DATA.md](DATA.md) and Room/DataStore (or equivalent) for progress.
- **`speech`** and **`ai-filter`** are swappable backends (online vs on-device) behind the same contracts.
- No feature module should invent “character” or “plot” entities. Situation = `Role` object in [DATA.md](DATA.md).

## Lesson data flow

```mermaid
sequenceDiagram
  participant U as Learner
  participant UI as ui
  participant L as domain.LessonRunner
  participant C as data.Content
  participant A as ai-filter
  participant S as speech
  U->>UI: Start skill lesson
  UI->>L: open(skillId)
  L->>C: load skill + frames + bans
  C-->>L: Skill record
  L->>UI: Russian task + step
  U->>UI: Answer / speak
  UI->>L: submit(stepResult)
  alt text check
    L->>A: check against frame
    A-->>L: ok or brokenSlot + workingPhrase
  else speak check
    L->>S: STT + frame match
    S-->>L: ok or mismatch
  end
  opt generate new example
    L->>A: new example of accepted skill
    A-->>L: line or discarded
  end
  L->>C: update progress / review queue
  L->>UI: next step or error view
```

## Offline vs online

| Capability | Offline | Online |
| --- | --- | --- |
| Bundled skills, letters, cards, kindergarten | Yes | — |
| Progress, review, stars | Yes | Optional sync later (v1: local only) |
| New examples of accepted skills | If offline model installed | Online LLM |
| Answer check / broken-slot note | Rule-based always; model optional | Model optional |
| Goal mini-dialogue | If offline model installed | Online LLM |
| Offline model download | Button in Settings; needs network once | — |

**Decision (documented):** v1 progress is **device-local only**. No account required for stages 0–5. Accounts/sync are out of scope until after fluff-filter acceptance.

## Content packing

- Packs live under documented path convention `content/skills/*.json` (see [DATA.md](DATA.md)).
- App ships a first content pack sized per [BUILD.md](BUILD.md).
- `reviewStatus` and `allowGenerate` gate what AI may expand.

## Non-goals (architecture)

- Multi-activity story flows or narrative lesson graphs.
- Social leagues, friend feeds, character profiles.
- Training or hosting our own LLM weights pipeline.
- Universal chatting tutor API without frames/bans.
- iOS / Apple as a **working** tech-help path (Apple may appear only as dismissed poor gear in role content).
- Rewriting pedagogy into “warm coach” copy in the `ui` layer.

## Related docs

- Screens: [SCREENS.md](SCREENS.md)
- Schemas: [DATA.md](DATA.md)
- Build order: [BUILD.md](BUILD.md)
- Filter rules: [PEDAGOGY.md](PEDAGOGY.md)
