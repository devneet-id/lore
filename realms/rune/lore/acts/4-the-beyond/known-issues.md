# Known Issues

> What is still open — and where to start.

Rune is not finished. The work itself lives in the **[issues of devneet-id/rune](https://github.com/devneet-id/rune/issues)** — each bug there names its file and the rune-dev trial that proves it. This page keeps the short list. Pick one, write its trial, fix it — see [Contributing](contributing.md).

## Bugs
Tracked as issues, e.g. Chanter flags (devneet-id/rune#17, #22) and Sentinel and Keeper (devneet-id/rune#20).

Fixed in 1.21.133 (devneet-id/rune#42): `--runite-remove` refuses an unknown rune or one not in the runite (#21) · legacy `_arise()` hooks gone, true `#NOTE`s, Minister marked `VOID`, the Grimoire header and composer links (#28).

Fixed in 1.21.126 (devneet-id/rune#40): a warning silenced with `@` is no longer a glitch (#16) · a glitch exits with code 1 (#19) · a hidden non-blocking Specter cast no longer blocks on Linux (#18).

Fixed in 1.21.123 (devneet-id/rune#38): shard paths with `\` on Windows — the cause of the Exura relics that opened oddly on Linux; an older relic's `\` is now read as `/` (#37) · `weaver_min_php()` changing strings (#33) · Crafter writing an empty file when no template fits (#34) · `ENCRYPTION gzip` (#35) · a failed spark leaking into the next build (#36).

## Sentinel
| Issue | What happens |
|---|---|
| `--runite-insert=Keeper` adds no `begin()`/`end()` (devneet-id/rune#20) | Without `Keeper::begin()` nothing is saved, yet `Keeper::item()` returns `true`. Add them by hand. |

## Planned work
| Task | State | Plan |
|---|---|---|
| Altar → Exura | postponed | Altar still uses Nirvana, runs `start cmd /k` (Windows only) with unsanitised POST input, and old paths (`.echoes/rune.php/`, `shards/`). See [Altar](altar.md). |

## Not tested yet
- Specter on macOS (Terminal via `osascript`) — written, never run on a Mac.
- Minister against a real familiar (URL + token).
- Windows-only paths (`cls`, `start cmd`) are written by `PHP_OS_FAMILY`; the trials run on Linux.
