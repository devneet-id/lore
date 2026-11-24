# The Workshop

> Never change Rune without testing it like a user.

Rune is tested the way it is used: through runites. Keep a **workshop** — a folder of your own, next to your clone of `rune`, that loads Rune from disk. Every change is proved there before it is committed. The workshop is yours; it is not part of any repo. Rune's own workshop is the **`dev` branch** of `devneet-id/rune`: Rune sits in its `core/`, and `php cast init` / `use` / `update` keep it — see [Working on this realm](../../README.md#working-on-this-realm).

## Set it up
```
your-folder/
├── rune/        your clone or fork of devneet-id/rune — only what ships
└── workshop/    your runites and trials (any name)
```

`workshop/composer.json` maps `Rune\` to the local package:
```json
{ "autoload": { "psr-4": { "Rune\\": "../rune/" } } }
```
Run `composer dump-autoload` once (and again only when this file changes). Every runite in the workshop requires `workshop/vendor/autoload.php`, so it uses **your** copy of Rune, not Packagist.

## What to keep in it
| Folder | Use |
|---|---|
| `scenario/` | runites from easy to complex, one folder each, named after the scenario (`keep-notes`, no number); every runite has a `test` cast — its **trial** |
| a runner | one runite at the root that runs every trial, one by one — on the `dev` branch: `php cast scenario` (each scenario in a new terminal through Specter, `--here` for the same terminal) — and a coverage runite that counts which Phantasm nodes the scenarios touch |
| `.proof/` | in every scenario, git-ignored: the proof of its last trial — `report.txt`, `report.json` (read by the runner) and what it made (a Crafter bundle, a report) |
| an evolution runite | `Rune\Ethereal::evolution();` — for `sentinel --phantasm-*` on the runes you change |

## Write a trial
A trial is a cast that checks, not prints. A tiny helper is enough:
```php
function trial( $label, $ok ) {
  global $TRIAL; $TRIAL[] = $ok;
  Whisper::echo(($ok ? '{{color-success}} ✓ ' : '{{color-danger}} ✗ ') . '{{color-end}}' . $label . '{{nl}}');
}

Chanter::cast('test', function() {
  trial('greet answers', Chanter::cast('greet --name=Rune')() === 'Hello, Rune');
  // …one line per behaviour
}, 'Run the trial of this runite.');
```
- Catch PHP warnings as errors (`set_error_handler` → `ErrorException`) so a glitch fails one check instead of ending the run.
- Back up and restore any data the trial touches.
- Keep what the trial makes in `.proof/` (git-ignored) — it is the proof, open it after the run.
- A runite can be cast from any folder — Rune keeps `.echoes` next to it.

```bash
cd workshop/scenario/greet-and-show-flow
php cast test
```

## Work on a rune
```bash
php evolve                                  # "The Evolution of Eidos" on the main hall
php evolve grimoire --runic=Weaver              # read the contract
php evolve sentinel --phantasm-repair=Weaver    # node + link + note (+ version, only if changed)
php evolve sentinel --phantasm-upgrade=Weaver   # only raise the version
```
`--phantasm-*` spells are refused outside evolution mode (*needs The Evolution of Eidos*).

## Test the released version
To check what users get, make another folder with its own `composer.json` and `composer require devneet/rune`. The same runite runs unchanged — only the autoload source differs.

## Rules of the bench
- Files in `rune` are **LF** (`.gitattributes` keeps them so): never commit CRLF, and `php -l` every PHP file you touch.
- A new scenario: a folder named after what it does (`track-todos-with-report` — the name is the key, no number), a `cast` with the shebang, the workshop autoload, a `test` cast.
- A fix without a trial is a guess. Add the check first, watch it fail, then fix.
- Notes, drafts and trials stay in the workshop — never in `rune`.
