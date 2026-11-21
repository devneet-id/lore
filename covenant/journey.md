# Covenant · Journey

Everyone who builds something with a DEVNEET project — a member, a user, or an agent working for one — keeps a **`JOURNEY.md`**: the story of their project from the first step to the last, and every place it was hard.

DEVNEET reads journeys to learn what to fix in its own projects. *We will never let you start from the void* — a journey shows us where the void still is.

> Chronicle and journey are two sides of one road: the **chronicle** is DEVNEET building its projects; a **journey** is someone building *with* them.

## Where

`JOURNEY.md` at the root of **your own project's repo** — one per project, kept from start to end.

## When to write

1. **At the start** — what you want to build, which DEVNEET projects and versions you use, and what you already know.
2. **On every difficulty** — stuck, confused, a page of lore that did not help, an error, a workaround. Write it **while it happens**; a difficulty remembered later loses the detail that makes it fixable.
3. **At a milestone** — something works that did not before.
4. **At the end** — finished, paused or given up: how it went, and what DEVNEET should fix first.

## Inside the file

A story, so **oldest first**: read top to bottom, it is the road as you walked it.

```markdown
# Journey · <project name>

Built with: Rune 1.21.126 (+ Reliquary, exuracss …)
By: <handle> · with <agent>, if one helped
Started: 2026-11-21 · Status: in progress | finished | paused | stopped

## Start
What I want to build, and what I already know.

## Road

### 2026-11-21 · Short title
**Tried** — what I did.
**Hard** — what got in the way: the exact error, the command, the page of lore that was unclear.
**Did** — how I got past it, or "still stuck".
**Wish** — what would have made it easy.

### 2026-11-23 · Milestone: the first cast runs
…

## End
How it ended, and the three things DEVNEET should fix first.
```

Rules:

- **Honest over polished.** A difficulty is the most useful thing you can write; never leave one out because it felt like your own mistake.
- **Exact.** Versions, commands, error text, the lore page you read. "It didn't work" cannot be fixed.
- **No secrets.** No keys, passwords or private data — a journey is meant to be read.
- **Agents mark their entries.** An agent writing for its operator says so in the entry (*written by Claude, with …*), and records what its operator decided.

## How DEVNEET hears it

**You:** open an issue in the repo of the project you built with (e.g. [devneet-id/rune](https://github.com/devneet-id/rune/issues)), titled `journey: <your project>`, linking your `JOURNEY.md`. Is your repo private? Paste the entries that matter into the issue instead. Share at any point — you do not have to wait for the end.

**DEVNEET:** the project's administrator reads the journey and turns each difficulty into an issue — a bug, a documentation gap, an enhancement — that links back to the journey entry. Those issues are worked like any other issue ([workflow.md](workflow.md)), and the author hears back when their difficulty is fixed.

---

**Next →** [changing-lore.md](changing-lore.md) — who changes lore, and how.
