# Covenant · Release

A release is a promise to everyone who uses the project. An operator makes it and answers for it; the agent does the work that leads up to it.

How a release is cut in each project (tags, packages, version numbers) lives in its realm, e.g. Rune's [Release](../realms/rune/acts/4-the-beyond/release.md). This law is about **who decides, and when**.

**It binds only the projects that ship releases** (e.g. Rune, Exura). A division whose work ships no release — no tag, no package, no published version (e.g. the reliquary division today) — has nothing to release, and this law does not apply to it.

## The operator decides

- **Every release is an operator's decision.** By default an agent never publishes a release — not a tag, not a GitHub release, not a package — even when it has the access to.
- **The operator who decides is the project's release owner: its administrator** — the developer responsible for the project, not a founder or a member by title. When the agent asks, it asks that operator.
- **The decision is final.** Trials and reports inform it; they do not overrule it. An agent never argues a decision away or acts around it.

## An agent with release permission

An operator may let an agent publish releases. The permission:

- is **explicit** — said by the operator, never inferred;
- is **recorded in the operator's chronicle** (the operator's own file), and in the agent's;
- names its **scope** — one release (`v1.21.123`), or standing permission for one project;
- can be **revoked** at any time, and the revoking is recorded the same way.

Even with permission, the agent publishes only after the operator's **yes** on that release, unless the permission says otherwise.

## When: at the release point

A release does not follow the pace of the work. Rounds only split one problem into parts ([workflow.md](workflow.md)); they never call for a release. The agent brings the operator a release report and asks *release, or not?* when one of these happens:

1. **The release point is reached** — the point the release owner set for the project. By default: **the issues are clean** — every issue the release owner wants in this release is closed, its PRs merged. The release owner may set another point (a chosen set of issues, a milestone); the agent records it in the chronicle. Example: Rune's release owner decided *"release after the issues are clean"*.
2. **The release owner asks** for a report — at any time.
3. **Hotfix** — a critical bug or a security hole fixed: the agent asks at once, without waiting for the release point.
4. **Reminder** — merged changes waiting more than **4 weeks** without a release: the agent reminds the operator. A reminder, never a trigger.

The operator may answer **no** and gather more work into the next release: a **no** is just as valid as a **yes**.

## The release report

The agent writes it; the operator reads it and answers. Same shape every time, so it can be read at a glance:

```markdown
## Release v1.21.123?

**Tested** — trials, stress tests: what ran, where, and the numbers (e.g. 175/175 on Linux).
**Not tested** — what could not be run, and why (e.g. Windows not run here).
**Compared to the last release** — no fewer passing trials? any regression?
**Changes** — the issues and PRs merged since the last release.
**Runes affected** — the runes changed, and the runes that lean on them (links).
**Breaking changes** — each one with how to migrate, or "none".
**Known issues** — what still fails, and its effect on users.
**Lore** — the realm pages to update after this release (from the PRs' *Lore* notes); docs follow the release ([workflow.md](workflow.md#docs-follow-the-release)).

**Draft release notes** — ready to publish.

**Agent's view** — ready / not ready, and why.
→ **yes / no?**
```

Rules for the agent writing it:

- **Facts and opinion apart.** The numbers above; the agent's view only at the end.
- **Failures first.** What failed or was not tested is stated plainly, never softened or left out. No OS or test beyond what the agent can run is forced — but every gap is named.
- **No pushing.** The report helps the operator decide; it does not campaign for a yes.

## The answer is recorded

- **Yes** → a chronicle entry: the version, and the reason when something failed (e.g. *released with trial X failing: a known linking error, no effect on users*). Whatever failed goes into the release notes as **Known issues**.
- **No** → a chronicle entry: the reason, and what is needed before the next report.

## Release notes

The agent drafts and recaps the release notes; the operator does not have to write them. Short, in English: a summary, the highlights, the runes and their versions, breaking changes with migration, known issues, and a link to the full changelog.

---

**Next →** [journey.md](journey.md) — the road of everyone who builds with DEVNEET.
