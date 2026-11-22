# Rune

**Repo:** `devneet-id/rune` · **Package:** `devneet/rune` · **Language:** PHP (8.1+) · **License:** MIT · **Current:** v1.21.138 (untagged; last tag v1.21.117)

> A lore-driven, modular concept beneath PHP that responds to development rather than dictating it.

Rune is the foundation of the DEVNEET ecosystem — lightweight, lazy-loaded, process-based. No bootstrapping; each rune awakens only when invoked. Its documentation is alive: every rune describes itself in its **Phantasm**, read by the Grimoire, instead of Reflection.

## This folder

- **[lore/](lore/README.md)** — the story & teaching: the [paradigm](lore/paradigm.md), the five **Acts** (Act 0 · The Void → Act 4 · The Beyond), and the [engravings](lore/engravings/README.md) (recipes and traps).
- **[reference/](reference/README.md)** — the technical detail: the ten origin [runes](reference/runes/README.md), the built-in [runites](reference/runites/README.md), the [modes](reference/modes.md) and the Rune [glossary](reference/glossary.md).

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

New here? Start with [lore/](lore/README.md). Looking something up? Go to [reference/](reference/README.md).

---

**Next →** [chronicle/README.md](../../chronicle/README.md) — the track record. Go deeper into this realm's `lore/` and `reference/` when the work needs it.
