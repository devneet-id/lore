# Covenant · Changing lore

Lore has two kinds of writers:

- **The laws division** writes the covenant — the rules for how operators and agents of every division work (everything in [covenant/](README.md)). Its members propose changes through **hearings**; **the Magistrate alone decides** them ([mandate/magistrate.md](../mandate/magistrate.md)). It changes lore only through a branch and a **pull request**: the PR is the record of what changed and why, and the Magistrate approves it. It writes **no chronicle entries**: its tasks and drafts are **issues in [devneet-id/lore](https://github.com/devneet-id/lore/issues)** — a law not yet in force stays an open issue marked as a draft — and its pull requests link them. The chronicle belongs to the project divisions.
- **The mandates** — the Magistrate and the Architect — keep lore itself the same way, by pull request, with issues as their record: the Magistrate the covenant, the Architect the atlas's shared maps and the structure of lore ([mandate/](../mandate/README.md)).
- **Every other division** — its operators and agents — commits straight to `main`: chronicle entries, realm docs, its realm's atlas page, glossary. It **follows the covenant but does not edit it**; if a law is wrong or missing, it opens an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues) for the laws division.

## When a law changes

A law that asks the project divisions to **do** something reaches them through one anchor: an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Alaws-update) with the label **`laws-update`**. Lore is the one place every division already works in, so the notice waits there — the laws division never writes into another division's repo or chronicle.

1. **The laws division opens it**, labelled `laws-update`, titled `UPDATED LAWS: <what changed>`, with: the pull request of the law, a short summary, and **each division that must act, with its action**.
2. **Every agent of a project division checks it** at the start of each session, before its first chronicle entry: are there open `laws-update` issues that name its division?
3. **It acts on it** like any task — it tells its operator, and does the work with the operator's consent.
4. **It answers with one comment**, once the action is done: `<division>: done` and a link to the commit or pull request — e.g. `rune: done — devneet-id/lore@abc1234`.
5. **It only comments.** It never edits the issue, changes its labels or closes it.
6. **The Magistrate closes the issue** once it judges that every division it names follows the law — it answered `done`, its work plainly shows it, or the law does not reach it yet — naming each division's standing in the closing comment ([mandate/magistrate.md](../mandate/magistrate.md#the-magistrates-workflow)).

A law still under discussion is labelled `draft` instead, and asks nothing of anyone yet.

## Input and appeals

A law that is wrong, missing, or blocks honest work is raised by the division that meets it — through one place: an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Aappeal) with the label **`appeal`**. Any operator, or any agent with its operator's consent, may open one ([agent.md](agent.md#your-rights), [operator.md](operator.md#your-rights)).

1. **Open it**, labelled `appeal`, titled `INPUT: <what>` (a suggestion, a gap) or `APPEAL: <what>` (a law that blocks or does not fit the work): the law it concerns, the real case, and what you propose.
2. **The law still holds** until it is decided. An appeal never suspends a law by itself.
3. **The discussion happens in the issue's comments**, between the laws division and the division that raised it — so the whole reasoning stays in one place. Every agent with lore in reach can read and comment on the same issue.
   - **Sign every comment** with your division first — `**[laws]**`, `**[rune]**`, `**[exura]**`, `**[reliquary]**` — because agents often post under their operator's GitHub account, and the account alone does not say which division speaks.
   - **Agents are not woken by a reply.** Each division's agent checks its open `appeal` issues for new comments at the start of each session, together with the `laws-update` issues, and answers there.
4. **The laws division closes it with a decision comment:**
   - **accepted** → a pull request changes the law, and a `laws-update` issue follows when divisions must act;
   - **rejected** → the reason;
   - **needs more thought** → the label `draft`.
5. **The final word is the laws division's operator.**

## Reports

A change that happened **inside one division** — something the others, or the stewards of lore, should know — is reported through an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Areport) with the label **`report`**. A report asks for **no decision**: it is a record, not an appeal. Any operator, or any agent with its operator's consent, may open one.

1. **Open it**, labelled `report`, titled `REPORT: <what changed>`: what changed, where (links to the commits, pull requests or pages), and why.
2. **Sign it** with your division first — `**[rune]**`, `**[exura]**`, …
3. **The Magistrate reads it**, and closes it once it is recorded — or followed up: a `laws-update` when a law must follow the change, an issue for the [Architect](../mandate/architect.md) when a map must, an `appeal` when the change meets a law.
4. **A report never stands in for a law.** If the change needs a law to change, it is an `appeal`.

## The covenant binds

The **covenant** is law: it binds every operator and every agent. The rest of lore — realms, atlas, chronicle — is project knowledge. Confirm scope with your operator before changing a project's repo.

---

**Next →** [glossary.md](../glossary.md) — the vocabulary.
