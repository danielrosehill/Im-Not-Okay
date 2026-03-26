Process a voice memo through the full pipeline: ingest, transcribe, edit, and analyse.

The user will provide a path to an audio file (e.g. on their desktop). If no path is provided, ask for one.

## Steps

1. **Determine the date**: Use today's date in DDMMYY format (e.g. 260326 for 26 March 2026). The folder name uses DDMM format (e.g. 2603).

2. **Ingest the audio**: Create `input/DDMM/` if it doesn't exist. Copy the audio file into it, renaming to `DDMMYY.mp3` (or preserving the original extension if not mp3).

3. **Transcribe**: Use the `transcribe` subagent to send the audio to AssemblyAI. Save the raw transcript as `raw/DDMM/DDMMYY_raw_transcript.md`.

4. **Edit the transcript**: Use the `edit-transcript` subagent to clean up the raw transcript into a polished, readable version. Save as `output/DDMM/DDMMYY_edited_transcript.md`.

5. **Analyse**: Launch the following subagents in parallel, all reading from the edited transcript:
   - `problems-summary` — extracts and describes each discrete problem
   - `problems-categorisation` — groups problems into categories
   - `priority-assessment` — orders problems by suggested priority
   - `pathways-recommendation` — suggests practical next steps and support pathways

6. **Check for user profile**: If `USER_PROFILE.md` exists at the repo root, pass it to each analysis subagent so outputs can be tailored to the user's support context (e.g. mentioning therapy if they're in therapy, or keeping suggestions general if they're not).

7. **Report**: List all generated files and give a brief summary of what was found.
