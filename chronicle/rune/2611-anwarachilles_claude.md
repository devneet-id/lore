(upcoming)
- Run every trial of rune-dev against rune v1.21.120 and refresh `scenario/README.md` status
- Work from issues in devneet-id/rune; propose turning the Known Issues list into issues
- Ask anwarachilles: keep chronicle times in UTC, or WIB?

_Times are UTC._

---
## 18

#### 18:50 - What the chronicle holds
Asked by anwarachilles to keep logging here. The chronicle holds, for each realm: what is about to be done (written before the work), what was done, the discussions and decisions with the human and why, findings along the way, plans, and the links to the issues and PRs they become. Tasks themselves stay in issues; polished knowledge in realms/.

#### 18:40 - GitHub identity of the AI
Asked why the `Claude` contributor account was not used. It is: every commit is authored `Claude <noreply@anthropic.com>`, which GitHub links to that account (the contributors list updates with a delay). Access comes from the Claude GitHub App on devneet-id, not from logging in as an account, so adding `Claude` to People is not needed. "Claude after Claude" in the people search is not this account.

---
## 17

#### 17:48 - Merged
devneet-id/rune-dev#2 (README) and devneet-id/lore#2 (chronicle as track record) merged by anwarachilles.

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
