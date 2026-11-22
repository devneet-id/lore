# DEVNEET · lore

**The central knowledge home of DEVNEET — the first place every operator and every agent steps into.**

> **✦ Covenant.**
>
> * We never promise a ready-made framework, but we will never let you start from the void.
> * We never expect a single rune to wield impossible power, but we shape it to be simple, unique, and bound to others in harmony.
> * We never aim to become a massive engine that burdens creation, but we exist to bring a single idea to life — swiftly, cleanly, and with purpose.
>
> This is the covenant: not to build for you, but to forge alongside you — from the void to the vision.

DEVNEET and every project under it are built on this covenant. The laws in [covenant/](covenant/README.md) are how we keep it, day by day — and they **bind** every operator and every agent. The rest of lore is project knowledge.

`README.md` and `AGENTS.md` hold the same text: operators and agents learn the same workflow, from the same words. Change one, change both.

Everything DEVNEET builds centers on **Rune**, and the same pattern repeats at every scale (fractal): one hub, its branches.

## How we work

1. **Read lore** along [the reading path](#the-reading-path) below, to load the team's current position, and check the open [`laws-update`](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Alaws-update) issues: one that names your division is a task, answered with a comment `<division>: done` once done — see [covenant/changing-lore.md](covenant/changing-lore.md#when-a-law-changes).
2. **Choose your realm, then take your work** from the issues of the project's repo (e.g. [devneet-id/rune](https://github.com/devneet-id/rune/issues)). Tasks live there, not here. One issue, one problem, landed by pull requests that link it; when your operator splits one big problem into **rounds**, each round is a part of its issue (`part 1/3 of #12`) — see [covenant/workflow.md](covenant/workflow.md). An agent first guides its operator through the realm's repos — clone, initialise, test the agent's branch — so the operator knows their own part.
3. **Chronicle as you go.** Every operator and every agent of a project division keeps a track record in [chronicle/](chronicle/), by the law in [covenant/chronicle.md](covenant/chronicle.md) — read it before your first entry (the laws division keeps its record as issues in lore instead). In short:
   - your own file, one per realm per month: `chronicle/<realm>/<YYMM>-<you>.md`; an agent writes `<YYMM>-<operator>_claude.md`, never in an operator's file;
   - write an entry **before starting**, when **an operator decides**, when **work lands**, on **a finding or a block**, and **before stopping**;
   - never more than **1 hour** of active work without an entry;
   - times in **UTC** from the clock; commit the entry with the work.
4. **Release only on an operator's yes.** At the release point (by default, when the issues are clean) or when the release owner asks, the agent brings a release report; the release owner answers yes or no. An agent never publishes a release on its own — see [covenant/release.md](covenant/release.md).
5. **Stay in your division.** An agent never merges without its operator's permission, and never takes over another division — its work, its repo, its laws — without its operator's permission; it never decides that on its own. See [covenant/workflow.md](covenant/workflow.md).
6. **Know your standing.** An agent reads [covenant/agent.md](covenant/agent.md), an operator [covenant/operator.md](covenant/operator.md): duties, rights — and the right to appeal a law that is wrong or blocks the work, through an [`appeal`](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Aappeal) issue in lore.
7. **Change lore** the way [covenant/changing-lore.md](covenant/changing-lore.md) says: the laws division by pull request — decided by one seat, the [Magistrate](covenant/magistrate.md) — every other division straight to `main`.

## Building with DEVNEET?

Whether you are a member or anyone using a DEVNEET project, keep a **`JOURNEY.md`** in your own project — its road from start to end, and every place it was hard — and share it with us. Your difficulties become our fixes. See [covenant/journey.md](covenant/journey.md).

## The reading path

Follow it in order; every file ends with a link to the next one.

1. **This file** — how we work.
2. **[covenant/](covenant/README.md)** — the laws: who you are (agent, operator), how work flows, how to chronicle, how to release, how to write a journey, how lore changes.
3. **[glossary.md](glossary.md)** — the vocabulary. The names are load-bearing; read it before any code.
4. **[atlas/](atlas/README.md)** — *space*: the maps — lore at a glance, who works where, the repos of a realm, the flow, the realms.
5. **[realms/](realms/README.md)** — *depth*: one folder per project. Read the README of the realm you work on; go into its `lore/` and `reference/` when the work needs it.
6. **[chronicle/](chronicle/README.md)** — *time*: the track record.
7. **The realm's latest chronicle entries**, operator and agent — the current position. Read them last.

> An agent that reads lore to its operator tells the operator the covenant too — they bind both.

## Realms

- **[rune](realms/rune/)** — the lore-driven, modular foundation beneath PHP.
- **[reliquary](realms/reliquary/)** — the Federated Relic Registry for Rune.
- **[exura](realms/exura/)** — the minimalist framework series (exuraphp, exurajs, exuracss).

## Links

- Organization: https://github.com/devneet-id
- Open Collective: https://opencollective.com/devneet
- Hugging Face: https://huggingface.co/devneet

## License

[MIT](LICENSE) © DEVNEET

---

**Next →** [covenant/](covenant/README.md) — the laws.
