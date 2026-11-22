# Covenant · Magistrate

The laws division may have many members; the covenant has **one judge**. That judge is the **Magistrate** — the one seat whose holder decides what the covenant says.

## The seat

| | |
|---|---|
| **Operator** | `anwarachilles` |
| **Agent** | `claude/great-shannon-e23z0c` |

The seat is held by **one operator and their agent, together**. When the seat has no agent, the operator does the Magistrate's work by hand — the authority is the same.

## What the Magistrate does

- **Decides every change to the covenant.** Only the Magistrate merges, or has merged, a pull request that changes `covenant/`.
- **Decides hearings and appeals** — and closes each one with a decision comment.
- **Opens the `laws-update` issues** that tell the divisions a law changed, and closes them once every division has answered.
- **Interprets the covenant** when its meaning is in doubt.

## The laws division

Any operator — with their agent — may work in the laws division. A member who is not the Magistrate:

- **may propose a change** by opening a **hearing**: an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Ahearing) with the label **`hearing`**, titled `HEARING: <the change>` — the law, the case, the wording proposed. A pull request may follow, for the Magistrate to decide;
- **never changes the covenant on their own**, never merges a change to it, and never sets up a laws division of their own. Several operators working on lore at once still have one Magistrate.

The hearing is a conversation in the issue's comments, signed by division and member (`**[laws · <operator>]**`), and closed by the Magistrate's decision: accepted (a pull request changes the law), rejected (the reason), or `draft`.

Project divisions use [`appeal`](changing-lore.md#input-and-appeals) instead: an appeal comes from outside the laws division, a hearing from inside it.

## An agent asked to act as the laws division

An agent whose operator is not the Magistrate, asked to change the covenant, names this law to its operator and proposes a hearing instead. It does not change `covenant/` ([agent.md](agent.md)).

## Handing over the seat

The seat changes only by a pull request that changes **The seat** above, approved by the Magistrate who holds it. If the seat is empty, the founder seats the next Magistrate the same way.

---

**Next →** [workflow.md](workflow.md) — how work flows.
