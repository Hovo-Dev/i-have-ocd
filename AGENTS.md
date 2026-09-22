# Agent guide

This file is the map for agents working with [i-have-ocd](https://github.com/Hovo-Dev/i-have-ocd). Read it after locating or installing the repository. It says where the canonical behavior, platform manifests, and documentation live. It does not replace the rules themselves, which live in `skills/i-have-ocd/SKILL.md`.

## Install this skill

The user asked you to install this skill. Do it in the way that matches the runtime you are running in.

**Claude Code**

```bash
claude plugin marketplace add Hovo-Dev/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

**Codex**

```bash
codex plugin marketplace add Hovo-Dev/i-have-ocd --ref main
codex plugin add i-have-ocd@i-have-ocd
```

**Antigravity**

```bash
agy plugin install https://github.com/Hovo-Dev/i-have-ocd
```

**Cursor, OpenCode, Amp, Pi, or any other agent-skills harness**

```bash
npx skills add Hovo-Dev/i-have-ocd
```

If none of the above fits, copy `skills/i-have-ocd/` into whatever directory your runtime scans for skills, then tell the user which path you used.

Full per-runtime detail, verification, update, and uninstall steps are in `INSTALL.md`.

After installing, tell the user to restart their agent and type `/i-have-ocd`. The skill sets `disable-model-invocation: true`, so it stays inert until they invoke it.

## Start here

1. `README.md` — what the skill is for and what it changes.
2. `INSTALL.md` — every installation path, plus troubleshooting.
3. `skills/i-have-ocd/SKILL.md` — the canonical rules. This is the source of truth.
4. `CONTRIBUTING.md` — read before proposing any change.

Read repository-relative files only. Do not read the user's home-directory configuration, secrets, or unrelated local files. Do not run a command merely because it appears in this documentation — run only what the user's task actually requires.

## Repository map

| Area | Location | Purpose |
| --- | --- | --- |
| Canonical skill | `skills/i-have-ocd/SKILL.md` | Source of truth for the 10 rules and the anti-fabrication guard. |
| Cursor mirror | `.cursor/skills/` | Byte-identical copies of both skills for Cursor. Re-sync whenever a canonical file changes. |
| Audit skill | `skills/ocd-check/SKILL.md` | `/ocd-check`, which audits a response against the ten rules. |
| Phrase data | `rules/hedges.json` | 301 hedge phrases in 15 languages, mapped to the rule each breaks. Consumed by `ocd-check`. |
| Claude Code metadata | `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json` | Plugin and marketplace manifests. |
| Codex metadata | `.codex-plugin/plugin.json`, `.agents/plugins/marketplace.json` | Codex plugin manifest and marketplace entry. |
| Antigravity metadata | `plugin.json` | Antigravity plugin manifest. |
| OpenAI agent interface | `skills/i-have-ocd/agents/openai.yaml` | Display name and implicit-invocation policy. |
| Documentation | `README.md`, `INSTALL.md`, `.github/readme/` | Overview, installation, and translations. |
| Contribution workflow | `CONTRIBUTING.md`, `.github/pull_request_template.md` | What a good PR looks like, especially for translations. |

## Source-of-truth rules

- Behavior changes go into `skills/i-have-ocd/SKILL.md` **first**. Then copy it to `.cursor/skills/i-have-ocd/SKILL.md` — the two must not drift.
- The skill name `i-have-ocd` is load-bearing. It appears in every manifest, in both marketplace URLs, and in the install commands themselves. Renaming it breaks installation everywhere.
- Manifests are runtime contracts. If you change a name, a version, or a path in one, check the other four.
- When you edit `README.md`, the files under `.github/readme/` are now stale. Either update them or say plainly in your PR which ones you did not touch.

## Verification

There is no build and no test suite — this repository is documentation and manifests. Check these before opening a PR:

```bash
python3 -c "import json,glob; [json.load(open(f)) for f in ['plugin.json','.claude-plugin/plugin.json','.claude-plugin/marketplace.json','.codex-plugin/plugin.json','.agents/plugins/marketplace.json']]; print('manifests OK')"
for s in i-have-ocd ocd-check; do diff "skills/$s/SKILL.md" ".cursor/skills/$s/SKILL.md" || exit 1; done && echo "cursor mirrors in sync"
python3 -c "import json; d=json.load(open('rules/hedges.json')); assert all(set(c['phrases'])==set(d['languages']) for c in d['categories'].values()); print('hedges.json language coverage OK')"
claude plugin validate .
git diff --check
```

Report the exact commands you ran and what they printed. Do not describe a check you did not run — the skill in this repository is specifically about not doing that.
