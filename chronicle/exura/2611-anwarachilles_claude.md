(upcoming)
- Fix in exuracss: tinted cards (`card="NAME:N"`) always use fixed-light text — unreadable light tints on a light page
- Rune: `aether_exit()` exits with a bare `exit` — a runite always returns 0; propose an issue in devneet-id/rune

_Times are UTC._

---
## 18

#### 15:45 - exura-dev fetches Exura with `php exura`
anwarachilles opened `main` with a new runite, `exura`, that fetches exuracss, exurajs and exuraphp from the CDN (a tag or a branch) and dropped the GitHub Actions workflow — no CI. Reshaped the workbench around it: no submodules; `playground/` → `src/`, the fetched files in `src/vessel/` (not committed, served as `/vessel/`); `cast` is development only — `serve` and `test`. 37 tests pass (1 todo). devneet-id/exura-dev#1.

#### 15:22 - exura-dev runs on Rune
At anwarachilles' request the workbench CLI became a runite: `php dev` → `php cast` (`setup`, `serve` through Specter's devserver, `build --css --js --php`, `test --php --js --css --integration`, `size`, `status`), on devneet/rune 1.21.117. Found that a runite always exits 0 (`aether_exit()` ends with a bare `exit`); the `cast` sets the real code from a shutdown function so CI can fail. `serve` now refuses to start when a submodule is empty — anwarachilles' playground had loaded without exuracss, most likely from an empty `packages/`.

#### 14:17 - exura-dev: the workbench of the series
With anwarachilles, designed and built devneet-id/exura-dev as the workshop of the Exura realm (branch `claude/jolly-cerf-fe39bl`):
- `packages/` — exuracss, exurajs, exuraphp as submodules (1.x); the packages stay the source of truth and free of dependencies.
- `php dev` — `setup`, `serve`, `build` (calls each package's `cast`), `test`, `size` (gzip budget in `exura-dev.json`), `status`.
- `playground/` — a page per exuracss module (incl. color balancing and the new clip grammar `e: a: ef:`), exurajs demos, the exuraphp API, and `apps/notes` combining the three.
- `tests/` — node:test + Playwright: 37 tests (php over HTTP, js and css in the browser, notes end to end), all passing; one `todo`.

Findings: exuracss 1.1.0 tints keep `--color-fixed-light` text (contrast 1.08 on `primary:1`, light page); `* { transition: all .05s }` animates every element; `php cast build` on Linux drops the blank lines of exurajs `dist/exura.js`.
