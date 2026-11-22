# Evolution

> The Evolution of Eidos — rebuild Rune in your own form.

Evolution is the release of Rune from its **Origin** to its **contributors**. Full freedom is given; only the **paradigm** stays — Ether, Essence, Entity, Manifest, Phantasm. With it you can build a new working environment, a different workflow, and runes of your own: public (to contribute) or private (local).

*Eidos* is the form behind a thing. It is only a caption — the words you see at the entrance.

## Unlock evolution mode
Ask the Sentinel:
```bash
php cast sentinel --evolution
```
```
::S E N T I N E L
[√] The Evolution of Eidos is unlocked: Rune\Ethereal::evolution();
[i] Read @evolution/README.md
```
It writes one line under the `require` line of your runite:
```php
#!/usr/bin/env php
<?php
require_once __DIR__ . '/vendor/autoload.php';

Rune\Ethereal::evolution();
```
Run the runite. The entrance changes from *The Awakening of Void* to:
```
 D E V N E E T  The Evolution of Eidos
```
Ask again and Sentinel only tells you it is already unlocked. To close the mode, delete the line by hand.

## What it does
`Rune\Ethereal::evolution()`:
1. makes `@evolution/` **next to the runite** (wherever you cast it from), with a `README.md` greeting;
2. adds a second autoloader: `Rune\X\…` → `@evolution/X/…`;
3. defines `EVOLUTION` — the path of `@evolution/`.

From then on:
- `aether_list_runes()` lists your runes (every PascalCase folder of `@evolution/`, through `aether_list_evolution()`) after the ten origin runes, and their Phantasm versions join the footer `Version=`.
- Sentinel opens its **E V O L U T I O N** spells: `--runic-create`, `--runic-delete`, `--phantasm-upgrade`, `--phantasm-repair` ([Sentinel](../../runites/sentinel.md)).

## The one law
**An evolution rune never replaces an origin rune.**
- The `@evolution/` loader is registered **after** Composer's, so `Rune\Whisper\…` always comes from the origin.
- Sentinel refuses an origin name, and a folder in `@evolution/` with one is never listed.
- Need another Whisper? Make a new rune with its own name (`MyWhisper`) — and only evolution runes are yours to change.

## Remember
- `@evolution/` lives next to the runite: `php lib/cast` from a parent folder finds the same runes as `php cast` inside `lib/`.
- `@evolution/` belongs to your project — it goes into git.
- Without evolution mode your runes do not exist, and the evolution spells answer *needs The Evolution of Eidos*.
- Old names you may still meet: `@ethereal/`, `@liberations/`, and `@liberation/` for runes (before v1.21.117) — all are now `@evolution/` (move the folders). `Rune\Ethereal::liberation()` now opens the runtime mode ([Liberation](../4-the-beyond/liberation.md)).
- Evolution, [Federation](../4-the-beyond/reliquary.md) and [Liberation](../4-the-beyond/liberation.md) can be open together; the caption of the highest wins ([Modes](../../modes.md)).
