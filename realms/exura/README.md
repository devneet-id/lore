# Exura

**Exura** is a series of three super-light frameworks — **exuracss** for CSS, **exurajs** for JavaScript, **exuraphp** for PHP. Each mirrors what a modern framework in its field can do, packed into **a single file** with no runtime dependencies and no build step for the user. Use one, two, or all three. These pages describe the released version.

> One philosophy — minimalist, semantic-first, modern — across three layers of the stack.

Independent of Rune; shares DEVNEET's philosophy, and every package is shaped with a Rune runite (`cast`).

## How the pages are laid out

- **This README** — the series, the story (principles, the series together, the goal), versioning, and *Working on this realm*.
- **Technical — one folder per package:** [exuracss/](exuracss/README.md) · [exurajs/](exurajs/README.md) · [exuraphp/](exuraphp/README.md). Each starts at its own README; the index is under [Documentation](#documentation).

## The series

| Package | Focus | Mirrors | Core idea | Size (min · gzip) | Repository |
|---|---|---|---|---|---|
| **exuracss** | semantic styling | a utility / component CSS framework | style with **attributes**: `button="primary"`, `flex="wrap"`, `size="w:1/2"` | ~215 KB · **~21 KB** | [devneet-id/exuracss](https://github.com/devneet-id/exuracss) |
| **exurajs** | modern reactive JavaScript | a reactive UI framework | `Exura.module()` → `state`, `effect`, `render` on an `<exura-name>` tag | ~5.5 KB · **~2 KB** | [devneet-id/exurajs](https://github.com/devneet-id/exurajs) |
| **exuraphp** | modern HTTP API endpoints | an *Express-like* API micro-framework | `Exura::module($method, $route, $fn)` → JSON | ~6 KB · **~2 KB** | [devneet-id/exuraphp](https://github.com/devneet-id/exuraphp) |

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devneet-id/exuracss@1.x/dist/exura.min.css">
<script src="https://cdn.jsdelivr.net/gh/devneet-id/exurajs@1.x/dist/exura.min.js"></script>
```
```php
require __DIR__ . '/exura.php';
```

## Documentation

| Package | Start here | Pages |
|---|---|---|
| **exuracss** | [exuracss/](exuracss/README.md) | [colors & dark mode](exuracss/color.md) · [layout](exuracss/layout.md) · [text](exuracss/text.md) · [ring](exuracss/ring.md) · [components](exuracss/components.md) · [clip icons](exuracss/clip.md) · [customize](exuracss/customize.md) |
| **exurajs** | [exurajs/](exurajs/README.md) | [module](exurajs/module.md) · [state, store & effect](exurajs/state.md) · [render & templates](exurajs/render.md) · [DOM helper](exurajs/dom.md) · [watch](exurajs/watch.md) · [router](exurajs/router.md) · [multi-page site](exurajs/pages.md) · [API](exurajs/api.md) |
| **exuraphp** | [exuraphp/](exuraphp/README.md) | [routing](exuraphp/routing.md) · [request](exuraphp/request.md) · [response](exuraphp/response.md) · [API](exuraphp/api.md) |

## The story

### Principles

- **Super light, still a framework.** Small is the point, but never at the cost of the abilities a developer expects from a framework.
- **One focus per package.** exuracss is about styling, exurajs about reactivity, exuraphp about HTTP. A feature belongs to the package whose focus it serves — nothing is forced across the series.
- **Readable by default.** Markup and code read like sentences: `flex="wrap j:between a:middle"`, `effect(() => render(), ['count'])`, `Exura::module('GET', 'user/*', …)`.
- **One file, no build for the user.** Drop in `dist/`, done.
- **Assist, not intrude.** Exura stays out of the developer's way.

#### Dark mode (exuracss)
exuracss has no separate dark palette. Every color has ten transparent shades (`primary-1` … `primary-10`) that blend with whatever is behind them, so the same markup works on light and dark. Dark mode is just:

```html
<body dark>
```

### The series together

A page styled by **exuracss**, made reactive by **exurajs**, talking to an API built with **exuraphp** — three single files.

**`api.php`**
```php
<?php
require __DIR__ . '/exura.php';

Exura::module('GET', 'notes', function() {
  return ['data' => [
    ['title' => 'Try Exura', 'done' => true],
    ['title' => 'Ship it',   'done' => false],
  ]];
});

Exura::fallback();   // nothing matched → 404 as JSON
```

**`index.html`**
```html
<body>
  <div container size="py:3">
    <exura-notes>
      <div card="primary:2" ring="b:full b:primary-5" size="p:2">
        <span text="h4 bold primary">{{left}} left of {{total}}</span>
        <ul list="ring:y" size="m:0 mt:1">{{{items}}}</ul>
      </div>
    </exura-notes>
    <button button="primary" size="mt:1" onclick="notes.load()">Reload</button>
  </div>

  <script>
    Exura.module(class notes {
      static async load() {
        const res = await fetch('api.php?/notes').then(r => r.json());
        const list = res.data;
        this.state.set('total', list.length);
        this.state.set('left', list.filter(n => !n.done).length);
        this.state.set('items', list.map(n => `<li>${n.done ? '✅' : '⬜'} ${Exura.escape(n.title)}</li>`).join(''));
      }
    });
    notes.effect(() => notes.render(), ['items']);
    notes.load();
  </script>
</body>
```

`{{key}}` is escaped, `{{{key}}}` inserts HTML; a module can be a `function` or a `class` with static methods (`this.state`, `this.render()`).

### Goal

The Exura series will:

- Let **CSS, JavaScript and PHP speak the same language** — readable, attribute-first, module-first.
- Grow **only where its focus grows**: on-demand CSS, list rendering for JS, route parameters for PHP.
- Become the foundation of **websites built with Exura** — starting with its own documentation.
- Stay **light**, and never become a burden for the developer.

Exura is here to assist — not to intrude.

## Versioning

- **Semantic Versioning per package** — each package has its own `MAJOR.MINOR.PATCH`; they do not have to match.
- `fix` → patch · compatible `feat` → minor · anything that changes how you write markup or code → major (with a new `2.x` branch).
- The version lives in one place — the package's runite `cast` — and is written into `dist/` on build.

## Shaped with Rune

Every package is shaped with **[Rune](../rune/README.md)** — a lore-driven, modular concept beneath PHP that responds to development rather than dictating it. Each package has a runite, `cast`, that turns `src/` into `dist/`:

```shell
composer install
php cast                       # all casts with notes
php cast build --min=true      # build dist/ (+ .min)
php cast version --up          # bump the version
```

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

**Release** — a package release is the release owner's yes ([covenant/release.md](../../covenant/release.md)): raise the version (`php cast version --up`), build, tag. Then `php exura setup --tags=<new>` in exura-dev, and this realm follows the release: the package folders here are updated from the PRs' *Lore* lines.

Building something with Exura? Keep a `JOURNEY.md` and share it — see [covenant/journey.md](../../covenant/journey.md).

---

**Next →** members: [chronicle/README.md](../../chronicle/README.md) — the track record; go into a package folder when the work needs it. Users: the package you use is the end of your path.
