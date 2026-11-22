# Keeping the Lore

> The realm describes the released Rune; every pull request says what it will change.

The `lore` repo (`devneet-id/lore`, realm `realms/rune/`) is how the next person learns Rune without asking. A lore that lies is worse than no lore. It describes **the released version** — what a user gets — so it is updated **after a release**, in one pass, from the *Lore* lines of the pull requests that went into it ([docs follow the release](../../../../../covenant/workflow.md#docs-follow-the-release)). The chronicle is written as the work happens.

## What is generated, what is written
| Part | How it is made |
|---|---|
| `reference/runes/*.md` | **generated** from each rune's Phantasm (version, mark, user, note, link, node), plus a short lore intro, "When to use", an example and notes |
| `reference/runites/`, `reference/modes.md`, `lore/engravings/` | written by hand, from the built-in runites and runites that were run |
| `lore/acts/`, `lore/paradigm.md` | written by hand, one step of the user per Act |
| `reference/glossary.md` | written by hand — every lore word |

## `reference/runes/` follows the Phantasm
The tables in `reference/runes/*.md` are generated from each rune's Phantasm — the Phantasm is the source of truth. Change the Phantasm (and its `#NOTE`s) in `rune` first; the page follows on the next lore update. A pull request that only edits a table in `reference/runes/` will be overwritten.

The lore intro, "When to use", the example and the notes are written by hand. Every example must run.

## Rules for writing
- English, short sentences. Lore first (1–3 sentences), then *In code*.
- Every example runs. Run it before you write it down.
- Every runite example starts with `#!/usr/bin/env php`.
- An Act only uses runes met so far: Act 0 — Aether, Whisper, Weaver, Chanter; Act 1 — + Forger, Cipher, Keeper; Act 2 — + Crafter; Act 3 — + Specter, Minister and your own runes.
- One page, one topic. Link, do not repeat.
- A new word goes into the [Glossary](../../../reference/glossary.md) first, with the same name as in code.

## When something changes
Every pull request in `rune` carries a *Lore* line: the pages below that will change. After the release, they are updated together.

| Change in `rune` | Update in `lore` (`realms/rune/`) — after the release |
|---|---|
| a node added/removed | its `reference/runes/` page; check Acts that use it |
| a built-in runite spell | `reference/runites/<name>.md` |
| a mode | `reference/modes.md` and its Act page |
| a rename | Glossary (old → new), [Decisions](decisions.md), every page that used the old name |
| a bug fixed | remove it from [Known Issues](known-issues.md) and from "Known issue" notes in `reference/runes/` |
| a release | rune versions in [Versioning](versioning.md) |
