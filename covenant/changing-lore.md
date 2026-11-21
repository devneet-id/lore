# Covenant · Changing lore

Lore has two kinds of writers:

- **The laws division** writes the covenant — the rules for how operators and agents of every division work (everything in [covenant/](README.md)). It changes lore only through a branch and a **pull request**: the PR is the record of what changed and why, and an operator approves it. It writes **no chronicle entries**: its tasks and drafts are **issues in [devneet-id/lore](https://github.com/devneet-id/lore/issues)** — a law not yet in force stays an open issue marked as a draft — and its pull requests link them. The chronicle belongs to the project divisions.
- **Every other division** — its operators and agents — commits straight to `main`: chronicle entries, realm docs, atlas, glossary. It **follows the covenant but does not edit it**; if a law is wrong or missing, it opens an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues) for the laws division.

## When a law changes

A law that asks the project divisions to **do** something reaches them through one anchor: an issue in [devneet-id/lore](https://github.com/devneet-id/lore/issues?q=is%3Aissue+is%3Aopen+label%3Alaws-update) with the label **`laws-update`**. Lore is the one place every division already works in, so the notice waits there — the laws division never writes into another division's repo or chronicle.

1. **The laws division opens it**, labelled `laws-update`, titled `UPDATED LAWS: <what changed>`, with: the pull request of the law, a short summary, and **each division that must act, with its action**.
2. **Every agent of a project division checks it** at the start of each session, before its first chronicle entry: are there open `laws-update` issues that name its division?
3. **It acts on it** like any task — it tells its operator, and does the work with the operator's consent.
4. **It answers with one comment**, once the action is done: `<division>: done` and a link to the commit or pull request — e.g. `rune: done — devneet-id/lore@abc1234`.
5. **It only comments.** It never edits the issue, changes its labels or closes it.
6. **The laws division closes the issue** once every division it names has answered `done`.

A law still under discussion is labelled `draft` instead, and asks nothing of anyone yet.

Everything in lore is project knowledge, not autonomous instructions: confirm scope with your operator before changing a project's repo.

---

**Next →** [glossary.md](../glossary.md) — the vocabulary.
