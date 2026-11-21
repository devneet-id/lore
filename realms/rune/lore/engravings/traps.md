# Traps

> Mistakes that are easy to make, and how to avoid them.

| You see | Because | Do |
|---|---|---|
| `Keeper::item()` returns `true` but nothing is saved | `Keeper::begin()` / `Keeper::end()` are missing (Sentinel does not add them) | Add `Keeper::begin()` after `Chanter::begin()` and `Keeper::end()` before `Aether::end()` |
| An empty list is not saved | `Keeper::item('x', [])` is read as *get* | Save `(object) $list` |
| A spell value is cut at a space | From code, casts are split by spaces | Use `%20`, or quotes on the command line |
| `--flag` gives `true`, a missing spell gives `false` | That is how spells are read (a bare flag was `'1'` before 1.21.137) | Check `is_string($v)` when a value is required |
| VS Code shows `cast` as Plain Text | No extension and no shebang | Start with `#!/usr/bin/env php` |
| `Class "Rune\X\Manifest" not found` | The rune is not there (or was deleted) | `sentinel --runite-remove=X`, or create the rune |
| `sentinel --runic-*` / `--phantasm-*` says *needs The Evolution of Eidos* | Not in evolution mode | `php cast sentinel --evolution` |
| `reliquary --initiate` / `--discover` / `--retrieve` says *opens with federation* | Not in federation mode | `php cast sentinel --federation` |
| An old spell answers *`--x` is now `--y`* | The spell was renamed | Use the new one ([Sentinel](../../reference/runites/sentinel.md#old-spells)) |
| *the seal is broken* | The downloaded relic does not match the reliquary's sha256 | Do not open it; tell the reliquary's owner |
| `@liberations/` or `@liberation/` runes are gone | Your runes live in `@evolution/` now (`@liberation/` keeps the portable runtimes) | Move the folders, `sentinel --evolution` |
| `sentinel --runtime-*` says *needs The Liberation of Forte* | Not in liberation mode | `php cast sentinel --liberation` |
| A relic opens without the files you built | Nothing was listed as a shard (Forger adds none) | List them in a `store` cast with `Keeper::shard([...])` |
| A Crafter build says `Skipped=<n>` | Those shards are not in the seed's `LANGUAGE` (or are folders) | Add the language to `LANGUAGE`, or leave them out |
| An evolution rune is ignored | Its name is an origin rune name | Rename it |
| `Weaver::bond('x')` errors | The second argument is required | `Weaver::bond('x', null)` |
| `Keeper::item('x')` gives an object, not an array | Items are kept as JSON objects | `json_decode(json_encode($data), true)` |
| A `{{key}}` in a later template is already filled | `Weaver::bind()` keeps every value in the global bond | Pick specific keys; never `nl`, `tab`, `end`, `php`, `bold` (Whisper's own tokens) |
| A Manifest method named `list` fails | `list` is a PHP keyword | Use another name (e.g. `quests`) |
