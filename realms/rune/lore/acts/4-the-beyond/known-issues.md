# Known Issues

> What is still open — and where to start.

Rune is not finished. The work itself lives in the **[issues of devneet-id/rune](https://github.com/devneet-id/rune/issues)** — each bug there names its file and the rune-dev trial that proves it. This page keeps the short list. Pick one, write its trial, fix it — see [Contributing](contributing.md).

## Bugs
Tracked as issues, e.g. Specter souls (devneet-id/rune#46).

Fixed in 1.21.138 (devneet-id/rune#47): `--runic-create` writes no `_arise()` (#43) · `--runic-delete` takes the rune out of the runite (#45) · a spell value is read as given — a `%2F` on the command line stays (#22).

Fixed in 1.21.137 (devneet-id/rune#44): a bare flag is `true` — **breaking**, compare with `true`, not `'1'` (#17) · Sentinel writes `begin()` / `end()` for a rune with a flow at the `#sentinel-flow-*` markers (#20) · `Keeper::tolerate()` (#24) · `$AETHER_FOOTER` / `$WHISPER_COLOR` for output read by a machine (#25) · Awakening writes the `.gitignore` (#30).

Fixed in 1.21.133 (devneet-id/rune#42): `--runite-remove` refuses an unknown rune or one not in the runite (#21) · legacy `_arise()` hooks gone, true `#NOTE`s, Minister marked `VOID`, the Grimoire header and composer links (#28).

Fixed in 1.21.126 (devneet-id/rune#40): a warning silenced with `@` is no longer a glitch (#16) · a glitch exits with code 1 (#19) · a hidden non-blocking Specter cast no longer blocks on Linux (#18).

Fixed in 1.21.123 (devneet-id/rune#38): shard paths with `\` on Windows — the cause of the Exura relics that opened oddly on Linux; an older relic's `\` is now read as `/` (#37) · `weaver_min_php()` changing strings (#33) · Crafter writing an empty file when no template fits (#34) · `ENCRYPTION gzip` (#35) · a failed spark leaking into the next build (#36).

## Open
| Issue | What happens |
|---|---|
| `Specter::soul('x', 0)` keeps the old value (devneet-id/rune#46) | `0`, `''` and `false` are read as "no value". Store a non-empty value (e.g. `'0'` is also lost — use `'zero'` or an array) until fixed. |

## Planned work
| Task | State | Plan |
|---|---|---|
| Altar → Exura | postponed | Altar still uses Nirvana, runs `start cmd /k` (Windows only) with unsanitised POST input, and old paths (`.echoes/rune.php/`, `shards/`). See [Altar](altar.md). |

## Not tested yet
- Specter on macOS (Terminal via `osascript`) — written, never run on a Mac.
- Minister against a real familiar (URL + token).
- The rune-dev trials run on Linux (the agent's bench) and on Windows (the administrator's, 199/199 on 1.21.133); on 1.21.138 the 278 trials (21 scenarios) pass on Linux; macOS not yet.
