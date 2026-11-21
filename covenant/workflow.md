# Covenant · Workflow

How work moves from an issue to merged code in a project's repo. Workflow is **how the work is done**; [release.md](release.md) is **when it is published**. They are separate laws: nothing in the workflow triggers a release.

**Lore itself is the exception:** lore changes by [changing-lore.md](changing-lore.md) — the laws division through pull requests, every other division straight to `main`.

## Divisions and operators

- **Every agent works for one division**, under its **operator** — the person it works for (every human member of DEVNEET is an operator), who gives it its tasks and its permissions.
- **An agent never takes over another division** — its work, its repo, its laws — without its operator's permission. It never decides to take one over on its own, even when it has the access and the change looks small: it raises the matter with its operator, or opens an issue for the division that owns it.

## Issues are the unit of work

- **Work comes from the issues** of the realm's repo (e.g. [devneet-id/rune](https://github.com/devneet-id/rune/issues)). Tasks live there, not in lore.
- **One issue, one problem.** A problem that is really two becomes two issues.
- **Confirm scope with your operator** before changing a project's repo.
- **A change lands as a pull request** that links its issue (`Fixes #12`, or `Part of #12` when the issue needs more than one PR).
- **Name work by what it fixes**, never by a made-up sequence number (`round 4`, `fix 3 of today`) — in PR titles, commits and chronicle entries alike. An issue number (`#12`) and the part of one issue (`part 1/3 of #12`) are not sequence numbers: use them.

## Findings go back to the issues

Something new found in the middle of the work — another bug, a gap, an idea — is **written back to the issues**: a new issue, linked from the one at hand. It is not fixed quietly in the current pull request. The current issue stays one problem; the finding waits for its own turn.

## Merging is the operator's

- **By default an agent never merges** a pull request — not its own, not anyone's. The operator reviews and merges.
- **An operator may let an agent merge.** The permission is **explicit** (said by the operator, never inferred), **recorded** (in the operator's chronicle — for the laws division, in its issue), names its **scope** (one pull request, or standing permission for one repo), and can be **revoked** at any time, recorded the same way.
- Merging is not releasing: even an agent allowed to merge publishes nothing without [release.md](release.md).

## Rounds: a technique for big problems

A **round** (or batch) is a suggested technique for working through **one** problem that is too big for one pass: split it into stages, so each stage stays small enough to do well and to check. It is a way of pacing, chosen by the operator — not a unit of planning and not a unit of release.

**When it helps:** one issue grows beyond what one pass can carry well. For example: a bug is reported with 10 cases; the agent's inspection widens it to 100. The operator splits the work into 3 rounds and picks the batch for each one.

**How:**

1. **The operator picks the batch** of each round. The agent works that batch only.
2. **Each round lands as one pull request**, named as a part of its issue: `part 1/3 of #12` in the PR title and the chronicle entry, with `Part of #12` in its body. When the total is not known yet: `part 1 of #12`.
3. **A round ends with a report to the operator:** what this part did, what it proved (tests, numbers), and what is left for the next part. Then the agent waits for the next batch.
4. **The last part closes the issue:** its pull request says `Fixes #12`.

**A round is not:**

- a set of issues picked together — several issues are simply several issues;
- numbered across the project (no "round 4");
- a release trigger — see [release.md](release.md).

## The flow

1. **Read lore** along the reading path, to load the team's current position.
2. **Take an issue**, and confirm its scope with your operator.
3. **Chronicle before starting** ([chronicle.md](chronicle.md)).
4. **Do the work** — in one pass, or in rounds when the operator splits it. Findings go back to the issues.
5. **Open a pull request** that links the issue; chronicle it.
6. **The operator reviews and merges** (or the agent, with permission); chronicle the landing.
7. **Release** happens only by [release.md](release.md): on the release owner's yes.

The laws division follows the same flow on lore, with one difference: it keeps **no chronicle** — its tasks and drafts are issues in [devneet-id/lore](https://github.com/devneet-id/lore/issues), and those issues are its record ([changing-lore.md](changing-lore.md)).

---

**Next →** [chronicle.md](chronicle.md) — how to keep the chronicle.
