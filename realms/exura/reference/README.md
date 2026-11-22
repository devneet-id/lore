# Exura — Reference

The documentation of each package, for the released version. The story lives in [../lore/](../lore/README.md).

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

## Versioning

- **Semantic Versioning per package** — each package has its own `MAJOR.MINOR.PATCH`; they do not have to match.
- `fix` → patch · compatible `feat` → minor · anything that changes how you write markup or code → major (with a new `2.x` branch).
- The version lives in one place — the package's runite `cast` — and is written into `dist/` on build.

## Shaped with Rune

Every package is shaped with **[Rune](../../rune/README.md)** — a lore-driven, modular concept beneath PHP that responds to development rather than dictating it. Each package has a runite, `cast`, that turns `src/` into `dist/`:

```shell
composer install
php cast                       # all casts with notes
php cast build --min=true      # build dist/ (+ .min)
php cast version --up          # bump the version
```

## Notes

- Keep the three packages consistent in spirit; never make one require another.
- These pages describe **the released version**: they change after a release, not with each pull request ([covenant/workflow.md](../../../covenant/workflow.md#docs-follow-the-release)).

---

**Next →** [chronicle/README.md](../../../chronicle/README.md) — the track record.
