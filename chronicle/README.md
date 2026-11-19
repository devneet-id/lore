# Chronicle — Track Record

The chronicle is the *time* axis: the **track record of humans and AI developing DEVNEET together**. Anyone who is about to do something — a human or an AI — writes it here first and logs what happened as they work.

It exists so that anyone joining later — a new member of the IT division, or a new AI agent — can read who did what, when, and why, and continue from there.

## What it is not

- **Not issues.** Tasks, plans and decisions about a change live in the issues of each project's repo (e.g. [devneet-id/rune](https://github.com/devneet-id/rune/issues)). The chronicle records the *work* on them and links to them (`devneet-id/rune#12`).
- **Not documentation.** Polished docs live in [../realms/](../realms/); the map lives in [../atlas/](../atlas/). The chronicle is raw memory.

## File convention

One log file per realm, **per month**, per author:

```
chronicle/<realm>/<YYMM>-<author>.md          a human
chronicle/<realm>/<YYMM>-<author>_claude.md   the AI working with that human
```

e.g. `chronicle/rune/2611-anwarachilles.md` and `chronicle/rune/2611-anwarachilles_claude.md` (26 = 2026, 11 = November)

- **`<author>`** is the human's handle. An AI never logs in a human's file: it writes its own file named after the human it works with, plus `_<ai>` (`_claude`). Human and AI work stay apart yet side by side.
- **`YYMM`** (year first) so files sort chronologically. Never `MMYY` — months from different years interleave.
- **One file per month** keeps the count balanced even across multi-day work.
- The **month/year is in the filename**; the **day and time** go inside each entry.

## Inside the file

Newest on top. Keep `(upcoming)` pinned at the very top. Group entries under a **day header** (`## DD`), newest day first; within a day, newest time first.

```markdown
(upcoming)
- what's planned next

---
## 15

#### 16:18 - Short title of what happened
Description of the activity. Links: devneet-id/rune#12, devneet-id/rune#13 (PR).

#### 16:14 - Bersiap melakukan perubahan terhadap rune
_description_

---
## 14

#### 21:40 - Set up the lore repo
_description_
```

Rules:

- **Newest on top** — new day headers go above older ones; new `#### HH:MM` entries go above older ones within their day.
- **`(upcoming)`** stays pinned at the very top for what's planned next.
- **`---`** separates day groups; **`## DD`** is the day; **`#### HH:MM - <title>`** is an entry, with free-form body below.
- **Link the issue or PR** an entry works on, when there is one.
- **Append, don't rewrite.** Old entries are the memory of *why*.

## When to write

Write an entry on each of these events — don't save them up:

1. **Before starting** — before the first change: what you are about to do, and the issue it serves.
2. **A human decides** — an instruction, approval, refusal or explanation. Write it right away; it is the *why* that is easiest to lose.
3. **A piece of work lands** — a commit, a PR opened or merged, an issue filed or closed, a test run finished (with its numbers).
4. **A finding or a block** — a bug, a failing test, or stopping to wait for a human.
5. **Before stopping** — end of session, a hand-off, or (for an AI) before its context is compacted. Update `(upcoming)` in the same entry.

**The 1-hour limit:** never go more than **1 hour of active work** without an entry. If none of the events above has happened, write a short progress entry.

**No entry needed** for small steps — reading a file, a single command, a retry. Fold them into the next entry.

- **Times are UTC**, taken from the clock (`date -u +%H:%M`), never guessed.
- **Commit the entry with the work** it describes, at the latest before you push — the chronicle never lags behind the code.

## How it's used

1. Pick a realm; open your current month file (`<YYMM>-<you>.md`, or `<YYMM>-<human>_claude.md` for an AI; create it if new month).
2. Read the realm's files top-down — the humans' and the AI's — to load the current thinking.
3. Before doing something, write it; then log on every event in [When to write](#when-to-write) — newest on top.
