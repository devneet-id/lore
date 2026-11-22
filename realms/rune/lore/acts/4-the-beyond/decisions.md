# Decisions

> Why things are the way they are.

Old names still hide in comments, Altar and old relics. When you meet one, this page tells you what it became and why.

## Old names → now
| Before | Now | Why |
|---|---|---|
| main file `rune.php` | `cast` | A runite is a CLI app; `php cast greet` reads like speech. Leftovers: Altar (`.echoes/rune.php/`), `ai.txt`. |
| `arise()` / `_arise()` / `_aether_end()` | `begin()` / `end()` | A pair that opens and closes the flow. The `_arise` hooks are gone from the origin runes (1.21.133) and from the `--runic-create` templates (1.21.138). |
| `@ethereal/`, `@liberations/`, `<repo>/@bindrune/`, then `@liberation/` | `@evolution/` | Many names meant your runes were missing from Grimoire and the footer. One name now, singular like every mode folder. |
| liberation mode (runes of your own) | evolution mode — *The Evolution of Eidos* | Making runes is rebuilding Rune's form (*eidos*). *Liberation* now means freedom from the host's PHP: a runtime of your own. |
| `@bindrune/` (and `@bindrune/chanter/`) | `@runite/` | The built-in runites are runites; one flat folder, no special case when listing runes. |
| artefact, `artefact` cast | relic, `reliquary` cast | *Artifact* is a common word with the same idea; a *relic* is what a *reliquary* keeps. Old `.rune` files with an `ARTEFACT` block still open. |
| `--invoke`, `--create-rune`, `--phantasm-fix`, `--rune` … | `--runite-insert`, `--runic-create`, `--phantasm-repair`, `--runic` … | Spells use system words (insert, create, list, repair…); lore words stay in the names of runites and things. Old spells answer with the new name. |
| starter templates in the package | relics in `devneet-id/reliquary` | Any relic online can be a starting point; the package stays small. |
| Nirvana (CSS/JS/PHP) | Exura | Rename of the web toolkit. Altar still uses Nirvana. |
| `shards/` folder | `shard.json` + relic | Shards travel inside the `.rune`; the map lives in `shard.json`. |
| `chipher()` | `cipher()` | A typo fixed. |
| `<runite>.json` echoes | `rune.json` | `cast.json` belonged to Specter; one fixed name avoids clashes. |

## Why not React or Tailwind → Exura
Integrating React and Tailwind was tried. Both are ecosystems of their own, and Rune stopped being simple. Exura was born instead: a small toolkit that fits after [Crafter](../2-understanding-its-flow/exura.md).

## Why VOID, BETA, EXIST
VOID already covers both roles: a function held back because it is dangerous, and a function voided until it is finished. DEVELOPMENT was a search for VOID's opposite — that opposite is **EXIST**: whole and stable. BETA sits between. "Development" means developing a rune, not a mark, so DEVELOPMENT is dropped; DEPRECATED is not a mark either.

## Why evolution never replaces an origin rune
Before, the loader for your runes was prepended: a full copy of `Whisper/` among them silently replaced the real Whisper. Now the loader is appended, origin names are refused, and the rule is: need another version → a new name.

## Why one package, not many
Runes are not split into many Composer packages. The origin runes stay together; growth happens through Evolution, not through an ecosystem of packages.

## Smaller decisions you will trip on
- `Chanter::spell('x', 'v')` is read on the **next** cast — the *respell* pattern, by design.
- `rune.json` stores only the repo folder name, never an absolute path.
- Relics store OS, release, version and architecture — never the computer name.
- `+` in spell values is kept (`--q=a+b` → `a+b`) `0` is a value, not "missing".
- `--runic-*` and `--phantasm-*` spells run only in evolution mode; `--runtime-*` only in liberation mode.

## Decided since
- **Whole-number versions** — a version is `<major>.<minor>` read as whole numbers, so `1.10` comes after `1.9`. See [Versioning](versioning.md).
- **`.echoes` next to the runite** — `AETHER_REPO` is the runite's own folder, so `.echoes`, the mode folders and shards stay with it, wherever it is cast from.
- **Modes are unlocked by Sentinel** — `sentinel --evolution` / `--federation` / `--liberation` write one line under `require`; there is no toggle, so closing a mode is a deliberate edit.
- **Mode folders go into git** — `@evolution/`, `@federation/` and `@liberation/` belong to the project; `sentinel --gitignore` hides only `vendor/` and every `.echoes/`.
- **Federation without an argument** — `Rune\Ethereal::federation()` only marks the mode; your reliquary lives in `@federation/federation.json` (`reliquary --initiate`), not in the runite.
- **A required spell in `arg`, an optional one in `echo`** — every built-in runite writes its casts this way.
- **Shards only through `Keeper::shard()`** — Forger no longer adds every file it reads or writes; a build calls `Crafter::spark()` and then a `store` cast where you set the shards.
- **Crafter reads only the seed's `LANGUAGE`** — other files and folders are skipped (`Skipped=<n>`), never read.
- **The caption of the highest mode wins** — Liberation > Federation > Evolution > none.
- **`AETHER_VERSION` 1.12** — raised with the mode change of v1.21.117.
