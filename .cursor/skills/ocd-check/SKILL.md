---
name: ocd-check
description: Audit a response against the i-have-ocd rules and report each violation with its rule number, the exact quoted span, and the replacement. Works on the previous answer, pasted text, a PR body, or a commit message. Detects hedging in 11 languages. Invoke with /ocd-check.
disable-model-invocation: true
---

# ocd-check

Audit writing against the ten rules in `i-have-ocd`. Report what breaks them. Do not rewrite unless asked.

## Target

Default: the assistant response immediately preceding this invocation.

Named alternatives: pasted text, a file path, a PR description, a commit message, an issue comment. If no target can be identified, ask once, then stop.

## Procedure

1. Load `rules/hedges.json` from this repository. It carries violation phrases for four of the ten rules across 11 languages. If it is not reachable, audit from the rule text alone and record that under `Open:`.
2. Detect the language of the target. Use that language's lists. If the text mixes languages, check every language present — a Spanish answer saying "debería funcionar" breaks rule 2 exactly as hard as "should work."
3. Walk the ten rules in order.
4. Quote the offending span **exactly as written**. Never paraphrase a violation into existence.
5. Give each violation a concrete replacement. Not "be more precise" — the actual sentence that belongs there, or the command whose output would settle the question.

## Checked against the phrase lists

| Rule | Category in `hedges.json` | Catches |
| --- | --- | --- |
| 2 | `unverified_claim` | A claim offered as probable rather than run: "should work", "probably fine". |
| 3 | `partial_state` | Completion that is neither done nor not done: "mostly done", "almost there". |
| 7 | `reassurance` | Comfort standing in for evidence: "don't worry", "all good". |
| 9 | `filler_affirmation` | Praise carrying no information: "great question", "good catch". |

## Checked by reading

- **Rule 1** — Does every claimed change name a file, and where possible a line range and a symbol? A change described only at summary level is a violation.
- **Rule 4** — Is there a line naming what was *not* touched? Its absence is itself the violation.
- **Rule 5** — Are options handed over without a pick, where the text shows enough information to pick?
- **Rule 6** — Is there an `Open:` list? A missing list is a violation even when nothing is open — the answer is then required to say `Open: none.`
- **Rule 8** — Does each error carry a mechanism (file, line, condition), or only a restated symptom?
- **Rule 10** — Does the answer say what it covers and what it does not?

## Output

Report in the shape the rules demand of everything else:

```
Audited: previous response (en)

Rule 2 — "that should fix the 401s"
  → Replace with: the command you ran and what it printed, or "not verified: no test covers this path".

Rule 4 — no line naming untouched scope
  → Add: "Not touched: <the modules you did not open>".

Rule 6 — no Open: list
  → Add: "Open: none." if nothing is genuinely open.

Clean: 1, 3, 5, 7, 8, 9, 10.
Open: none.
```

A clean audit is a valid result. Report `0 violations` and list all ten as clean. **Do not manufacture a finding to look thorough** — inventing a violation breaks the rule that outranks all ten.

## Limits

State these when they apply, under `Open:`:

- This checks **shape, not truth**. It cannot confirm that `src/auth.ts:42` says what the text claims, or that a reported test run happened. A well-shaped lie passes.
- A phrase list is a tripwire, not a judge. "It should work" quoted from someone else, or inside a code sample, is not a violation. Read the span before counting it.
- The lists are incomplete by construction. Absence of a match is not proof of absence of hedging.
