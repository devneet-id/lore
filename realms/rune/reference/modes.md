# Modes

> A mode is a step away from the origin. Each one is a line in your runite and a folder next to it.

A runite unlocks a mode with Sentinel. Sentinel writes one line under the `require … autoload.php` line, and the mode opens its folder next to the runite with a `README.md` greeting. An unlocked mode is not unlocked twice — Sentinel only tells you. To close a mode, delete its line by hand.

```php
require_once __DIR__ . '/vendor/autoload.php';

Rune\Ethereal::evolution();
Rune\Ethereal::federation();
Rune\Ethereal::liberation();
```

| Mode | Unlock | Line | Folder | Constant | Caption |
|---|---|---|---|---|---|
| — | — | — | — | — | *The Awakening of Void* |
| Evolution | `sentinel --evolution` | `Rune\Ethereal::evolution();` | `@evolution/` | `EVOLUTION` | *The Evolution of Eidos* |
| Federation | `sentinel --federation` | `Rune\Ethereal::federation();` | `@federation/` | `FEDERATION` | *The Federation of Fides* |
| Liberation | `sentinel --liberation` | `Rune\Ethereal::liberation();` | `@liberation/` | `LIBERATION` | *The Liberation of Forte* |

Modes can be open together. The caption of the highest wins: **Liberation > Federation > Evolution > none**.

## The shape of a mode folder
- The main content lives **directly in the root** of the mode folder: runes (PascalCase), `<vendor>/` of relics, `php@<version>/`.
- Extra features become **keys in `<mode>.json`**, not new folders.
- A mode folder belongs to your project and goes into git. `sentinel --gitignore` hides only `vendor/` and every `.echoes/`.

## Evolution — runes of your own
*Eidos* is the form behind a thing: here you rebuild Rune in your own form.

```
@evolution/
├── Ledger/            Ether.php Essence.php Entity.php Manifest.php Phantasm.php
└── README.md
```
- A second autoloader maps `Rune\X\…` → `@evolution/X/…`, registered **after** Composer's: an evolution rune never replaces an origin rune.
- `aether_list_evolution()` lists every PascalCase folder; `aether_list_runes()` adds them after the ten origin runes, and their Phantasm versions join the footer `Version=`.
- Sentinel opens the **EVOLUTION** spells: `--runic-create`, `--runic-delete`, `--phantasm-upgrade`, `--phantasm-repair` ([Sentinel](runites/sentinel.md)).
- Learn it in [Act 3 · Evolution of Eidos](../lore/acts/3-evolution-of-eidos/evolution.md).

## Federation — your own reliquary
*Fides* is trust; *foedus* (the pact behind "federation") shares its root. Every reliquary stands on its own, yet they are connected — forks of forks — and the seals (sha256) keep the trust between them.

```
@federation/
├── devneet-id/how-to-casting@0.1.0.rune
├── federation.json
└── README.md
```
```json
{ "updated": "…",
  "reliquary": { "main": "<you>/reliquary", "list": { "<vendor>/<repo>": { "repo": "…", "runite": "cast", "note": "…", "tags": { … } } } } }
```
- `main` is set by `reliquary --initiate --repo=<you>/reliquary`; without it the reliquary is `devneet-id/reliquary`.
- `list` holds plain relics, filled by `--discover` (replaced) and by `--relic`, `--relics`, `--relic-runite` (added).
- The Reliquary opens its **FEDERATION** spells: `--initiate`, `--discover`, `--retrieve` ([Reliquary](runites/reliquary.md)).
- Without federation every relic comes from `devneet-id/reliquary` and nothing is recorded.
- Learn it in [The Reliquary](../lore/acts/4-the-beyond/reliquary.md).

## Liberation — your own PHP runtime
*Forte* is freedom in ability: your app is no longer bound to the PHP of the machine it lands on.

```
@liberation/
├── php@8.3.36/        php / php.exe, ext/, php.ini
├── liberation.json
└── README.md
```
```json
{ "updated": "…",
  "php": { "version": "8.3.36", "os": "windows", "arch": "x86_64", "extensions": ["mbstring", "openssl"], "source": "…" } }
```
- Sentinel opens the **LIBERATION** spells: `--runtime-install[=php@<version>]` (`--os=windows|linux|macos`, `--arch=x86_64|aarch64`), `--runtime-list`, `--runtime-remove=php@<version>` ([Sentinel](runites/sentinel.md)).
- **Windows** builds come from windows.php.net (NTS x64, sha256 checked); a small `php.ini` is written with `extension_dir = "ext"` and the extensions Rune reaches for (curl, fileinfo, mbstring, openssl, zip — when present).
- **Linux and macOS** builds are static PHP cli builds from static-php (`dl.static-php.dev`); give the full version (`php@8.3.14`) unless it is the PHP you are running.
- Empty `--runtime-install` takes the PHP you are running now.
- `liberation.json` records the runtime in use; `--runtime-remove` clears it when that one is removed.
- Run your runite with it: `@liberation/php@<version>/php cast` (or `php.exe` on Windows).
- Learn it in [Liberation](../lore/acts/4-the-beyond/liberation.md).
