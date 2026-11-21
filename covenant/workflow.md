# Covenant · Workflow

How work moves from an issue to merged code. Workflow is **how the work is done**; [release.md](release.md) is **when it is published**. They are separate laws: nothing in the workflow triggers a release.

## Issues are the unit of work

- **Work comes from the issues** of the realm's repo (e.g. [devneet-id/rune](https://github.com/devneet-id/rune/issues)). Tasks live there, not in lore.
- **One issue, one problem.** A problem that is really two becomes two issues.
- **Confirm scope with your human** before changing a project's repo.
- **A change lands as a pull request** that links its issue (`Fixes #12`, or `Part of #12` when the issue needs more than one PR).
- **Name work by what it fixes**, never by a sequence number — in PR titles, commits and chronicle entries alike.

## Rounds: splitting one problem

A **round** is a human's way of pacing an agent through **one** problem that is too big for one pass. It belongs to the conversation between a human and their agent; it is not a unit of planning and not a unit of release.

**When:** one issue grows beyond what one pass can carry well. For example: a bug is reported with 10 cases; the agent's inspection widens it to 100. The human splits the work into 3 rounds and picks the batch for each one.

**How:**

1. **The human picks the batch** of each round. The agent works that batch only.
2. **Name it as a part of its issue:** `part 1/3 of #12` in the PR title and the chronicle entry. When the total is not known yet: `part 1 of #12`.
3. **A round ends with a report to the human:** what this part did, what it proved (tests, numbers), and what is left for the next part. Then the agent waits for the next batch.
4. **The issue closes with its last part.**

**A round is not:**

- a set of issues picked together — several issues are simply several issues;
- numbered across the project (no "round 4");
- a release trigger — see [release.md](release.md).

## The flow

1. **Read lore** along the reading path, to load the team's current position.
2. **Take an issue**, and confirm its scope with your human.
3. **Chronicle before starting** ([chronicle.md](chronicle.md)).
4. **Do the work** — in one pass, or in rounds when the human splits it.
5. **Open a pull request** that links the issue; chronicle it.
6. **The human reviews and merges**; chronicle the landing.
7. **Release** happens only by [release.md](release.md): on the release owner's yes.

---

**Next →** [chronicle.md](chronicle.md) — how to keep the chronicle.
