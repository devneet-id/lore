# Covenant · Release

A release is a promise to everyone who uses the project. A human makes it and answers for it; the agent does the work that leads up to it.

How a release is cut in each project (tags, packages, version numbers) lives in its realm, e.g. Rune's [Release](../realms/rune/lore/acts/4-the-beyond/release.md). This law is about **who decides, and when**.

## The human decides

- **Every release is a human's decision.** By default an agent never publishes a release — not a tag, not a GitHub release, not a package — even when it has the access to.
- **The human who decides is the project's release owner: its administrator** — the developer responsible for the project, not a founder or a member by title. When the agent asks, it asks that human.
- **The decision is final.** Trials and reports inform it; they do not overrule it. An agent never argues a decision away or acts around it.

## An agent with release permission

A human may let an agent publish releases. The permission:

- is **explicit** — said by the human, never inferred;
- is **recorded in the human's chronicle** (the human's own file), and in the agent's;
- names its **scope** — one release (`v1.21.123`), or standing permission for one project;
- can be **revoked** at any time, and the revoking is recorded the same way.

Even with permission, the agent publishes only after the human's **yes** on that release, unless the permission says otherwise.

## When: at the release point

A release does not follow the pace of the work. Rounds only split one problem into parts ([workflow.md](workflow.md)); they never call for a release. The agent brings the human a release report and asks *release, or not?* when one of these happens:

1. **The release point is reached** — the point the release owner set for the project. By default: **the issues are clean** — every issue the release owner wants in this release is closed, its PRs merged. The release owner may set another point (a chosen set of issues, a milestone); the agent records it in the chronicle. Example: Rune's release owner decided *"release after the issues are clean"*.
2. **The release owner asks** for a report — at any time.
3. **Hotfix** — a critical bug or a security hole fixed: the agent asks at once, without waiting for the release point.
4. **Reminder** — merged changes waiting more than **4 weeks** without a release: the agent reminds the human. A reminder, never a trigger.

The human may answer **no** and gather more work into the next release: a **no** is just as valid as a **yes**.

## The release report

The agent writes it; the human reads it and answers. Same shape every time, so it can be read at a glance:

```markdown
## Release v1.21.123?

**Tested** — trials, stress tests: what ran, where, and the numbers (e.g. 175/175 on Linux).
**Not tested** — what could not be run, and why (e.g. Windows not run here).
**Compared to the last release** — no fewer passing trials? any regression?
**Changes** — the issues and PRs merged since the last release.
**Runes affected** — the runes changed, and the runes that lean on them (links).
**Breaking changes** — each one with how to migrate, or "none".
**Known issues** — what still fails, and its effect on users.
**Lore** — updated to follow the code, or what is still missing.

**Draft release notes** — ready to publish.

**Agent's view** — ready / not ready, and why.
→ **yes / no?**
```

Rules for the agent writing it:

- **Facts and opinion apart.** The numbers above; the agent's view only at the end.
- **Failures first.** What failed or was not tested is stated plainly, never softened or left out. No OS or test beyond what the agent can run is forced — but every gap is named.
- **No pushing.** The report helps the human decide; it does not campaign for a yes.

## The answer is recorded

- **Yes** → a chronicle entry: the version, and the reason when something failed (e.g. *released with trial X failing: a known linking error, no effect on users*). Whatever failed goes into the release notes as **Known issues**.
- **No** → a chronicle entry: the reason, and what is needed before the next report.

## Release notes

The agent drafts and recaps the release notes; the human does not have to write them. Short, in English: a summary, the highlights, the runes and their versions, breaking changes with migration, known issues, and a link to the full changelog.

---

**Next →** [changing-lore.md](changing-lore.md) — who changes lore, and how.
