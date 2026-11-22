# Reliquary

**Repo:** `devneet-id/reliquary` · **Language:** PHP (on Rune) · **License:** MIT

> Forged through Rune. Kept by its people. The **Federated Relic Registry** for Rune.

A **relic** (`.rune`) is a sealed snapshot of a runite (code + echoes + shards) — like a Docker image. A reliquary records where each relic rests and its **seal (sha256)**. There is **no central registry**: the repo *is* the registry, federated by fork. Reliquary ships **no release**: what is on `main` is what every reliquary takes with `php hall sync`.

## How this realm is laid out

One page for now: this README. Pages are added at the realm's root, named by what they hold, as the work lands (no release: the realm follows `main`).

## The Federation of Fides

*Fides* is trust; *foedus*, the pact at the root of *federation*, shares its root. Every vendor keeps its own reliquary, and the seals keep the trust between them. A reliquary keeps no relic — it only remembers where each one rests, and the seal it bore when it was listed.

## At a glance

- Two records: `relic.json` (this owner's relics) + `nexus.json` (links to forks).
- Runites: `php relic …`, `php nexus …`, `php hall …`, and the page (`php cast build/serve/watch/start/publish`).
- Every cast that writes a record commits **that record only** and pushes it; `--local` only saves it.
- Each reliquary publishes a page via GitHub Pages that reads its records live.

## The six Laws of the Reliquary

1. **A relic is a `.rune`.** It is named `<vendor>/<repo>/<relic>`, lowercase; a reliquary lists only its owner's own repos.
2. **A version never changes.** The same version with another seal is refused; a change is a new version.
3. **The seal is the sha256** of the `.rune` when it was listed.
4. **A version from `main` is pinned to its commit.**
5. **A fork that has not initiated is silent.**
6. **Your records and your page are yours.** `hall sync` takes the runites of the parent, never its records or its page.

## Working on this realm

| Repo | What it is |
|---|---|
| [`devneet-id/reliquary`](https://github.com/devneet-id/reliquary) | the project: the first reliquary — the runites (`relic`, `nexus`, `hall`, `cast`, `exura`), its records (`relic.json`, `nexus.json`) and its page (`index.html`, `cast.rune`); default branch `main`; its issues live here |
| [`devneet-id/relic-cli`](https://github.com/devneet-id/relic-cli) · [`relic-web`](https://github.com/devneet-id/relic-web) · [`relic-web-exura`](https://github.com/devneet-id/relic-web-exura) · [`relic-web-exura-vercel`](https://github.com/devneet-id/relic-web-exura-vercel) | the relics `devneet-id/reliquary` lists — each repo carries its own `.rune` files |
| [`AnwarAchilles/reliquary`](https://github.com/AnwarAchilles/reliquary) | a fork, linked in `nexus.json`: the test reliquary — a change to `hall sync`, `nexus` or the page is tried here before `devneet-id/reliquary` |
| [`devneet-id/reliquary-skill`](https://github.com/devneet-id/reliquary-skill) | what an agent needs to *use* Reliquary — not written yet |

There is **no `-dev` repo**: a change is developed in a clone of `devneet-id/reliquary`, tried with `--local` (nothing is pushed), and — when it touches the federation — in the test fork.

Requirements: **PHP 8.1+** with `curl` (or `allow_url_fopen`), **Composer**, a GitHub account. `GITHUB_TOKEN` raises the API limit (60 → 5,000 req/hr).

**Clone and initialise:**
```bash
git clone https://github.com/devneet-id/reliquary.git
cd reliquary
composer install
php hall analyze
```
`hall analyze` only reads: the records, the name against `git remote origin`, every seal — `9 valid, 0 warning(s), 0 invalid` today. To work on the page, open its source: `php cast reliquary --relic-runite` (`cast.rune` → `cast` + `src/`), then `php cast start` (http://127.0.0.1:8000).

**Test an agent's branch** — the agent names it in its pull request, with the casts to run:
```bash
git fetch origin && git checkout <branch> && git pull
composer install
php hall analyze
php relic register --repo=<repo>/<relic> --tag=<tag> --local   # any cast that writes: always --local
```
- **Always `--local`** on a cast that writes (`relic`, `nexus`, `hall sync`): without it, the cast commits and pushes the record to the branch you are on.
- `relic` and `nexus` take `--api=<url>` and `--raw=<url>` to point at a fake GitHub, for a test that must not touch GitHub at all.
- Throw the test records away afterwards: `git checkout -- relic.json nexus.json`.
- Then merge or send it back, go back to `main`, `git pull`, `git branch -d <branch>`. **A merge is what every fork takes** on its next `hall sync` — there is no release in between.

Building something with Reliquary? Keep a `JOURNEY.md` and share it — see [covenant/journey.md](../../covenant/journey.md).

---

**Next →** members: [chronicle/README.md](../../chronicle/README.md) — the track record. Users: this realm is the end of your path.
