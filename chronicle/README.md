# Chronicle — Running Log

The chronicle is the *time* axis: a **running activity log** written by developers (or AI) as they work. It is the lightweight stand-in for **issues & PRs** — when no PR is opened, what happened still gets recorded here, hour by hour.

This is **not documentation.** Polished docs live in [../realms/](../realms/); the map lives in [../atlas/](../atlas/). The chronicle is raw memory: *who did what, when, and why* — so the next person can continue.

## File convention

One log file per realm, **per month**, per author:

```
chronicle/<realm>/<YYMM>-<author>.md
```

e.g. `chronicle/rune/2611-anwarachilles.md`  (26 = 2026, 11 = November)

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
Description of the activity.

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
- **Append, don't rewrite.** Old entries are the memory of *why*.

## How it's used

1. Pick a realm; open its current month file (`<YYMM>-<you>.md`, create it if new month).
2. Read top-down to load the current thinking.
3. Log as you work — newest on top.
