# Rune

**Repo:** `devneet-id/rune` · **Package:** `devneet/rune` · **Language:** PHP (8.1+) · **License:** MIT · **Current:** v1.21.140 (untagged; last tag v1.21.117)

> A lore-driven, modular concept beneath PHP that responds to development rather than dictating it.

Rune is the foundation of the DEVNEET ecosystem — lightweight, lazy-loaded, process-based. No bootstrapping; each rune awakens only when invoked. Its documentation is alive: every rune describes itself in its **Phantasm**, read by the Grimoire, instead of Reflection.

## How the pages are laid out

The realm is flat — every page sits here, under this README:

| Side | Pages | What they hold |
|---|---|---|
| **Story** — read in order | [`paradigm.md`](paradigm.md), [`acts/`](#the-acts--learn-step-by-step), [`engravings/`](engravings/README.md) | why Rune exists, the five Acts step by step, recipes and traps |
| **Technical** — look things up | [`runes/`](runes/README.md), [`runites/`](runites/README.md), [`modes.md`](modes.md), [`glossary.md`](glossary.md) | the ten origin runes (generated from each Phantasm), the built-in runites, the modes, every Rune word |

Start with the [Paradigm](paradigm.md): why Rune exists and the rules it keeps. Then walk the Acts.

### The Acts — learn step by step
Each Act is one step of understanding. An Act only uses the runes you have met so far.

| Act | Runes | What you learn |
|---|---|---|
| [Act 0 · The Void](acts/0-the-void/README.md) | Aether, Whisper, Weaver, Chanter | The prologue: what a rune is, how a runite is shaped — and your first cast. |
| [Act 1 · First Resonance](acts/1-first-resonance/README.md) | the four, then Forger, Cipher, Keeper | Resonate with each rune by building a CLI app; it learns to remember; meet the relic. |
| [Act 2 · Understanding Its Flow](acts/2-understanding-its-flow/README.md) | all of Act 1 + Crafter | How the runes flow together, using them beyond the Manifest, and bundling. |
| [Act 3 · Evolution of Eidos](acts/3-evolution-of-eidos/README.md) | Specter, Minister, then your own runes | Go beyond the flow, create runes of your own, and build new apps. |
| [Act 4 · The Beyond](acts/4-the-beyond/README.md) | all | See Rune from the inside, keep it alive, release it and contribute — share relics through the federation of reliquaries, and carry your own PHP. |

### Look it up
- **[Engravings](engravings/README.md)** — how to engrave common runites, and the traps.
- **[Runes](runes/README.md)** — the ten origin runes, node by node (generated from each Phantasm).
- **[Runites](runites/README.md)** — the built-in runites: [Awakening](runites/awakening.md), the [main hall](runites/rune.md), [Grimoire](runites/grimoire.md), [Reliquary](runites/reliquary.md), [Sentinel](runites/sentinel.md) — and the shape of your own.
- **[Modes](modes.md)** — Evolution, Federation, Liberation: what each one unlocks, its folder and its record.
- **[Glossary](glossary.md)** — every Rune word with its technical meaning.
- Inside the package: [Anatomy](acts/4-the-beyond/anatomy.md) · [Laws](acts/4-the-beyond/laws.md) · [Versioning](acts/4-the-beyond/versioning.md) · [Decisions](acts/4-the-beyond/decisions.md).

### Runes and Runites
Two words you will meet everywhere:

| | **Runes** | **Runites** |
|---|---|---|
| What | The **core** — the basic building blocks of Rune (Aether, Whisper, Weaver, Chanter, Forger, Cipher, Keeper, Crafter, Specter, Minister) | The **apps** — files engraved from the runes |
| Made of | Ether, Essence, Entity, Manifest, Phantasm | `use` runes, awaken them, register casts |
| Lives in | the Rune package (and `@evolution/` for your own runes) | your project, e.g. a file named `cast` |
| Examples | `Keeper::item()`, `Whisper::echo()` | Awakening, Grimoire, Reliquary, Sentinel — and **every app you build** |

Runes are what Rune gives you. Runites are what you build with them — the built-in runites are simply the first ones, made the same way yours will be.

### Laws of the Rune (invariants)

1. One rune, one purpose.
2. Entity holds the logic; entities call other entities.
3. Manifest only forwards to entities.
4. Phantasm is the contract (replaces Reflection).
5. Aether flows everywhere; runes awaken together in one flow.
6. Every change raises the Phantasm version of the rune that changed.
7. An evolution rune never replaces an origin rune.

The full list, with the reason for each, is in [Laws](acts/4-the-beyond/laws.md).

## At a glance

- **Five subjects:** Ether (truth) · Essence (flow) · Entity (behaviour), joined by **Manifest**, described by **Phantasm**.
- **CLI:** an app is a **runite** (a file named `cast`); commands are **casts**, options are **spells**.
- **Built-in runites:** Awakening, the main hall (`rune`), Grimoire, Reliquary, Sentinel — in `@runite/`.
- **Modes:** *The Evolution of Eidos* (runes of your own) · *The Federation of Fides* (your own reliquary) · *The Liberation of Forte* (portable runtimes).
- **Distribution:** seal a runite into a `.rune` **relic** and share it through a reliquary (see [reliquary](../reliquary/README.md)).
- **Version:** the footer `Version=` is counted from every rune's Phantasm version — it is the release tag.

## Working on this realm

| Repo | What it is |
|---|---|
| [`devneet-id/rune`](https://github.com/devneet-id/rune) | the product — default branch `1.x`; issues live here |
| [`devneet-id/rune-dev`](https://github.com/devneet-id/rune-dev) | the workshop — `scenario/` (one runite per scenario, with its trial) and `exploration/` (the modes) |
| [`devneet-id/rune-skill`](https://github.com/devneet-id/rune-skill) | what an agent needs to *use* Rune — not written yet |

**Clone and initialise** — side by side, rune-dev takes Rune from `../rune`:
```bash
git clone https://github.com/devneet-id/rune.git
git clone https://github.com/devneet-id/rune-dev.git
cd rune-dev
composer dump-autoload
php cast scenario --here
```
No `composer require`, no lock file: `dump-autoload` only writes the autoloader. Every scenario must pass.

**Test an agent's branch** — the agent names it in its pull requests (one in `rune`, its scenario in `rune-dev`):
```bash
cd rune && git fetch origin && git checkout <branch> && git pull
cd ../rune-dev && git fetch origin && git checkout <branch> && git pull
php cast scenario --here
```
A new scenario must fail on `1.x` and pass on the branch; the agent's pull request says the counts. Then merge or send it back, go back to `1.x` / `main`, `git pull`, `git branch -d <branch>`.

Building something with Rune? Keep a `JOURNEY.md` and share it — see [covenant/journey.md](../../covenant/journey.md).

New here? Start with the [Paradigm](paradigm.md), then [Act 0](acts/0-the-void/README.md). Looking something up? Go to [Look it up](#look-it-up).

---

**Next →** [chronicle/README.md](../../chronicle/README.md) — the track record. Go deeper into this realm's Acts and pages when the work needs it.
