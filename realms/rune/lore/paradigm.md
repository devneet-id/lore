# Paradigm

> Why Rune exists, and the rules it never breaks.

## Rune is a door, not a finished framework
Rune is the lowest layer beneath PHP. It gives you two things:

- a **paradigm** — a way of seeing code as runes: Ether, Essence, Entity, Manifest, Phantasm;
- the **origin runes** — ten runes in the `devneet/rune` package.

On top of them you build tools, apps, even frameworks of your own — modular, fast, light, many-purposed. Think of a Swiss Army knife: one handle, many blades, and a blade opens only when you need it.

> *Rune is a lore-driven, modular concept beneath PHP, designed not to dictate development — but to respond to it.*

Only the paradigm is fixed. Everything else is yours to change.

## Where the names come from
At first, humans did not know anything. By looking, writing and growing, they came to understand. Rune keeps that path in its names:

- **Rune** — something we do not know yet.
- **Ethereal** — the place of what is not yet known (`Rune\Ethereal`, the class that opens Awakening and the modes).

Every part of the system is named for its **role in the world**, not with a generic word. A lore name carries meaning you cannot see in the code — so when a word is new, look it up in the [glossary](../reference/glossary.md).

## The five subjects of a rune
| Subject | Lore | Code | Nature |
|---|---|---|---|
| **Ether** | something that never changes but always has meaning | `define(...)` in `Ether.php` | rules, constants |
| **Essence** | something that changes as time goes on | `$GLOBALS[...]` in `Essence.php` | the state that flows while a runite lives |
| **Entity** | something that makes other things change | `function rune_xxx()` in `Entity.php` | **all of the logic** |
| **Manifest** | a box that connects things so they work together | `class Rune\X\Manifest` (static) | the face of the entities, for your runite |
| **Phantasm** | a picture in the mind, to understand | `class Rune\X\Phantasm` | the shadow of the rune — living documentation |

## The rules between the layers
- **Entity moves between runes.** It may call the entities of other runes (`keeper_item_get`, `cipher_hash`, `aether_arcane`). This is how runes work together.
- **Manifest moves between engravings.** It only shows the entities to your runite and holds no logic of its own. Every method: call the entity → `aether_arcane('X.manifest.name')` → return.
- **Phantasm is the contract** between the maker of a rune and the Grimoire, and Rune's replacement for heavy Reflection. *A rune without a Phantasm is a rune nobody knows — and likely of no use.*
  - `version`, `main` (name), `user` (who keeps it), `note` (purpose), `mark` (how safe it is: VOID → BETA → EXIST), `link` (the runes it needs), `node` (every ether, essence, entity and manifest with its `#NOTE`), `flow` (whether the runite must call its `begin()` / `end()`), `origin` (its folder).

**Who may use whom**

| Subject | Used by |
|---|---|
| Ether | Essence, Entity, Manifest, other Manifests |
| Essence | Entity, Manifest, other Manifests |
| Entity | Manifest, other Entities |
| Manifest | other Entities, other Manifests |

**Terms**
- Never instantiate a core Manifest — call it statically.
- Every rune has its origin in Aether.
- Before use, a rune's ether, essence and entity must be awakened: `X::ether()::essence()::entity();`.

## Principles
1. **One rune, one purpose.** No copies of a rune; need another version → a new rune with its own name (e.g. `MyWeaver`).
2. **Runes are not standalone.** Aether flows into every rune; leaning on Aether is the design, not a flaw.
3. **Runes live inside an engraving.** Global functions without namespaces are safe, because they run inside a runite that stands on its own (a CLI, a CRUD, a tool).
4. **Lazy, no bootstrap.** A rune that is not called is not loaded; no container, no dependency injection, no Reflection at run time.
5. **One package.** The origin runes stay together; growth happens through **Evolution** (runes of your own), not through an ecosystem of small packages.
6. **Every rune has a clear role.** Chanter is the command line. **HTTP is not part of Rune**: HTTP API endpoints are the domain of exuraphp. Minister talks to a *familiar* as a client, never as a server.

## Levels of work
| Level | What | Examples |
|---|---|---|
| **Origin runes** | the material: the ten runes of the package | Aether, Chanter, Weaver, … |
| **Built-in runites** (`@runite/`) | the first works made from the origin runes — real examples and helpers at once | Awakening, the main hall, Grimoire, Reliquary, Sentinel |
| **Your runites** | apps engraved with runes | a `cast`, a CRUD, a build tool |
| **Evolution runes** (`@evolution/`) | new runes you make yourself | `Ledger` |

## Modes
A runite can unlock three modes, each a step further from the origin:

| Mode | Caption | What it unlocks |
|---|---|---|
| Evolution | *The Evolution of Eidos* | runes of your own in `@evolution/` — *Eidos* is the form behind a thing |
| Federation | *The Federation of Fides* | your own reliquary and its relics in `@federation/` — *Fides* is trust |
| Liberation | *The Liberation of Forte* | portable runtimes in `@liberation/` (PHP, Node, Python…) — *Forte* is freedom in ability |

Without a mode the caption is *The Awakening of Void*. Details: [Modes](../reference/modes.md).

## The life of a work
**Awakening** (rise from the void: a blank runite or a relic) → **Engraving** (carve runes into the runite with `Chanter::cast`) → the **Arcane** is recorded (Aether's trace, kept by Keeper) → the **Grimoire** is read (Phantasm and arcane) → a **Relic** (the runite preserved in a `.rune`) → shared through a **reliquary** → found → **opened** again, read with an understanding of runes.

> Whoever finds a relic needs an understanding of runes to read it — it is sealed with the runic cipher.

## The Arcane — a trace in two realms
- To the system it is a **log**. To the lore it is a **mystic recorder in two realms**.
- *Arcane* comes from Latin *arcanus* (hidden), from *arca* (a chest): secret knowledge kept in a chest.
- **The realm of runes:** `aether_arcane()` is called whenever a Manifest or Entity moves. **The chest:** Keeper writes `.echoes/<runite>/arcane.txt`. **The realm of the user:** `grimoire --arcane` opens the chest.
- The Arcane is **not a rune** — it is a property of Aether.

> *Aether is the unseen flow; the Arcane is its secret trace, kept in a chest, opened only for the one who calls its name.*

## A runite as a whole workshop
A runite can hold a complete working environment in one file. The Exura website relics show it: `build` (Crafter) → `store` (the shards, with `Keeper::shard`) → `watch` (Specter observer) → `serve` (Specter dev server) → `start` (another process) → `ready` (build + store, then a release folder). See [Bundling](acts/2-understanding-its-flow/bundling.md) and [Exura](acts/2-understanding-its-flow/exura.md).

## Rune and Exura
The **Exura series** (exuracss · exurajs · exuraphp) is a set of very light CSS, JS and PHP frameworks, each shaped with a `cast` runite in its own repo — a real work built on Rune. Rune is **not** Exura's build engine: building is just one engraving (Crafter, Forger, Weaver, Chanter) inside a `cast`. Exura's READMEs say it plainly: *"Shaped with Rune"*.

## What Rune is not
- Not a set of small packages — the origin runes are not split apart.
- Not standalone runes — every rune flows with Aether.
- Not an HTTP framework — HTTP APIs are exuraphp's domain.
- Not a "build engine" or a "task engine".
- Not versioned by its Packagist tag alone — every rune carries its own Phantasm version, and the footer counts them.
- Not Reflection — the Phantasm is declared and alive.
- Not to be measured as an ordinary framework or library (dependency injection, namespaced functions, tiny packages).

Next: [Act 0 · The Void](acts/0-the-void/README.md)
