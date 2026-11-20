# Known Issues

> What is still open — and where to start.

Rune is not finished. The work itself lives in the **[issues of devneet-id/rune](https://github.com/devneet-id/rune/issues)** — each bug there names its file and the rune-dev trial that proves it. This page keeps the short list. Pick one, write its trial, fix it — see [Contributing](contributing.md).

## Bugs
Tracked as issues, e.g. Keeper and `@` (devneet-id/rune#16), Chanter flags (devneet-id/rune#17, #22), Specter on Linux (devneet-id/rune#18), the exit code (devneet-id/rune#19).

Fixed in 1.21.123 (devneet-id/rune#38): shard paths with `\` on Windows — the cause of the Exura relics that opened oddly on Linux; an older relic's `\` is now read as `/` (#37) · `weaver_min_php()` changing strings (#33) · Crafter writing an empty file when no template fits (#34) · `ENCRYPTION gzip` (#35) · a failed spark leaking into the next build (#36).

## Sentinel
| Issue | What happens |
|---|---|
| `--runite-insert=Keeper` adds no `begin()`/`end()` (devneet-id/rune#20) | Without `Keeper::begin()` nothing is saved, yet `Keeper::item()` returns `true`. Add them by hand. |
| `--runite-remove` does not validate the rune name (devneet-id/rune#21) | Unknown names say *Removed* though nothing changed, unlike `--runite-insert`. |

## Contract and text — devneet-id/rune#28
- Some `#NOTE`s are inaccurate: Keeper `begin`/`end`, generic `end()`, "placeholder" for `cipher()` / `forger()`. Fix the `#NOTE`, then `--phantasm-repair --mode=note`.
- `_arise()` hooks remain in the Manifests of Cipher, Forger, Specter, Weaver and Whisper — never called (legacy).
- Minister still has the mark `DEVELOPMENT`, which is not a mark (should be VOID, BETA or EXIST).
- The Grimoire header still says *Carefull use rune BETA/DEPRECATED* (`@runite/grimoire/header.txt`); DEPRECATED is not a mark.
- `composer.json` `support` links point to `github.com/devneet/rune`; the repo is `devneet-id/rune`.

## Planned work
| Task | State | Plan |
|---|---|---|
| Altar → Exura | postponed | Altar still uses Nirvana, runs `start cmd /k` (Windows only) with unsanitised POST input, and old paths (`.echoes/rune.php/`, `shards/`). See [Altar](altar.md). |

## Not tested yet
- Specter on macOS (Terminal via `osascript`) — written, never run on a Mac.
- Minister against a real familiar (URL + token).
- Windows-only paths (`cls`, `start cmd`) are written by `PHP_OS_FAMILY`; the trials run on Linux.
