# Glossary
 
The shared, lore-driven vocabulary of DEVNEET. These names are load-bearing — they map to real constructs across the realms. Read this before any code. Grouped by realm; everything ultimately centers on Rune. Rune's complete glossary lives in [realms/rune/reference/glossary.md](realms/rune/reference/glossary.md).
 
## Shared
 
- **DEVNEET** — the open developer community (Indonesia) behind these projects.
- **realm** — one project in the ecosystem (rune, reliquary, exura). Nodes on the atlas.
- **lore** — the body of knowledge/story of a thing (also the name of this repo, and of each realm's narrative folder).
- **codex** — _(coming soon)_ a separate store of small reusable code (e.g. cast-build snippets).
- **round** — one part of a single problem that a human split into several passes, named `part 1/3 of #12`. Never a set of issues, never numbered across the project, never a release trigger. See [covenant/workflow.md](covenant/workflow.md).
## Rune
 
- **Rune** — a modular unit of the framework; "something not yet known" until invoked.
- **Ethereal** — the bootstrap surface (`Rune\Ethereal`): awakening and the three modes.
- **Ether** — truth that does not change but always has meaning (constants / config).
- **Essence** — what changes over time (state / flow).
- **Entity** — what makes other things change (behaviour / logic). Entities call other entities — this is how runes interconnect.
- **Manifest** — connects things so they work together; forwards calls to entities.
- **Phantasm** — the living contract that replaces Reflection (version, user, note, mark, link, node).
- **Awakening** — starting from anywhere (`Ethereal::awakening()`).
- **Evolution** — creating your own runes beside the origin ones (`@evolution/`); caption *The Evolution of Eidos*.
- **Federation** — keeping your own reliquary and its relics (`@federation/`); caption *The Federation of Fides*.
- **Liberation** — keeping **portable runtimes** next to the runite (`@liberation/<runtime>@<version>/`: PHP, Node, Python…; PHP the first); caption *The Liberation of Forte*. Running several runtimes will be carried by Minister (still being designed).
- **Echoes** — persisted memory in `.echoes/` (kept by Keeper).
- **Arcane** — the phased process log recorded by Aether.
- **Runite (built-in)** — the runites Rune carries in `@runite/`: awakening, rune (the main hall), grimoire, reliquary, sentinel. Once called *Bindrune*.
- **Grimoire** — live system inspection (`php cast grimoire`).
- **Sentinel** — the guard of a runite: unlocks the modes, inserts/removes runes, shapes your own runes, keeps portable runtimes.
- **cast** — the app file, and a registered command.
- **runite** — a `cast` app (any project built on Rune).
- **spell** — a command option (`--name` or `--name=value`).
- **echo** — a note on a cast; also Whisper's styled output.
- **zero trust** — a guarded execution mode for breaking changes.
## Reliquary
 
- **Artefact** — the old name of a relic (older `.rune` files carry an `ARTEFACT` block).
- **Relic** — a `.rune` file: a sealed snapshot of a runite (code + echoes + shards). Like a Docker image.
- **Shard** — a file carried by a relic, listed with `Keeper::shard()` (nothing becomes a shard on its own).
- **Reliquary** — a federated registry recording where relics rest and their seals.
- **Seal** — the sha256 of a `.rune` at the time it was listed.
- **Nexus** — the map of a reliquary's forks (`nexus.json`).
- **Fides / Foedus** — trust / pact; the root of the federation idea.
## Exura
 
- **Exura** — the minimalist, semantic-first framework series; independent of Rune.
- **exuraphp** — the backend micro-framework (PHP).
- **exurajs** — the frontend micro-framework (JavaScript).
- **exuracss** — the semantic-first CSS framework.
- **semantic-first** — style and structure follow meaning (semantic HTML), not utility classes.
## Quick analogies
 
- Rune ≈ a lazy, modular PHP foundation (runes instead of services, no bootstrap).
- Relic ≈ Docker image; Reliquary ≈ a federated Docker Hub with no central server.
- Phantasm ≈ Reflection, but declared and alive.
- Grimoire ≈ a live, self-describing inspector.

---

**Next →** [atlas/](atlas/README.md) — the maps.
