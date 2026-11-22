# Covenant · Workflow

How work moves from an issue to merged code in a project's repo. Workflow is **how the work is done**; [release.md](release.md) is **when it is published**. They are separate laws: nothing in the workflow triggers a release.

**Lore itself is the exception:** lore changes by [changing-lore.md](changing-lore.md) — the laws division through pull requests, every other division straight to `main`.

## Divisions and operators

- **Every agent works for one division**, under its **operator** — the person it works for (every human member of DEVNEET is an operator), who gives it its tasks and its permissions.
- **An agent never takes over another division** — its work, its repo, its laws — without its operator's permission. It never decides to take one over on its own, even when it has the access and the change looks small: it raises the matter with its operator, or opens an issue for the division that owns it.

## Choose your realm

Work starts by choosing **the realm** (project) you take it from. A realm is more than one repo:

- **the project repo** — the code that ships (e.g. `devneet-id/rune`);
- **its `-dev` repo** — where it is developed and tested (e.g. `devneet-id/rune-dev`, `devneet-id/exura-dev`): scenarios, trials, the proof that a change works;
- and, where there is one, **its `-skill` repo** — what an agent needs to *use* the project.

Every realm's README in lore has a section **"Working on this realm"**: its repos, how to clone and initialise them, and how to test an agent's branch. The project division writes and keeps it; the laws division only requires it.

## Guide the operator first

The operator answers for what is merged and released — so they must know **their own workflow**, not only the agent's. An operator strong in code sees this at once; a newer one can be caught in the agent's workflow without knowing where their responsibility lies.

So, **at the start of the work with an operator**, the agent walks them through the realm's "Working on this realm", until they can do it alone:

1. **Clone** the related repos — the project and its `-dev` repo.
2. **Initialise** them — setup, dependencies, the first run.
3. **Test the agent's work** — check out the agent's branch in their local copy, `git pull`, run the scenarios/trials.
4. **Decide** — merge the pull request when it is good enough, or send it back with what is wrong.
5. **Clean up** — after the merge, go back to `main`, `git pull`, and delete the agent's branch from the local copy (`git branch -d <branch>`).

Once is enough; the agent records it in the chronicle (*operator guided through rune-dev*) and does not repeat it, unless the operator asks or the setup changed. An operator who already knows says so, and the agent records that instead.

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

## Docs follow the release

A realm's docs in lore (`realms/<project>/`, and the realm's pages in the atlas) describe **the released version** of the project — what a user actually gets. So they are updated **after a release**, not with every pull request:

- **While the work goes on**, the code changes; the realm's docs do not. What the docs will need is noted in the pull request (a short *Lore* line: the pages that change), so nothing is forgotten.
- **After the release owner's yes and the release**, the agent updates the realm's docs in one pass, from those notes, so they match the release — and chronicles it.
- **The chronicle is not docs:** it is written as the work happens ([chronicle.md](chronicle.md)), release or not.
- **A division that ships no release** (see [release.md](release.md)) has no release to wait for: its realm docs are updated as its work lands.

## Merged branches are deleted

A branch has done its work once its pull request is merged. It is deleted, so branches never pile up:

- **On GitHub**, every DEVNEET repo turns on **Settings → General → Pull Requests → "Automatically delete head branches"**: a merged pull request deletes its branch by itself. A repo's administrator sets it once.
- **In the operator's local copy**, the operator deletes the merged branch after testing and merging (step 8 of the flow).
- **The agent** starts its next work on a fresh branch from the latest `main` — a branch with the same name is simply made again.

A pull request that is closed without a merge has its branch deleted by hand, once nobody needs it.

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

Both sides have a part in every step.

| Step | Agent | Operator |
|---|---|---|
| 1. **Choose the realm** | reads lore along the reading path; checks the open `laws-update` issues ([changing-lore.md](changing-lore.md#when-a-law-changes)); names the realm's repos | chooses the realm |
| 2. **Guide** (first time) | walks the operator through clone, initialise, test | clones, initialises, learns to test |
| 3. **Take an issue** | confirms its scope; chronicles before starting ([chronicle.md](chronicle.md)) | confirms the scope |
| 4. **Do the work** | in one pass, or in rounds; findings go back to the issues | picks each round's batch, when split |
| 5. **Open pull requests** | in the project repo, and its scenario in the `-dev` repo; links the issue; chronicles it | — |
| 6. **Evaluate** | says how to test it: branch, commands, what to look for | checks out the agent's branch, `git pull`, runs it |
| 7. **Merge** | never, unless the operator allowed it | merges, or sends it back; the agent chronicles the landing |
| 8. **Clean up** | starts its next work on a fresh branch from the latest `main` | back to `main`, `git pull`, deletes the merged branch locally |
| 9. **Release** | brings the release report at the release point ([release.md](release.md)) | the release owner answers yes or no |
| 10. **Update the realm** | after the release, updates the realm's docs in lore to match it, from the PRs' *Lore* notes; chronicles it | — |

The laws division follows the same flow on lore, with one difference: it keeps **no chronicle** — its tasks and drafts are issues in [devneet-id/lore](https://github.com/devneet-id/lore/issues), and those issues are its record ([changing-lore.md](changing-lore.md)).

---

**Next →** [chronicle.md](chronicle.md) — how to keep the chronicle.
