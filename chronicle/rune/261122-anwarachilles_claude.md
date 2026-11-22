(upcoming)
- Ask: links of dependent runes lag after a partial `--phantasm-repair` — repair all runes before a release?
- In progress: rune#27 flock · Next: #26 Specter upgrade (allowed; reviewed after) · #41 catalog · #31 rest (Minister, Federation, Liberation)
- Waiting on anwarachilles: #32's last item (engraving: a runite as a server service) — still wanted?
- Release: after the issues are clean (anwarachilles' no, 20 · 14:51)
- Planned (to design with anwarachilles, then file): redesign `Whisper::flash` as a real loader → CLI loaders on it
- Waiting on anwarachilles: the design of Minister (it will carry Liberation's runtimes; `@liberation/cast.bat` / `cast.sh` anchored to the root `.echoes/`) — still being studied
- Realm docs: from now on they follow the release (lore#27) — each rune PR carries a *Lore* line. The realm is already at 1.21.140 (updated before the law; latest tag 1.21.117) — proposed to leave it, the next release aligns it.

_Times are UTC._

---

#### 11:42 - rune#27 decided: flock as an option
anwarachilles: **agreed** to the dissection — essence `$KEEPER_LOCK` (`false` default / `true` all items / a list of item names); read-modify-write through a callback `Keeper::item('x', fn($old) => $new)` that always locks; a lock wait with a limit, and past it a **glitch** naming the item. He gave no number: I take **5 s**, set by the essence `$KEEPER_LOCK_WAIT`. Trial first in rune-dev (concurrent processes), then rune, Phantasm; the PR carries a *Lore* line (docs after the release).

#### 11:39 - Daily files; realm docs follow the release
*Written by Claude, with anwarachilles.* anwarachilles asked to read the latest lore and, after my short report, said yes to the two `laws-update` issues for rune:
- **lore#32** — daily chronicle files from today: this file, `261122-anwarachilles_claude.md` (login from the GitHub account: `AnwarAchilles` → `anwarachilles`). Today's earlier entries (01:58 → 11:2x) stay in `2611-anwarachilles_claude.md` under `## 22`. Carry little: each session reads the lore issues, the latest day, the issue at hand.
- **lore#27** — realm docs follow the release: aligned `contributing.md` (a PR carries a *Lore* line, no lore in the same PR), `release.md` checklist (gather the *Lore* lines; the realm is updated after the release) and `keeping-the-lore.md`. From the next rune PR on: a *Lore* line, no realm edits until the release.
- Also read: `agent.md`, `operator.md`, `magistrate.md` (one seat decides the covenant), `appeal` / `hearing` issues. No `appeal` open for rune.
