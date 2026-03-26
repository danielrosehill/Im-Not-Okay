Delete all demo/example data from the repository so the user can start fresh with their own voice memos.

## What gets deleted

- `input/2603/` (demo audio file)
- `raw/2603/` (demo raw transcript)
- `output/2603/` (demo edited transcript and analysis outputs)
- `project-idea/` (project concept voice memo and transcript)

## What is preserved

- All slash commands and subagents (`.claude/`)
- `CLAUDE.md` (project instructions)
- `.mcp.json` (AssemblyAI config)
- `README.md`
- `USER_PROFILE.md` (if it exists)
- The `input/`, `raw/`, and `output/` directories themselves (kept empty)

## Steps

1. Confirm with the user before deleting: "This will remove all demo data (input/2603, raw/2603, output/2603, and project-idea/). Your own data and all configuration will be preserved. Proceed?"

2. If confirmed, delete the listed directories.

3. Create empty `.gitkeep` files in `input/`, `raw/`, and `output/` so the directories are preserved in git.

4. Report what was deleted.
