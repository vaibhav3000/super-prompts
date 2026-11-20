# Skills

Reusable Claude Code skills. Each skill is a folder with a `SKILL.md` file.

## Layout

```text
skills/
  skill-name/
    SKILL.md        required
    reference.md    optional supporting files
```

`SKILL.md` starts with frontmatter:

```markdown
---
name: skill-name
description: What the skill does and when Claude should use it.
---

Instructions for Claude go here.
```

The `description` decides when Claude picks the skill up, so name the trigger clearly.

## Install a skill

Claude Code does not read this `skills/` folder directly. Copy a skill's folder to one of these:

- `~/.claude/skills/skill-name/` (on Windows, `%USERPROFILE%\.claude\skills\skill-name\`) to use it in every project.
- `<your-project>/.claude/skills/skill-name/` to use it in one project and share it with that repo.

Quick copy to your user folder, run from the repo root (replace `<skill-name>`; rerun after pulling to sync updates):

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null; Copy-Item -Recurse -Force "skills\<skill-name>" "$HOME\.claude\skills\"
```

```bash
mkdir -p ~/.claude/skills && cp -r "skills/<skill-name>" ~/.claude/skills/
```

Claude then uses the skill when a task matches its description, or you can call it directly with `/skill-name`.

## Add a skill here

Create `skills/skill-name/SKILL.md`, test it in a real session, and add a row to the Index in the root `README.md`.
