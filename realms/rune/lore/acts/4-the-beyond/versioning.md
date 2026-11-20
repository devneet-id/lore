# Versioning

> Every change raises a Phantasm; the footer counts them.

Rune counts its own growth. Each rune carries a version in its Phantasm; the footer of every run counts them. The count is the version of Rune — and the release tag.

## The footer
```
◇Version=1.21.133: ϟExecute=0.0070s, ΞMemory=975.42KB - ^1.14MB
```
`aether_version()` builds it, with **whole numbers** only:
1. Split `AETHER_VERSION` into major and minor (`'1.12'` → `1` and `12`).
2. Split every rune's `Phantasm::$version` into major and minor (`'1.18'` → `1` and `18`; `'0.10'` → `0` and `10`). A folder without a Phantasm is skipped.
3. `Version = <major> . <minor + sum of rune majors> . <sum of rune minors>`.

The ten origin runes today:

| | Aether | Chanter | Cipher | Crafter | Forger | Keeper | Minister | Specter | Weaver | Whisper | **Sum** |
|---|---|---|---|---|---|---|---|---|---|---|---|
| version | 1.21 | 1.16 | 1.7 | 1.16 | 1.17 | 1.17 | 0.4 | 1.11 | 1.10 | 1.14 | |
| major | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 1 | 1 | 1 | **9** |
| minor | 21 | 16 | 7 | 16 | 17 | 17 | 4 | 11 | 10 | 14 | **133** |

→ `1 . (12 + 9) . 133` = `Version=1.21.133`.

The footer (`aether_version(true)`) also counts runes in `@evolution/` in evolution mode (not those named like an origin rune), so your footer can be higher than the official one — that is expected. Everything that must match between machines counts the **origin runes only** (`aether_version()`): the relic header, `rune.json`, the copyright line of a Crafter bundle, and the release tag.

## Raise a version
Rule: **every change to a rune's Ether, Essence, Entity or Manifest raises that rune's Phantasm version.** The built-in runites of `@runite/` have no Phantasm and are not counted.

From an evolution runite (see [The Workshop](the-workshop.md)):
```bash
php evolve sentinel --phantasm-upgrade=Weaver
```
`--phantasm-upgrade` adds 1 to the minor: `1.7` → `1.8`, `1.9` → `1.10`. The footer's last number moves by one (`1.21.133` → `1.21.134`). Or edit `public $version` in `<Rune>/Phantasm.php` by hand — always `'<major>.<minor>'`, as a string.

`--phantasm-repair` raises the version only when it changed the Phantasm (node, link or note). A link records the version of the rune it leans on, so raising Aether changes the links of the runes that use it.

## Why it only goes up
- `--phantasm-upgrade` on any rune → last number +1.
- A rune raises its major (`0.3` → `1.0`) → the middle number +1; the last may drop, and the version still goes up.
- A new origin rune → middle + its major, last + its minor.
- An origin rune removed → both drop: raise the minor of `AETHER_VERSION` enough to keep the version going up.
- Never lower a version by hand.

## Version, tag, package
- The footer `Version=` of a clean checkout (no `@evolution/`) is the **release tag**: `v1.21.133`.
- Packagist reads the tags. See [Release](release.md).
- The version also guards relics: a relic made with a newer Rune is refused when opened — *This relic needs Rune X, you have Y.*
