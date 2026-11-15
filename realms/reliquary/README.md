# Reliquary

**Repo:** `devneet-id/reliquary` · **Language:** PHP (on Rune) · **License:** MIT

> Forged through Rune. Kept by its people. The **Federated Relic Registry** for Rune.

A **relic** (`.rune`) is a sealed snapshot of a runite (code + echoes + shards) — like a Docker image. A reliquary records where each relic rests and its **seal (sha256)**. There is **no central registry**: the repo *is* the registry, federated by fork.

## This folder

- **[lore/](lore/)** — the story: the federation idea, the "Federation of Fides".
- **[reference/](reference/)** — the technical detail: model, commands, records, laws.

## At a glance

- Two records: `relic.json` (this owner's relics) + `nexus.json` (links to forks).
- Commands: `php relic …`, `php nexus …`, website casts (`php cast build/serve/watch/start`).
- Each reliquary publishes a page via GitHub Pages that reads its records live.

See [reference/](reference/) for depth.
