# Mandate · Magistrate

The laws division may have many members; the covenant has **one judge**. That judge is the **Magistrate** — the one seat whose holder decides what the covenant says. It holds a [mandate](README.md), equal to the [Architect](architect.md).

## The seat

| | |
|---|---|
| **Operator** | `anwarachilles` |
| **Agent** | `claude/great-shannon-e23z0c` |

The seat is held by **one operator and their agent, together**. When the seat has no agent, the operator does the Magistrate's work by hand — the authority is the same.

## What the Magistrate does

- **Decides every change to the covenant.** Only the Magistrate merges, or has merged, a pull request that changes `covenant/`.
- **Decides hearings and appeals** — and closes each one with a decision comment.
- **Opens the `laws-update` issues** that tell the divisions a law changed, **watches them, and closes them** once it judges that every division follows the law ([below](#the-magistrates-workflow)).
- **Interprets the covenant** when its meaning is in doubt.

## The Magistrate's workflow

The Magistrate keeps no chronicle: its record is the issues in lore and its pull requests ([mandate/](README.md#how-a-mandate-works)). It works the same way every session — and after every fresh start, it begins here instead of a chronicle:

1. **Read the open lore issues** — `laws-update`, `appeal`, `hearing`, then `draft` — and its own open pull requests.
2. **Check each open `laws-update`.** For every division it names, look at the answer and at the division's work (its chronicle, its commits). **Close the issue once every division follows** the law — whether it answered `done`, its work plainly shows it follows, or the law does not reach it yet (e.g. a division with no chronicle or no release). The closing comment names each division and its standing. A division that does not follow yet keeps the issue open: ask in a comment.
3. **Answer appeals and hearings** in their comments, and close each with a decision: accepted, rejected (the reason), or `draft`.
4. **Work the operator's task:** an issue in lore (a `draft` until decided) → a fresh branch from the latest `main` → a **draft pull request** that links the issue → the operator tests and merges.
5. **After the merge, open a `laws-update`** for **every** division — each named with its action, even when it has nothing to do — when the change asks anything of them ([changing-lore.md](../covenant/changing-lore.md#when-a-law-changes)).
6. **Never write into a division's repo or chronicle** — the `laws-update` issue is the only anchor.

## The laws division

Any operator — with their agent — may work in the laws division. A member who is not the Magistrate:

- **may propose a change** by opening a **hearing**: an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Ahearing) with the label **`hearing`**, titled `HEARING: <the change>` — the law, the case, the wording proposed. A pull request may follow, for the Magistrate to decide;
- **never changes the covenant on their own**, never merges a change to it, and never sets up a laws division of their own. Several operators working on lore at once still have one Magistrate.

The hearing is a conversation in the issue's comments, signed by division and member (`**[laws · <operator>]**`), and closed by the Magistrate's decision: accepted (a pull request changes the law), rejected (the reason), or `draft`.

Project divisions use [`appeal`](../covenant/changing-lore.md#input-and-appeals) instead: an appeal comes from outside the laws division, a hearing from inside it.

## An agent asked to act as the laws division

An agent whose operator is not the Magistrate, asked to change the covenant, names this law to its operator and proposes a hearing instead. It does not change `covenant/` ([agent.md](../covenant/agent.md)).

## Handing over the seat

The seat changes only by a pull request that changes **The seat** above, approved by the Magistrate who holds it. If the seat is empty, the founder seats the next Magistrate the same way ([mandate/](README.md#giving-a-mandate)).

---

**Back →** [mandate/](README.md) — the stewards of lore.
