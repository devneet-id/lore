# Projects

Depth, one folder per project (realm). Each has two sides:

- **`lore/`**: the story and teaching (the narrative, Act by Act where it applies).
- **`reference/`**: the technical detail (architecture, APIs, commands, formats).

Cross-project material lives up a level: the map in [atlas/](../atlas/), the vocabulary in [glossary.md](../glossary.md). The track record of the work lives in [chronicle/](../chronicle/); tasks live in each repo's issues.

## Index

- **[rune/](rune/)**: the lore-driven, modular foundation beneath PHP.
- **[reliquary/](reliquary/)**: the Federated Relic Registry for Rune.
- **[exura/](exura/)**: the minimalist framework series (exuraphp, exurajs, exuracss).

## Who reads a realm

- **Using a DEVNEET project?** The realm you use is all you need, with [covenant/journey.md](../covenant/journey.md). Its pages describe what you actually get: the released version.
- **A member working on it?** Start from its README's *Working on this realm*; go into `lore/` and `reference/` only when the work needs it ([covenant/agent.md](../covenant/agent.md#carry-little)).

## Who keeps a realm

- **Every realm is kept by its project division**, whatever its shape: one repo or several, with releases or without, code or mostly docs ([covenant/workflow.md](../covenant/workflow.md#choose-your-realm)). The division commits its realm straight to `main` ([covenant/changing-lore.md](../covenant/changing-lore.md)). No other division writes in it; a finding for another realm goes to that division as an issue.
- **A realm describes the released version.** While the work goes on, each pull request carries a *Lore* line: the realm pages it will change. After the release, the division updates them in one pass. A division that ships no release updates its realm as its work lands ([docs follow the release](../covenant/workflow.md#docs-follow-the-release)).
- **Its atlas page** (`atlas/<realm>.md`) is kept by the division too, in the shared shape the [Architect](../mandate/architect.md) keeps.

## What every realm's README has

- **What the project is**: one paragraph, for a user.
- **"Working on this realm"**, for members. The project division writes it; [covenant/workflow.md](../covenant/workflow.md) requires it. It lists:
  - the **project repos**;
  - the **repos used to develop and test them**: a `-dev` repo where there is one, or whatever the realm uses instead (another repo, a fork, a test instance, a local setup). A `-dev` repo is one way, not a must;
  - the **`-skill` repo**, where there is one;
  - how to **clone and initialise** them;
  - how to **test an agent's branch** before merging.

  The agent walks its operator through this section once ([guide the operator first](../covenant/workflow.md#guide-the-operator-first)).

> **Adding a project?** A new realm changes the structure of lore, so propose it first as an issue labelled `atlas`, for the [Architect](../mandate/architect.md). Once agreed, its division creates `realms/<name>/` with `README.md` (with *Working on this realm*), `lore/` and `reference/`, and its `chronicle/<name>/`. The Architect links it here, in the root README and in the atlas.

---

**Next →** members: the README of the realm you work on (above), then [chronicle/README.md](../chronicle/README.md). Users: the realm you use is the end of your path.
