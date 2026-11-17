# Sentinel

> Someone or something that guards.

Sentinel guards your runite. It unlocks the modes, writes runes into the runite and takes them out, helps you shape runes of your own (evolution) and keeps a PHP runtime (liberation).

## Spells
| Group | Spell | Does |
|---|---|---|
| HELP | `sentinel --gitignore` | writes a marked block in the `.gitignore` next to the runite: `vendor/` and every `.echoes/` |
| UNLOCK | `sentinel --evolution` | writes `Rune\Ethereal::evolution();` under the `require` line, opens `@evolution/` |
| UNLOCK | `sentinel --federation` | writes `Rune\Ethereal::federation();` under the `require` line, opens `@federation/` |
| UNLOCK | `sentinel --liberation` | writes `Rune\Ethereal::liberation();` under the `require` line, opens `@liberation/` |
| RUNITE | `sentinel --runite-insert=Keeper` | adds `use Rune\Keeper\Manifest as Keeper;` and `Keeper::ether()::essence()::entity();` at the markers |
| RUNITE | `sentinel --runite-insert=Keeper.entity` | awakens only some parts (`ether`, `essence`, `entity`) |
| RUNITE | `sentinel --runite-remove=Keeper` | removes them again (`Keeper.essence` removes one part) |

### EVOLUTION (evolution mode only)
| Spell | Does |
|---|---|
| `sentinel --runic-create=Ledger` | creates `@evolution/Ledger/` with the five files (origin names are refused) |
| `sentinel --runic-delete=Ledger` | deletes it and removes it from the runite |
| `sentinel --phantasm-upgrade=Ledger` | raises its minor version by one (`0.9` → `0.10`); refuses an unknown rune or a version that is not `<major>.<minor>` |
| `sentinel --phantasm-repair=Ledger` | node + link + note at once, then raises the version only if one of them changed |
| `sentinel --phantasm-repair=Ledger --mode=node` | only rebuilds the node list from the code (`--mode=note` copies every `#NOTE`, `--mode=link` finds which runes it uses) |
| `sentinel --phantasm-repair --all` | every rune (with or without `--mode`) |

### LIBERATION (liberation mode only)
| Spell | Does |
|---|---|
| `sentinel --runtime-install` | downloads the PHP version you are running now into `@liberation/php@<version>/` (with a progress bar) |
| `sentinel --runtime-install --from=local` | copies the PHP you are running now |
| `sentinel --runtime-install=php@8.3` | another version; `--os=windows\|linux\|macos`, `--arch=x86_64\|aarch64` for another system (Windows: windows.php.net, sha256 checked; Linux/macOS: static-php, full version) |
| `sentinel --runtime-url=<url> --name=node@22` | any runtime from a link (zip, tar.gz, tar.bz2, tar, single file); `--sha256=` to check it |
| `sentinel --runtime-list` | the runtimes Rune knows (php), the ones in `@liberation/`, and the one in use (`liberation.json`) |
| `sentinel --runtime-use=php@8.3.6` | makes a kept runtime the one in use |
| `sentinel --runtime-remove=php@8.3.36` | removes a runtime; the newest kept version of it takes its place |
| `sentinel --runtime-launcher` | writes `cast.bat` (Windows) or `cast.sh` that runs the runite with the PHP in use |

The `.gitignore` block, written again (not added twice) on every run; your own lines are kept:
```
# rune (sentinel)
vendor/
.echoes/
# /rune
```

## Old spells
| Was | Is |
|---|---|
| `--invoke` / `--revoke` | `--runite-insert` / `--runite-remove` |
| `--create-rune` / `--remove-rune` | `--runic-create` / `--runic-delete` |
| `--phantasm-up` | `--phantasm-upgrade` |
| `--phantasm-fix`, `-node`, `-note`, `-link`, `-link-all` | `--phantasm-repair` (`--mode=…`, `--all`) |

## Notes
- An unlocked mode is not unlocked twice: Sentinel only tells you. To close a mode, delete its line by hand.
- Sentinel writes at `#sentinel-manifest` and `#sentinel-awaken`. Keep the markers.
- `--runite-insert=Keeper` does not add `Keeper::begin()` / `Keeper::end()` — write them yourself.
- Sentinel keeps the runite's own line ending (CRLF or LF).
- Rune names are matched whatever their case (`ledger` → `Ledger`).
- `--altar` (the GUI) and `--inspect` are still there, hidden while in development.
