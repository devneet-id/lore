(upcoming)
- Waiting on anwarachilles: review and merge the flat realm + *Working on this realm* (branch `claude/brave-feynman-x4977r`); then answer lore#40 and lore#42 with the commit on `main`
- Confirm with anwarachilles: the testing way written in *Working on this realm* — `--local` on every cast that writes, `AnwarAchilles/reliquary` as the test reliquary; then guide him through it once
- To settle with anwarachilles: do the relic repos (`relic-cli`, `relic-web`, `relic-web-exura`, `relic-web-exura-vercel`) belong to this division? `reliquary-skill` is empty — fill it now or later?
- Follow lore#33 (`-dev` repo → `dev` branch): it does not bind a realm without a `-dev` repo, but may shape ours
- Finding, for the rune division: `realms/rune/acts/4-the-beyond/reliquary.md` and `realms/rune/runites/reliquary.md` still show the old `relic.json` (`how-to-casting`, `<owner>/<repo>`)

_Times are UTC._

---

#### 19:03 - Realm flattened; Working on this realm written (lore#42, lore#40)
anwarachilles: the structure of `realms/` changed — fix it, and check the laws-update issues.
- **Laws-update:** lore#27, #32, #36 closed by the Magistrate (this division's first file landed through devneet-id/lore#38, merged by anwarachilles). Open for reliquary: **lore#40** (every realm is a project division; a `-dev` repo is one way — write *Working on this realm*) and **lore#42** (a realm is flat, one README). lore#29 closed by #40: reliquary is a project division.
- **lore#42:** `realms/reliquary/lore/` and `reference/` removed; their text merged into the one README (the Federation of Fides; the laws). No link in lore pointed at them; the README's links checked.
- **lore#40:** *Working on this realm* — `devneet-id/reliquary`, the relic repos it lists, `AnwarAchilles/reliquary` as the test reliquary, `reliquary-skill`; clone and initialise; test an agent's branch with `--local` (`--api`/`--raw` for a fake GitHub), throw the records away after. Run here before writing it: `composer install`, `php hall analyze` → 9 valid, 0 warning(s), 0 invalid (PHP 8.3, Rune 1.20.114).
- The finding of 13:39 fixed with it (no release: docs land with the work): the laws are six, named `<vendor>/<repo>/<relic>`.
- The testing way is my proposal from the runites' own spells — for anwarachilles to confirm.

#### 13:39 - The reliquary division begins; prepared for the latest lore
*Written by Claude, with anwarachilles.* The first entry of the reliquary division: no division kept this realm before.

**anwarachilles decided** (earlier today, written now from the conversation):
- He is the operator of this division; the chronicle handle is `anwarachilles` (GitHub login `AnwarAchilles`, from the account this session works under).
- The release owner of reliquary is **us** (anwarachilles with this agent).
- **Reliquary has no release: work goes straight to `main`.** He named it a hole in the laws — since closed by the Magistrate: `covenant/release.md` binds only projects that ship releases, and a division without releases updates its realm docs as its work lands.
- Our main work for now: **Working on this realm**.
- First, to know the flow of work in reliquary.

**Read** the whole reading path once, then the latest lore (`main` @ 4d896d3): `agent.md`, `operator.md`, `party.md`, `mandate/` (Magistrate, Architect), daily chronicle files, *Hand-overs and fresh starts*, appeals.
- **lore#27** — realm docs follow the release: nothing to change. No release here; `realms/reliquary/`, the `reliquary` README and `reliquary-skill` (empty) carry no rule that ties lore to a PR or a release.
- **lore#32** — daily files: this file is the division's first.
- **lore#36** — party and roles; start again from the latest chronicle: read. One agent here, so no party and no roles.
- No `appeal` issue open for reliquary. Drafts about us: lore#29, lore#33.
