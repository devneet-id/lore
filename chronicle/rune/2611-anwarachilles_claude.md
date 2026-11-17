(upcoming)
- Run every trial of rune-dev against rune v1.21.120 and refresh `scenario/README.md` status
- Work from issues in devneet-id/rune; propose turning the Known Issues list into issues

_Times are UTC._

---
## 17

#### 17:45 - Chronicle: human and AI track record
Clarified with anwarachilles: the chronicle is the track record of humans and AI developing together (for anyone joining the IT division later), not a stand-in for issues. AI logs in `<YYMM>-<human>_claude.md`. Updated `chronicle/README.md`, `README.md`, `llms.txt`, `realms/README.md`; started this file.

#### 17:40 - Work is issue-based
Agreed: development is planned and noted in issues of devneet-id/rune; PRs close them; chronicle links them. No GitHub Actions CI — trials run whenever a scenario or change comes in.

#### 17:31 - rune-dev README
Wrote the root README (rune = product, rune-dev = workshop of the rune realm, lore = DEVNEET knowledge; the cycle of a change) and replaced the `exploration/` stub (one runite per mode). devneet-id/rune-dev#2.

#### 17:20 - rune-dev joined; `.echoes/` untracked
Cloned devneet-id/rune-dev (the workshop). Untracked 41 `.echoes/` files from the scenarios and ignored `.echoes/`. devneet-id/rune-dev#1 (merged).

#### 15:45 - Studied lore and rune
Read the paradigm, laws, decisions, versioning, modes and the rune source (Aether, Chanter, Keeper, runites). Found lore behind the code: footer 1.21.120 vs 1.21.117 in Versioning; `chanter_cast_has()` and `weaver_item()` already fixed in code but still listed in Known Issues. (Both since corrected by anwarachilles: lore updated to v1.21.120.)
