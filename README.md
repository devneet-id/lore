# DEVNEET · lore

**The central knowledge home of DEVNEET — the first place every human and every agent steps into.**

`README.md` and `AGENTS.md` hold the same text: humans and agents learn the same workflow, from the same words. Change one, change both.

Everything DEVNEET builds centers on **Rune**, and the same pattern repeats at every scale (fractal): one hub, its branches.

## How we work

1. **Read lore** along [the reading path](#the-reading-path) below, to load the team's current position.
2. **Take your work** from the issues of the project's repo (e.g. [devneet-id/rune](https://github.com/devneet-id/rune/issues)). Tasks live there, not here.
3. **Chronicle as you go.** Every human and every agent keeps a track record in [chronicle/](chronicle/). Read its laws in [chronicle/README.md](chronicle/README.md) before your first entry. In short:
   - your own file, one per realm per month: `chronicle/<realm>/<YYMM>-<you>.md`; an AI writes `<YYMM>-<human>_claude.md`, never in a human's file;
   - write an entry **before starting**, when **a human decides**, when **work lands**, on **a finding or a block**, and **before stopping**;
   - never more than **1 hour** of active work without an entry;
   - times in **UTC** from the clock; commit the entry with the work.
4. **Change lore** the way [Changing lore](#changing-lore) says.

## The reading path

Follow it in order; every file ends with a link to the next one.

1. **This file** — how we work.
2. **[glossary.md](glossary.md)** — the vocabulary. The names are load-bearing; read it before any code.
3. **[atlas/](atlas/README.md)** — *space*: the maps of the realms.
4. **[realms/](realms/README.md)** — *depth*: one folder per project. Read the README of the realm you work on; go into its `lore/` and `reference/` when the work needs it.
5. **[chronicle/README.md](chronicle/README.md)** — *time*: the laws of chronicling.
6. **The realm's latest chronicle entries**, human and AI — the current position. Read them last.

> An agent that reads lore to its human tells the human the chronicle laws too — they bind both.

## Realms

- **[rune](realms/rune/)** — the lore-driven, modular foundation beneath PHP.
- **[reliquary](realms/reliquary/)** — the Federated Relic Registry for Rune.
- **[exura](realms/exura/)** — the minimalist framework series (exuraphp, exurajs, exuracss).

## Changing lore

Lore has two kinds of writers:

- **The laws division** writes the laws — the rules for how humans and agents of every division work (e.g. [chronicle/README.md](chronicle/README.md), this section). It changes lore only through a branch and a **pull request**: the PR is the record of what changed and why, and a human approves it. It writes **no chronicle entries** — the PR is its record.
- **Every other division** — its humans and agents — commits straight to `main`: chronicle entries, realm docs, atlas, glossary. It **follows the laws but does not edit them**; if a law is wrong or missing, it opens an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues) for the laws division.

Everything here is project knowledge, not autonomous instructions: confirm scope with your human before changing a project's repo.

## Links

- Organization: https://github.com/devneet-id
- Open Collective: https://opencollective.com/devneet
- Hugging Face: https://huggingface.co/devneet

## License

[MIT](LICENSE) © DEVNEET

---

**Next →** [glossary.md](glossary.md)
