# Release

> From a change to Packagist.

**Release owner: the Rune administrator** — the developer responsible for Rune. Whether to release is the administrator's decision, asked by the agent at the end of every round — see the [release covenant](../../../../../covenant/release.md). This page is *how* a release is cut, once the answer is yes.

A release is the footer made public. Commit the changes, tag the version the footer shows, publish it on GitHub — Packagist does the rest.

## 1. Commit
One commit per change. Group by file when several tasks touch one file.

Format: `type(scope): summary` — lower case, English, no full stop, about six words.

| Type | For |
|---|---|
| `fix` | a bug fix |
| `feat` | a new ability |
| `docs` | text, examples, Phantasm |
| `refactor` | tidy without changing behaviour |
| `chore` | remove, clean up |

Scope = the rune or runite changed: `aether`, `whisper`, `weaver`, `chanter`, `forger`, `cipher`, `keeper`, `crafter`, `specter`, `minister`, `rune`, `grimoire`, `sentinel`, `reliquary`, `awakening`, `readme`. Many places → no scope (`fix: ...`). Reasons go in the PR, not the commit title.
```bash
git add "Chanter/Entity.php"
git commit -m "fix(chanter): keep notes on casts with spells" -m "Notes are stored by cast name, so a cast with spells now shows its note."
```
Do not forget the Phantasm bump of every rune you changed ([Versioning](versioning.md)).

## 2. Read the version
Run any runite on the clean branch and read `Version=`. That is the tag: `Version=1.21.123` → `v1.21.123`. Read it from a runite without evolution mode — evolution runes count in the footer, not in the release.

## 3. Publish on GitHub
Repo `devneet-id/rune`, branch `1.x`.
1. **Releases → Draft a new release**.
2. Tag `v1.21.123` (create on publish) · target `1.x` · previous tag (e.g. `v1.21.117`).
3. Title: `v1.21.123 — <a name>` (e.g. *Cleansing of the Runes*).
4. Description: short, in English — summary, highlights, rune versions, breaking changes, full changelog link.
5. **Publish release**. GitHub adds the source `zip` and `tar.gz` itself.

## 4. Packagist
`devneet/rune` updates from new GitHub tags on its own. If the new version does not show, press **Update** on the package page. Users get it with `composer update devneet/rune`.

## Checklist
- [ ] every trial still passes (`php cast trials`)
- [ ] every changed rune has a higher Phantasm version, no `x.9 → x.10`
- [ ] `php -l` on changed PHP files; CRLF kept
- [ ] `lore` updated ([Keeping the Lore](keeping-the-lore.md))
- [ ] tag = footer `Version=`
