(upcoming)
- Work the issues when anwarachilles asks: fix → version → release → `php exura setup --tags=<new>` → the scenarios turn ✓
- Tint fix: move AnwarAchilles/exuracss#1 to a branch of devneet-id/exuracss for devneet-id/exuracss#4, then close the fork PR
- Mode plan (18:10): worked when asked — devneet-id/exurajs#3, devneet-id/exuraphp#9; decide `console.clear()`
- Rune: `aether_exit()` exits with a bare `exit` — a runite always returns 0; propose an issue in devneet-id/rune

_Times are UTC._

---
## 18

#### 18:10 - Plan: development and production mode through configure()
Discussed with anwarachilles after he added the drafts `scenario/exurajs-mode` and `scenario/exuraphp-mode` to exura-dev (structure fixed in devneet-id/exura-dev#7).

**The idea.** `configure()` — not `environment()` — overrides ("rebases") the settings of each package; its main use is the mode. Both packages are in **development** by default; `mode: 'production'` removes the trace output.
- exurajs: `Exura.configure({ mode: 'production' })` — merges into `ExuraEnvironment.configure` (`mode`, `url`, …). Today `Exura.environment()` is an empty stub and the default is `production`.
- exuraphp: `Exura::configure(['mode' => 'production'])` — does not exist yet.

**History.** exurajs once had a development output, commented out since `init` (bece238): a banner `E X U R A - <version> //////` (`console.debug`), a note when a service already exists on `window`, and a tracking of clashing module names (recalled by anwarachilles, not in the history). exuraphp still carries leftovers of that development mode — the `"E X U R A - <version>"` trace in every answer — but incomplete.

**exurajs — development (default):**
```
E X U R A - 1.1.1 ////// development
EXURA · module cart()  ✓
⚠ EXURA · module cart() already exists — the new one replaces it
⚠ EXURA · service router() already exists on window — the page's own is kept
⚠ EXURA · ghost(): <exura-ghost> not found, render() does nothing
⚠ EXURA · shop(): watch target [more] not found
```
**exurajs — production:** a clean console (no banner, no warnings).

**exuraphp — development (default):** as today, completed — the trace `"E X U R A - <version>": { url, state, route, method, request, referer, notice }`, full errors (`type`, `code`, `message`, `file`, `line`), plus the request time.
```json
{ "E X U R A - 1.1.0": { "url": "…/api/", "state": 200, "route": "user/42", "method": [], "request": "GET", "referer": "" },
  "state": 200, "data": { "id": 42, "name": "Anwar" } }
```
**exuraphp — production:** no trace, no notices, no paths; an exception answers a general message.
```json
{ "state": 200, "data": { "id": 42, "name": "Anwar" } }
{ "state": 500, "error": { "message": "Internal Server Error" } }
{ "error": { "message": "Route not found" }, "state": 404 }
```
Approved by anwarachilles.

**Open.** `console.clear()` of the old banner: proposed to drop it (it wipes errors logged before Exura loads) — not decided yet.

**Proof.** exura-dev `exurajs-mode` / `exuraphp-mode` check that `configure()` exists (✗ on 1.1.0); their checks per mode come with the issues.

**Issues.** devneet-id/exurajs#3, devneet-id/exuraphp#9.

**Also.** anwarachilles: changes to lore go straight to `main` (no branch, no PR) — for lore only; every other repo keeps branches and draft PRs.

#### 17:27 - 10 issues filed in the package repos
New session on the devneet-id repositories (the last one could reach only the AnwarAchilles forks, whose issues are off). Checked each finding against `main`, then filed the drafts from exura-dev HANDOFF.md:
- exuracss: devneet-id/exuracss#4 (tint ink), devneet-id/exuracss#5 (red strong/em), devneet-id/exuracss#6 (`transition: all`)
- exurajs: devneet-id/exurajs#2 (CRLF/LF build diff)
- exuraphp: devneet-id/exuraphp#3 (JSON null), devneet-id/exuraphp#4 (big ints), devneet-id/exuraphp#5 (multipart PUT/PATCH), devneet-id/exuraphp#6 (scalar JSON + query → 500), devneet-id/exuraphp#7 (broken JSON → 400), devneet-id/exuraphp#8 (validation)

Not worked on yet — they wait until asked. The Rune finding stays upcoming: devneet-id/rune is outside this session.

#### 17:10 - Findings go to issues; method() probed
anwarachilles set the rule: a finding becomes an issue in the package's own repo (devneet-id/exuracss, exurajs, exuraphp), not a direct fix, and exura-dev holds no issues — recorded in exura-dev AGENTS.md. Probed `Exura::method()` over HTTP in a new scenario, `exuraphp-method-values` (devneet-id/exura-dev#6): JSON types hold; JSON null → default, big ints lose digits, multipart PUT unread, scalar JSON + query → empty 500, broken JSON read as a form. 10 issues drafted (3 exuracss, 1 exurajs, 6 exuraphp); not filed yet — the session can only reach the forks (AnwarAchilles/*), whose issues are disabled.

#### 16:25 - exura-dev reshaped like rune-dev
anwarachilles: exura-dev reads like docs, not a workshop — reshape it like rune-dev, without tests. Now `core/` (fetched by `php exura`), `exploration/` (every component of the three packages + `app/`, a complete notes CRUD and its API) and `scenario/` (16 standalone possibilities; exurajs/exuraphp ones check themselves in the page with ✓/✗). `php cast` serves one folder: `exploration`, `scenario --name`, `serve --path`. Tests and Playwright removed. Also seen: exuracss 1.1.0 paints every `strong`/`em` red. devneet-id/exura-dev#4.

#### 16:05 - exuracss: readable tints in light and dark
anwarachilles: "warnanya ngawur". Every `card="NAME:N"` used one fixed ink for all ten shades (contrast down to 1.0 in both modes). The exuracss build now picks the ink per tint and per page (light/dark) by WCAG contrast over the blended surface, as `--ink-NAME-N`; lowest contrast 1.0 → 4.1, +0.6KB gzip. AnwarAchilles/exuracss#1; the exura-dev test now covers all 70 tints × both modes (todo until release): devneet-id/exura-dev#2.

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
