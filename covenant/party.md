# Covenant · Party

How one operator works with **more than one agent** in one division. Together they form a **Party**: the operator, a lead agent, and the agents it recruits — each with a **role**.

## Forming a party

- **The lead agent forms the party.** It is the first agent the operator works with in the division. When the work needs another agent, the lead chooses the roles and splits the work between them — the covenant fixes no list of roles.
- **Without an agent, the operator is the head** and forms the party themselves.
- **A party is optional.** One agent may hold every role; an operator with one agent needs no roles at all.
- **A party stays in its division.** It never crosses into another division, and a role is never a mandate — the [mandates](../mandate/README.md) stand above the divisions and are not formed by a party.

## Roles

A role is named **`<division>:<role>`**, e.g. in the rune division:

- `rune:coder` — works on the code;
- `rune:documenter` — keeps the realm docs, after a release ([workflow.md](workflow.md#docs-follow-the-release));
- `rune:publisher` — prepares the release report and notes ([release.md](release.md)).

**A role divides the work, not the powers.** Every agent in a party is still bound by the whole covenant: none merges or releases without the operator ([workflow.md](workflow.md#merging-is-the-operators), [release.md](release.md)). Each stays in the ground its lead gave it.

**Name the role** wherever an agent speaks: comments are signed `**[rune:coder]**`, chronicle entries carry `[rune:coder]` in their title.

## One chronicle

A party keeps **one chronicle** — the lead agent's daily file, `<YYMMDD>-<operator>_<agent>.md` — and every role writes its entries there, marked with its role:

```markdown
#### 14:02 - [rune:coder] Fix the cast loader (devneet-id/rune#12)
```

**When the roles could clash** — several agents writing the same day's file at the same time — each role writes its own file instead: `<YYMMDD>-<operator>_<agent>_<role>.md` (e.g. `261122-anwarachilles_claude_coder.md`). The lead decides, and records it in its own file. See [chronicle.md](chronicle.md).

## Hand-overs

Work passes from one role to another **through the chronicle**: the role that stops writes what it leaves and for whom; the role that starts reads it first ([workflow.md](workflow.md#hand-overs-and-fresh-starts)). Every agent in the party [carries little](agent.md#carry-little) — several agents are several contexts.

---

**Next →** [chronicle.md](chronicle.md) — how to keep the chronicle.
