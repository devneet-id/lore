(upcoming)
- Waiting on anwarachilles: test and merge configure — devneet-id/exurajs#4 and devneet-id/exuraphp#10 merged; scenarios in devneet-id/exura-dev#7; then the release decision
- Worked only when asked: devneet-id/exuracss#4–#6, devneet-id/exurajs#2, devneet-id/exuraphp#3–#8 (findings)
- Tint fix: move AnwarAchilles/exuracss#1 to a branch of devneet-id/exuracss for devneet-id/exuracss#4, then close the fork PR
- Waiting on anwarachilles: devneet-id/exura#1 links follow the flat realm (updated)
- To do with anwarachilles: guide him once through *Working on this realm* (clone, `php exura`, test a branch) and record it
- Waiting on anwarachilles: review/merge devneet-id/exura#1 (removes the docs moved to lore)
- Realm docs follow the release (lore#27): each exura PR carries a *Lore* line; `realms/exura/` is updated after a release
- Rune: `aether_exit()` exits with a bare `exit` — a runite always returns 0; for the rune division (devneet-id/rune is outside this session)

_Times are UTC._

---

#### 10:02 - devneet-id/exuraphp#10 merged
anwarachilles merged devneet-id/exuraphp#10 into `1.x` (closes devneet-id/exuraphp#9). `configure()` is now in both packages, not released. Still open: devneet-id/exura-dev#7 (the scenarios), devneet-id/exura#1.

#### 09:30 - devneet-id/exurajs#4 merged
anwarachilles merged devneet-id/exurajs#4 into `1.x` (closes devneet-id/exurajs#3). Not released: no version bump, no tag. Still open: devneet-id/exuraphp#10, devneet-id/exura-dev#7, devneet-id/exura#1.

#### 09:22 - configure() landed for review: exurajs#4, exuraphp#10, exura-dev#7
- **devneet-id/exurajs#4** (Fixes #3): `Exura.configure()` rebases the settings (`environment()` kept as the old name); **development is the default** — banner once, `module x() ✓`, warnings for a name used twice, a name like a global, a missing element / watch target; **production** writes nothing, catches errors in effects / router / watch, cancels uncaught errors and rejected promises, hands each to `onError`. dist rebuilt, no version bump.
- **devneet-id/exuraphp#10** (Fixes #9): `Exura::configure()`; development keeps the trace, now with `time`; production drops the trace and keeps only an error message (`Internal Server Error` for a 5xx).
- **devneet-id/exura-dev#7**: `exurajs-mode` 12/12 ✓, `exuraphp-mode` 11/11 ✓ with the PRs' dist; on `1.x` 1 ✗ / 8 ✗. Production really hides errors: no `Runtime.exceptionThrown` in DevTools (control: development shows them).
- Seen, not changed: the trace's `route` and the fallback's `error.route` include the script folder (`api/hello`) while matching strips it; JSON stays pretty in both modes (undecided).
- Each PR carries a *Lore* line; `realms/exura/` is updated after the release.

#### 09:18 - Starting configure() in exurajs and exuraphp
anwarachilles: work exura configure, in exurajs and exuraphp — devneet-id/exurajs#3, devneet-id/exuraphp#9. **He decided:**
- exurajs production hides every error by **catching** it: `error` / `unhandledrejection` with `preventDefault`, `try/catch` around exurajs' own callbacks, optional `configure({ onError })` — not `setTimeout` + `console.clear()`.
- Development has **no** `console.clear()` before the banner.
Plan: a branch in each package (fix in `src/`, `php cast build --min=true`, no version bump — that is the release), and the checks per mode in exura-dev `exurajs-mode` / `exuraphp-mode` (on #7's branch).
