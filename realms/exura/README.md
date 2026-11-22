# Exura

The Exura series: three super-light frameworks — **exuracss**, **exurajs**, **exuraphp** — each a single file, each usable on its own.

> One philosophy — minimalist, semantic-first, modern — across three layers of the stack.

Independent of Rune; shares DEVNEET's philosophy, and every package is shaped with a Rune runite (`cast`).

## This folder

- **[lore/](lore/README.md)** — the story: principles, the series together, the goal.
- **[reference/](reference/README.md)** — the documentation of each package: [exuracss](reference/exuracss/README.md) · [exurajs](reference/exurajs/README.md) · [exuraphp](reference/exuraphp/README.md).

## Working on this realm

| Repo | What it is |
|---|---|
| [`devneet-id/exuracss`](https://github.com/devneet-id/exuracss) | the CSS package — default branch `1.x`; `src/` → `dist/`; its issues live here |
| [`devneet-id/exurajs`](https://github.com/devneet-id/exurajs) | the JavaScript package — default branch `1.x`; its issues live here |
| [`devneet-id/exuraphp`](https://github.com/devneet-id/exuraphp) | the PHP package — default branch `1.x`; its issues live here |
| [`devneet-id/exura-dev`](https://github.com/devneet-id/exura-dev) | the workshop — `scenario/` (one possibility per folder, checked in the page) and `exploration/` (every component); fetches the packages into `core/` |
| [`devneet-id/exura`](https://github.com/devneet-id/exura) | the home of the series — the intro and the website; the docs now live here in lore |
| `devneet-id/exura-skill` | what an agent needs to *use* Exura — not written yet |

Requirements: **PHP 8.1+** and **Composer**.

**Clone and initialise** — the workshop is enough to start; it fetches the released files from the CDN:
```bash
git clone https://github.com/devneet-id/exura-dev.git
cd exura-dev
composer install
php exura setup --dist=core/ --tags=1.1.0 --install
php exura css --part=clip
php cast scenario
```
`php cast exploration` serves every component at http://localhost:8080. A package you work on is cloned beside it, and built with its own runite:
```bash
git clone https://github.com/devneet-id/exurajs.git
cd exurajs
composer install
php cast build --min=true
```

**Test an agent's branch** — the agent names it in its pull requests: one in the package, its scenario in `exura-dev`.
```bash
cd exura-dev && git fetch origin && git checkout <branch> && git pull
php exura setup --tags=<commit> --install
php cast scenario --name=<scenario>
```
`--tags` takes a tag, a branch without `/` (`1.x`), or a **commit**: an agent's branch is named `claude/…`, so take the head commit of its package pull request (`git rev-parse origin/<branch>` in the package). The agent builds `dist/` in that pull request, so the CDN serves it. The scenario that showed ✗ on the release must show ✓; the pull requests say what to look for. Then merge or send it back, go back to `1.x` / `main`, `git pull`, `git branch -d <branch>`.

**Release** — a package release is the release owner's yes ([covenant/release.md](../../covenant/release.md)): raise the version (`php cast version --up`), build, tag. Then `php exura setup --tags=<new>` in exura-dev, and this realm's [reference/](reference/README.md) follows the release.

Building something with Exura? Keep a `JOURNEY.md` and share it — see [covenant/journey.md](../../covenant/journey.md).

---

**Next →** [chronicle/README.md](../../chronicle/README.md) — the track record. Go deeper into this realm's `lore/` and `reference/` when the work needs it.
