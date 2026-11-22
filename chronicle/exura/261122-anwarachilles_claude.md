(upcoming)
- Waiting on anwarachilles: review/merge devneet-id/exura-dev#7 (mode scenarios use `configure()`)
- Waiting on anwarachilles: how exurajs production hides every error — `setTimeout` 5 s + `console.clear()` (his idea) or catching them (`error` / `unhandledrejection` + `try/catch`, optional `onError`, my proposal); then update devneet-id/exurajs#3 and this chronicle
- Worked only when asked: devneet-id/exurajs#3, devneet-id/exuraphp#9 (mode); devneet-id/exuracss#4–#6, devneet-id/exurajs#2, devneet-id/exuraphp#3–#8 (findings)
- Tint fix: move AnwarAchilles/exuracss#1 to a branch of devneet-id/exuracss for devneet-id/exuracss#4, then close the fork PR
- To do with anwarachilles: `realms/exura/README.md` lacks *Working on this realm* (covenant/workflow.md); guide him once through exura-dev and the packages (clone, `php exura`, test a branch) and record it
- Realm docs follow the release (lore#27): each exura PR carries a *Lore* line; `realms/exura/` is updated after a release
- Rune: `aether_exit()` exits with a bare `exit` — a runite always returns 0; for the rune division (devneet-id/rune is outside this session)

_Times are UTC._

---

#### 11:46 - Daily files; realm docs follow the release; catching up
*Written by Claude, with anwarachilles.* Read the latest lore at anwarachilles' request (`agent.md`, `operator.md`, `magistrate.md`, the new chronicle and workflow laws). He said: prepare for the new lore.
- **lore#32** — daily files from today: this file, `261122-anwarachilles_claude.md` (login from the GitHub account: `AnwarAchilles` → `anwarachilles`). `2611-anwarachilles_claude.md` stays as history. Carry little: lore issues, the latest day, the issue at hand.
- **lore#27** — realm docs follow the release: no conflicting rule in `realms/exura/`, nor in the guides of exura-dev (README, WORKFLOW.md, AGENTS.md) and the three packages' READMEs. From the next exura PR on: a *Lore* line.
- No `appeal` issue open for exura.

**Not chronicled since 18 · 18:10** (written now, from the conversation):
- 18 Nov — anwarachilles pushed the drafts `scenario/exurajs-mode` and `scenario/exuraphp-mode` to exura-dev `main`; I gave them the scenario structure (shared CSS, `expect()`, the exuraphp `call()`/`show()` in an async block, guarded API call) → devneet-id/exura-dev#7 (draft).
- 18 Nov — **anwarachilles decided:** it is `configure()`, not `environment()` — it rebases the settings, and `mode: 'production'` removes the trace output. Renamed in #7; both scenarios show ✗ on 1.1.0 (no `configure()` yet).
- 18 Nov — **anwarachilles approved** the outputs per mode, and: development is the default; exurajs once had more development output (banner, service and module-clash tracking); exuraphp keeps leftovers of it. Plan written at 18 · 18:10; issues devneet-id/exurajs#3, devneet-id/exuraphp#9.
- 18 Nov — **anwarachilles decided:** exurajs production removes **every** error from the console. He proposed `setTimeout` 5 s then `console.clear()`; I proposed catching them instead (a clear only covers the first 5 s, wipes other logs, and is ignored with *Preserve log*). Not chosen yet.
- 18 Nov — **anwarachilles decided:** changes to lore go straight to `main` (now the law: covenant/changing-lore.md).
