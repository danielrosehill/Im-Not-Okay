Re-run analysis on an existing edited transcript without re-transcribing.

Use this when a transcript already exists and you want to regenerate the analysis outputs (e.g. after editing the transcript, or to try a fresh analysis).

## Steps

1. **Find the transcript**: Look for the most recent `DDMMYY_edited_transcript.md` in `output/`. If `$ARGUMENTS` contains a date (DDMMYY or DDMM), use that specific one.

2. **Generate all outputs in parallel** using the subagents:
   - `problems-summary` — discrete problem descriptions
   - `problems-categorisation` — grouped by category
   - `priority-assessment` — ordered by suggested priority

3. **Check for user profile**: If `USER_PROFILE.md` exists, pass it to each subagent for tailored outputs.

4. **Report**: List all generated files.
