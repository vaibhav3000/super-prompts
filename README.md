# super-prompts

A shared library of tested prompts and Claude Code skills. Copy what you need, improve what you use, and record what works.

## What's inside

| Folder | Purpose |
|---|---|
| `prompts/` | Copy-paste prompts, grouped by category |
| `skills/` | Reusable Claude Code skills (`SKILL.md`) |
| `.claude/commands/` | Slash commands for Claude Code |
| `templates/` | Starting point for new prompts |

## Index

| Name | Type | Category | Path | Status |
|---|---|---|---|---|
| Humanized presentations | Prompt | presentations | `prompts/presentations/humanized-presentations.md` | Planned |
| Knowledge transfer | Prompt | knowledge-transfer | `prompts/knowledge-transfer/knowledge-transfer.md` | Planned |

When an entry lands, link its name to the file and set Status to `Ready`.

## How to add or edit a prompt on GitHub (no terminal needed)

1. **Open the file or folder.** To edit a prompt, open it and click the pencil icon. To add one, go to the right folder under `prompts/`, click **Add file > Create new file**, name it `your-prompt-name.md`, and paste in the contents of `templates/PROMPT_TEMPLATE.md`. If you don't have write access, GitHub will offer to fork the repo first.
2. **Make your changes.** Fill in the template, bump `version`, update `last_tested`, and add a Changelog line.
3. **Propose the change.** Click **Commit changes**, pick **Create a new branch**, and open a pull request. Add or update the row in the Index above in the same pull request.

To just use a prompt, open its file and click the copy button on the code block.

## Use a skill

Claude Code loads skills from `~/.claude/skills/`. From the repo root, copy one there (replace `<skill-name>`; rerun after pulling to sync updates):

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null; Copy-Item -Recurse -Force "skills\<skill-name>" "$HOME\.claude\skills\"
```

```bash
mkdir -p ~/.claude/skills && cp -r "skills/<skill-name>" ~/.claude/skills/
```

See `skills/README.md` for the skill format.

## Slash commands

Claude Code turns each Markdown file in `.claude/commands/` into a slash command, so `review-pr.md` becomes `/review-pr`. Keep only command files in that folder, since any other `.md` file (a README included) also shows up as a command.

Create `.claude/commands/command-name.md`:

```markdown
---
description: One line shown in the command menu.
argument-hint: [topic]
---

Instructions for Claude. $ARGUMENTS is replaced with whatever you type after the command.
```

- In this repo: open Claude Code in the repo folder and type `/command-name`.
- In another project: copy the file to that project's `.claude/commands/`, or to `~/.claude/commands/` to use it everywhere.

Add a row to the Index for each new command.

## Conventions

- File names are lowercase and hyphenated, like `code-review-checklist.md`.
- One prompt per file, following the template.
- List only models you actually tested in `best_models`.
- No em dashes or en dashes. Use commas, colons, or parentheses instead.
- No AI attribution or `Co-Authored-By` trailers in commits or docs.
- Keep it short and practical.
