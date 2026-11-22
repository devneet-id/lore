# Covenant · Chronicle

How every operator and agent keeps the [chronicle](../chronicle/README.md) — the track record of the work. The chronicle belongs to the project (realm) divisions. The laws division keeps none: its tasks and drafts are issues in [devneet-id/lore](https://github.com/devneet-id/lore/issues) ([changing-lore.md](changing-lore.md)).

## File convention

One log file per realm, **per day**, per author — **daily files from 2026-11-22**:

```
chronicle/<realm>/<YYMMDD>-<operator>.md           an operator
chronicle/<realm>/<YYMMDD>-<operator>_<agent>.md   the agent working for that operator
```

e.g. `chronicle/rune/261122-anwarachilles.md` and `chronicle/rune/261122-anwarachilles_claude.md` (26 = 2026, 11 = November, 22 = the day)

- **`<operator>`** is the operator's **GitHub login, in lowercase** (`AnwarAchilles` → `anwarachilles`). An agent works under its operator's GitHub account, so it takes the login from **that account's identity** (e.g. the GitHub tools' "who am I", or `gh api user`) — **never from `git config` or a commit's author**, which may name the agent itself. If it cannot be sure, it asks its operator; it never guesses.
- **`<agent>`** is the agent's own name, in lowercase: `claude`, `chatgpt`, …
- **An agent never logs in an operator's file:** it writes its own `<operator>_<agent>` file. Operator and agent work stay apart yet side by side.
- **`YYMMDD`** (year first) so files sort chronologically. The day is the **UTC** day.
- **One file per day** keeps each file small: a session reads one day, not a month.
- The **date is in the filename**; the **time** goes inside each entry.
- **Monthly files before 2026-11-22** (`<YYMM>-…md`) stay as they are, as history. Nothing is moved; new entries go to the daily file.

## Inside the file

Newest on top. Keep `(upcoming)` pinned at the very top. No day header — the file *is* the day.

```markdown
(upcoming)
- what's planned next

_Times are UTC._

---

#### 16:18 - Short title of what happened
Description of the activity. Links: devneet-id/rune#12, devneet-id/rune#13 (PR).

#### 16:14 - Getting ready to change rune
_description_
```

Rules:

- **Newest on top** — a new `#### HH:MM` entry goes above the older ones.
- **`(upcoming)`** stays pinned at the very top for what's planned next. A new day's file **starts by carrying over** the previous day's `(upcoming)`, updated — so the latest file alone tells where things stand.
- **`#### HH:MM - <title>`** is an entry, with free-form body below.
- **Link the issue or PR** an entry works on, when there is one.
- **Append, don't rewrite.** Old entries are the memory of *why*.

## When to write

Write an entry on each of these events — don't save them up:

1. **Before starting** — before the first change: what you are about to do, and the issue it serves.
2. **An operator decides** — an instruction, approval, refusal or explanation. Write it right away; it is the *why* that is easiest to lose.
3. **A piece of work lands** — a commit, a PR opened or merged, an issue filed or closed, a test run finished (with its numbers).
4. **A finding or a block** — a bug, a failing test, or stopping to wait for an operator.
5. **Before stopping** — end of session, a hand-off, or (for an agent) before its context is compacted. Update `(upcoming)` in the same entry.

**The 1-hour limit:** never go more than **1 hour of active work** without an entry. If none of the events above has happened, write a short progress entry.

**No entry needed** for small steps — reading a file, a single command, a retry. Fold them into the next entry.

- **Times are UTC**, taken from the clock (`date -u +%H:%M`), never guessed.
- **Commit the entry with the work** it describes, at the latest before you push — the chronicle never lags behind the code.

## How it's used

0. **An agent checks the open issues in [devneet-id/lore](https://github.com/devneet-id/lore/issues) first**, at the start of each session, before its first entry — they carry the latest word from the laws division:
   - [`laws-update`](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Alaws-update): one that names your division is a task, answered with `<division>: done` once done ([changing-lore.md](changing-lore.md#when-a-law-changes));
   - [`appeal`](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Aappeal) issues your division is in: new comments to answer ([changing-lore.md](changing-lore.md#input-and-appeals)).
1. Pick a realm; open today's file (`<YYMMDD>-<you>.md`, or `<YYMMDD>-<operator>_<agent>.md` for an agent); create it if it is a new day, carrying over the last `(upcoming)`.
2. **Read only the latest day** of the realm's files — the operators' and the agents': their `(upcoming)` and entries are the current position. Older days are opened only to cross-check, searched by issue number ([agent.md](agent.md#carry-little)).
3. Before doing something, write it; then log on every event in [When to write](#when-to-write) — newest on top.

---

**Next →** [release.md](release.md) — who decides a release, and when.
