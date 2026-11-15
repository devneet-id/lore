# Reliquary — Reference

The technical detail of Reliquary. The narrative lives in [../lore/](../lore/).

> **Skeleton.** Fill these from the repo; detailed drafts already exist and can be dropped in.

## Planned pages

- `model.md` — the federated design, the Docker analogy, the page (GitHub Pages).
- `commands.md` — every `relic`, `nexus`, and website command with spells.
- `records.md` — `relic.json` / `nexus.json` formats with examples.
- `laws.md` — the five Laws of the Reliquary.

## The five Laws (invariants)

1. A name is its repo (`<owner>/<repo>`); a reliquary lists only its owner's repos.
2. A version never changes — same version + different seal is refused.
3. The seal is the sha256 of the `.rune` when listed.
4. A version from `main` is pinned to its commit.
5. A fork that has not initiated is silent.

## Requirements

PHP 8.1+ with `curl` (or `allow_url_fopen`), Composer, a GitHub account. Rune `^1.12` (restore needs 1.20+). `GITHUB_TOKEN` raises the API limit (60 → 5,000 req/hr).
