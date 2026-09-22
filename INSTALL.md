# Install i-have-ocd

Pick your agent below. The skill is a single file — every path here just puts it somewhere your agent looks.

<details>
<summary><strong>Claude Code</strong></summary>

### Install

```bash
claude plugin marketplace add Hovo-Dev/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Type `/i-have-ocd`.

### Verify

```bash
claude plugin list
```

### Update

```bash
claude plugin marketplace update i-have-ocd
```

### Uninstall

```bash
claude plugin uninstall i-have-ocd
claude plugin marketplace remove i-have-ocd
```

To silence it without removing it: `claude plugin disable i-have-ocd`.

### Always-on (optional)

Add to `~/.claude/CLAUDE.md`:

```markdown
## Output style

Always follow the rules in the `i-have-ocd` skill: exact file and line for every change, verified or explicitly not verified, no reassurance, every open item in one `Open:` list.
```

</details>

<details>
<summary><strong>Codex</strong></summary>

### Install

```bash
codex plugin marketplace add Hovo-Dev/i-have-ocd --ref main
codex plugin add i-have-ocd@i-have-ocd
```

Type `$i-have-ocd`.

### Verify

```bash
codex plugin list
```

### Update

```bash
codex plugin marketplace upgrade i-have-ocd
codex plugin remove i-have-ocd
codex plugin add i-have-ocd@i-have-ocd
```

### Uninstall

```bash
codex plugin remove i-have-ocd
codex plugin marketplace remove i-have-ocd
```

### Always-on (optional)

Add to `~/.codex/AGENTS.md`:

```markdown
## Output style

Always follow the rules in the `i-have-ocd` skill: exact file and line for every change, verified or explicitly not verified, no reassurance, every open item in one `Open:` list.
```

</details>

<details>
<summary><strong>Antigravity (<code>agy</code>)</strong></summary>

### Install

```bash
agy plugin install https://github.com/Hovo-Dev/i-have-ocd
```

### Verify

```bash
agy plugin list
```

### Update

```bash
agy plugin uninstall i-have-ocd
agy plugin install https://github.com/Hovo-Dev/i-have-ocd
```

### Uninstall

```bash
agy plugin uninstall i-have-ocd
```

To silence it without removing it: `agy plugin disable i-have-ocd`.

### Always-on (optional)

Add to `~/.gemini/GEMINI.md`:

```markdown
## Output style

Always follow the rules in the `i-have-ocd` skill: exact file and line for every change, verified or explicitly not verified, no reassurance, every open item in one `Open:` list.
```

</details>

<details>
<summary><strong>Cursor, OpenCode, Amp, Pi, and any other agent-skills harness</strong></summary>

Any harness that indexes agent skills can load this. Substitute your own agent for `-a <agent>`.

### Install

```bash
npx skills add Hovo-Dev/i-have-ocd                  # this workspace
npx skills add Hovo-Dev/i-have-ocd -g               # all projects
npx skills add Hovo-Dev/i-have-ocd -a cursor -y     # one agent only
npx skills add Hovo-Dev/i-have-ocd -a opencode -y
```

Open a fresh chat, type `/i-have-ocd`.

No CLI? Drop the folder into your agent's skills directory yourself:

```bash
git clone https://github.com/Hovo-Dev/i-have-ocd
mkdir -p ~/.cursor/skills     # Cursor. Use .agents/skills for OpenCode, or your agent's own path
cp -R i-have-ocd/skills/i-have-ocd ~/.cursor/skills/
```

### Verify

```bash
npx skills list
npx skills ls -g    # if installed globally
```

### Update

```bash
npx skills update i-have-ocd
npx skills update -g    # if installed globally
```

### Uninstall

```bash
npx skills remove i-have-ocd
npx skills remove i-have-ocd -g    # if installed globally
```

### Always-on (optional)

Put this wherever your agent keeps standing rules — Cursor under **Settings → Rules → User Rules** (or a `.cursor/rules/` file with `alwaysApply: true`), OpenCode in `~/.config/opencode/AGENTS.md`.

```markdown
## Output style

Always follow the rules in the `i-have-ocd` skill: exact file and line for every change, verified or explicitly not verified, no reassurance, every open item in one `Open:` list.
```

</details>

## How activation works

1. **Sitting there uninvoked.** Zero effect. The frontmatter carries `disable-model-invocation: true`, which keeps the skill out of the model's view entirely — it cannot reach for these rules on its own.
2. **After you type `/i-have-ocd`.** Active for the rest of that session. Say "stop ocd mode" or "normal mode" to drop it.
3. **With the always-on config above.** Active from the first message of every session.

There is no partial state, which is fitting. Off until you switch it on.

## Troubleshooting

**No `/i-have-ocd` in autocomplete.** The plugin index is built when the agent boots, so restart it.

**`claude plugin marketplace add` errors out.** It wants the `owner/repo` shorthand. If you pass a local path, aim it at the repo root — not the `.claude-plugin/` folder inside it.

**Installed, but answers still hedge.** Start a new session first. If the drift survives that, sharpen the wording in `skills/i-have-ocd/SKILL.md` — the rules are yours to edit.

**It started inventing line numbers.** That is the failure mode the skill warns about in *Precision is not fabrication*. Re-invoke `/i-have-ocd` in a fresh session; if it persists, strengthen that section in your fork.

**Different rules wanted.** Fork it, rewrite `skills/i-have-ocd/SKILL.md`, then point the marketplace at your copy: `claude plugin marketplace add <your-username>/i-have-ocd`.

**`npx skills add` ran but nothing appeared.** Skills are indexed when a session starts, so open a new chat. Then check two things: the folder actually landed in the directory your agent scans (`~/.cursor/skills/` for Cursor, `.agents/skills/` for OpenCode), and the `name` in the frontmatter matches the folder's name.

---

The install layout above follows [i-have-adhd](https://github.com/ayghri/i-have-adhd) by [Ayoub Ghriss](https://github.com/ayghri), MIT licensed.
