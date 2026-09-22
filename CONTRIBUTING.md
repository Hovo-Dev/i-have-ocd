# Contributing

Small, bounded PRs. One concern each.

## Translations (most wanted)

The README is translated under `.github/readme/README.<code>.md`. To add a language:

1. Copy `README.md` to `.github/readme/README.<code>.md` (BCP-47: `de`, `pt-BR`, `zh-CN`).
2. Translate the prose. **Do not translate:** code blocks, file paths, CLI commands, the rule keywords `Open:` / `Changed:` / `Verified:` / `Not touched:`, or the skill name `i-have-ocd`.
3. In your file's flag row, make your own language `<strong>` instead of a link, point 🇬🇧 at `../../README.md`, and point siblings at `README.<code>.md`.
4. Add your flag to the row in the root `README.md`, alphabetically by code.
5. Fix relative links: from `.github/readme/`, the skill is `../../skills/i-have-ocd/SKILL.md`.

Native or fluent speakers only, please. A machine-translated README is worse than no README — say in your PR which you are.

## Adding hedge phrases

`rules/hedges.json` maps violation phrases to the rule each one breaks, per language. It is what makes `/ocd-check` work outside English.

If you add or fix a translation, add that language's phrases too — a translated README without phrases is decoration; with them, the skill actually works for that language's speakers. Keep entries short and lowercase where the script has case, and prefer the phrasing an assistant would actually produce over the dictionary form.

Every category must list every language in `languages`. The check in `AGENTS.md` enforces it.

## Changing the rules

`skills/i-have-ocd/SKILL.md` is the source of truth. If you change it:

- Copy it to `.cursor/skills/i-have-ocd/SKILL.md`. The two must stay identical.
- Update the numbered list in `README.md` if a rule's summary changed.
- Say in the PR which translated READMEs your change made stale. Do not silently leave them wrong.

A rule earns its place by naming a failure mode you can demonstrate. "Be more precise" is not a rule; "never say *should work*, say what you ran and what it printed" is.

## Before you open the PR

```bash
python3 -c "import json; [json.load(open(f)) for f in ['plugin.json','.claude-plugin/plugin.json','.claude-plugin/marketplace.json','.codex-plugin/plugin.json','.agents/plugins/marketplace.json']]; print('manifests OK')"
diff skills/i-have-ocd/SKILL.md .cursor/skills/i-have-ocd/SKILL.md && echo "mirror in sync"
git diff --check
```

Report what you ran and what it printed. Given what this repo is about, a PR that claims a check it did not run is the one thing that will definitely get sent back.

## AI-assisted contributions

Welcome, and please say so in the PR. Then read your own diff before submitting — you are accountable for it, not the model.
