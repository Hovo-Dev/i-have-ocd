<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./logo-dark.png">
    <img src="./logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Certainty-shaped outputs. No OCD diagnosis needed!</strong>
</p>
<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/Hovo-Dev/i-have-ocd?style=flat" alt="License"></a>
  <a href="https://github.com/Hovo-Dev/i-have-ocd/stargazers"><img src="https://img.shields.io/github/stars/Hovo-Dev/i-have-ocd?style=flat" alt="Stars"></a>
</p>

<p align="center">
  <strong title="English" aria-label="English">🇬🇧</strong> ·
  <a href=".github/readme/README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳</a> ·
  <a href=".github/readme/README.es.md" title="Español" aria-label="Español">🇪🇸</a> ·
  <a href=".github/readme/README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷</a> ·
  <a href=".github/readme/README.ja.md" title="日本語" aria-label="日本語">🇯🇵</a> ·
  <a href=".github/readme/README.ko.md" title="한국어" aria-label="한국어">🇰🇷</a> ·
  <a href=".github/readme/README.ru.md" title="Русский" aria-label="Русский">🇷🇺</a> ·
  <a href=".github/readme/README.fr.md" title="Français" aria-label="Français">🇫🇷</a> ·
  <a href=".github/readme/README.de.md" title="Deutsch" aria-label="Deutsch">🇩🇪</a> ·
  <a href=".github/readme/README.tr.md" title="Türkçe" aria-label="Türkçe">🇹🇷</a> ·
  <a href=".github/readme/README.et.md" title="Eesti" aria-label="Eesti">🇪🇪</a> ·
  <a href=".github/readme/README.sr.md" title="Српски" aria-label="Српски">🇷🇸</a> ·
  <a href=".github/readme/README.ka.md" title="ქართული" aria-label="ქართული">🇬🇪</a> ·
  <a href=".github/readme/README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href=".github/readme/README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

## Install

Copy/paste into your CLI prompt:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Or 🔗 [check the installation instructions](INSTALL.md).

## What it does

Your agent says *"Done — that should work now!"* and you go and check anyway. You have to. Nothing in that sentence tells you whether it ran the tests or just believes in itself.

This skill takes that sentence away from it. What you get instead:

- **The files and lines that changed.** `src/auth.ts:42-58`, not "the auth logic."
- **The command it ran, and what that printed.** If it ran nothing, it says so in those words.
- **What it deliberately left alone** — so you know how far the change reached.
- **One list at the bottom for anything still unresolved.** When nothing is, the list says `none`.

The point is that you read it once.

## What changes

<table>
<tr>
<td width="50%">

## Before

> I've updated the auth logic and cleaned up a few things along the way. That should fix the 401s you were seeing. There might be some edge cases around token refresh, but it's probably fine — the main path looks good now. Let me know if anything seems off!

</td>

<td width="50%">

## After

> **Changed:** `src/auth.ts:42-58` — `verifyToken` now calls `jwt.verify` with the RS256 key from `AUTH_PUBLIC_KEY`.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 passed, 0 failed.
>
> **Not touched:** session middleware, cookie config, login UI.
>
> **Open:** token refresh past 24h is untested — no test covers that path.

</td>
</tr>
</table>

## The rules

Ten of them. The unabridged version is [SKILL.md](./skills/i-have-ocd/SKILL.md).

1. State exactly what changed — file, lines, symbol.
2. Never "should work." Verified, or explicitly not verified.
3. Done or not done. No third state.
4. Name what you did not touch.
5. One answer, not a menu.
6. Unknowns go in one `Open:` list — which says `none` when it is empty.
7. No reassurance. Show the output instead.
8. Errors get an exact cause, not a restated symptom.
9. No filler affirmations.
10. Bound every answer: what it covers, what it does not.

Plus the one rule that outranks all ten: **precision is not fabrication.** Never invent a line number you did not read.

## `/ocd-check` — audit any answer

This repo ships a second skill. Point it at a response and it reports which rules that response breaks, quoting the exact span and naming the replacement.

```
Audited: previous response (en)

Rule 2 — "that should fix the 401s"
  → Replace with: the command you ran and what it printed, or "not verified: no test covers this path".

Rule 6 — no Open: list
  → Add: "Open: none." if nothing is genuinely open.

Clean: 1, 3, 4, 5, 7, 8, 9, 10.
Open: none.
```

Works on the previous answer, pasted text, a PR body, or a commit message — including ones you did not write. A clean audit reports zero violations; the skill is explicitly forbidden from inventing a finding to look thorough.

### Hedging is multilingual, so the detection is too

[`rules/hedges.json`](rules/hedges.json) carries **301 hedge phrases across 15 languages**, each mapped to the rule it breaks. *Debería funcionar*, *sollte funktionieren*, *çalışması lazım*, *требало би да ради* and *動くはずです* are the same violation as *should work* — and `/ocd-check` catches them in whichever language your assistant answered in.

It is a plain MIT-licensed JSON file. Point a linter, a git hook, or your CI at it; you do not need the skill to use the data.

## A note on the name

The joke is the name. The skill is not a joke, and it deliberately does not do reassurance — seeking reassurance is the compulsion, not the cure. What it does instead is refuse to leave a claim unverified, which is a thing every reader benefits from and a thing that nobody's assistant does by default.

## Tune it

Fork, edit `skills/i-have-ocd/SKILL.md`, then swap your copy in:

```bash
claude plugin uninstall i-have-ocd            # drop the upstream copy first:
claude plugin marketplace remove i-have-ocd   # fork and upstream share both names
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Restart your coding assistant, then re-invoke `/i-have-ocd`.

## Contributing

Translations especially welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

## Open:

Rule 6 says every answer carries an `Open:` list, and that the list reads `none` when it is empty. That applies to this README.

- **13 of the 14 translations are AI-drafted and not native-reviewed.** Armenian is the only one the author can read. Corrections from native speakers are the most useful PR this repo can get.
- **The phrase lists are incomplete by construction.** 301 entries catch common hedging. Absence of a match is not proof of absence of hedging.
- **There is no eval suite.** These rules have not been measured across models. The before/after example is illustrative, not a benchmark result.
- **`/ocd-check` checks shape, not truth.** It cannot confirm that a cited line number exists. A well-shaped lie passes it.

Open: the four items above.

## Credits

The shape of this repo — one `SKILL.md`, a before/after table, per-agent install paths — follows [i-have-adhd](https://github.com/ayghri/i-have-adhd) by [Ayoub Ghriss](https://github.com/ayghri), which got there first and is MIT licensed. The rules here are written from scratch and pull the opposite way: that skill optimizes for *starting* (lead with the action, cut everything else), this one optimizes for *closing* (nothing unverified, nothing unbounded). They pair well. Install both.

## License

[MIT](LICENSE).

Star ⭐ if it saved you one round of "wait, did it actually run the tests?"
