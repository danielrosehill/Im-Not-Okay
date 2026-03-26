Delete all demo/example data from the repository so the user can start fresh with their own voice memos.

## What gets deleted

- `input/demo/` (demo audio files)
- `raw/demo/` (demo raw transcripts)
- `output/demo/` (demo edited transcripts and analysis outputs)
- `project-idea/` (project concept voice memo and transcript)

## What is preserved

- All slash commands and subagents (`.claude/`)
- `CLAUDE.md` (project instructions)
- `.mcp.json` (AssemblyAI config)
- `README.md`
- `USER_PROFILE.md` (if it exists)
- The `input/`, `raw/`, and `output/` directories themselves (kept empty)

## Steps

1. Confirm with the user before deleting: "This will remove all demo data (input/demo, raw/demo, output/demo, and project-idea/). Your own data and all configuration will be preserved. Proceed?"

2. If confirmed, delete the listed directories.

3. Create empty `.gitkeep` files in `input/`, `raw/`, and `output/` so the directories are preserved in git.

4. Report what was deleted.
