(upcoming)
- Fix in exuracss: tinted cards (`card="NAME:N"`) always use fixed-light text — unreadable light tints on a light page
- Decide whether exura-dev keeps the GitHub Actions workflow (rune-dev chose none)
- `tools/docs-sync` (exura-dev → exura docs and `realms/exura/reference/`) and a release check

_Times are UTC._

---
## 18

#### 14:17 - exura-dev: the workbench of the series
With anwarachilles, designed and built devneet-id/exura-dev as the workshop of the Exura realm (branch `claude/jolly-cerf-fe39bl`):
- `packages/` — exuracss, exurajs, exuraphp as submodules (1.x); the packages stay the source of truth and free of dependencies.
- `php dev` — `setup`, `serve`, `build` (calls each package's `cast`), `test`, `size` (gzip budget in `exura-dev.json`), `status`.
- `playground/` — a page per exuracss module (incl. color balancing and the new clip grammar `e: a: ef:`), exurajs demos, the exuraphp API, and `apps/notes` combining the three.
- `tests/` — node:test + Playwright: 37 tests (php over HTTP, js and css in the browser, notes end to end), all passing; one `todo`.

Findings: exuracss 1.1.0 tints keep `--color-fixed-light` text (contrast 1.08 on `primary:1`, light page); `* { transition: all .05s }` animates every element; `php cast build` on Linux drops the blank lines of exurajs `dist/exura.js`.
