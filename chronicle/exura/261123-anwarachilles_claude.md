(upcoming)
- Waiting on anwarachilles: review/merge devneet-id/exura-dev#7 (mode scenarios use `configure()`)
- In progress: devneet-id/exurajs#3, devneet-id/exuraphp#9 (configure / mode)
- Worked only when asked: devneet-id/exuracss#4–#6, devneet-id/exurajs#2, devneet-id/exuraphp#3–#8 (findings)
- Tint fix: move AnwarAchilles/exuracss#1 to a branch of devneet-id/exuracss for devneet-id/exuracss#4, then close the fork PR
- Waiting on anwarachilles: devneet-id/exura#1 links follow the flat realm (updated)
- To do with anwarachilles: guide him once through *Working on this realm* (clone, `php exura`, test a branch) and record it
- Waiting on anwarachilles: review/merge devneet-id/exura#1 (removes the docs moved to lore)
- Realm docs follow the release (lore#27): each exura PR carries a *Lore* line; `realms/exura/` is updated after a release
- Rune: `aether_exit()` exits with a bare `exit` — a runite always returns 0; for the rune division (devneet-id/rune is outside this session)

_Times are UTC._

---

#### 09:18 - Starting configure() in exurajs and exuraphp
anwarachilles: work exura configure, in exurajs and exuraphp — devneet-id/exurajs#3, devneet-id/exuraphp#9. **He decided:**
- exurajs production hides every error by **catching** it: `error` / `unhandledrejection` with `preventDefault`, `try/catch` around exurajs' own callbacks, optional `configure({ onError })` — not `setTimeout` + `console.clear()`.
- Development has **no** `console.clear()` before the banner.
Plan: a branch in each package (fix in `src/`, `php cast build --min=true`, no version bump — that is the release), and the checks per mode in exura-dev `exurajs-mode` / `exuraphp-mode` (on #7's branch).
