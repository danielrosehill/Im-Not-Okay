# I'm Not Okay

A Claude Code template that uses AI to organise voice memos into structured summaries for personal reflection or sharing with a support person.

**This is not therapy.** Claude does not provide therapeutic advice, diagnosis, or treatment. This tool organises information that the user provides — nothing more. It takes a rambling voice note and produces structured documents that make it easier to understand and communicate what you're dealing with.

## Getting Started

### First-time setup

1. Set the `ASSEMBLYAI_API_KEY` environment variable (required for transcription)
2. Run `/init` to create your user profile — this tells the tool about your support context and how you'd like outputs framed
3. Run `/process-memo` with a path to your first voice memo

### Ongoing use

1. Record a voice memo describing what's on your mind (any length, any format — just talk)
2. Run `/process-memo /path/to/your/memo.mp3`
3. Review the outputs in `output/DDMM/`

### Removing demo data

The repo ships with example data for demonstration. Run `/delete-demo` to remove it and start clean.

## Directory Structure

```
input/                                  # Original audio files
  DDMM/                                # Date folder (e.g. 2603 = 26th March)
    DDMMYY.mp3                         # Audio file

raw/                                    # Raw transcripts (unedited AssemblyAI output)
  DDMM/
    DDMMYY_raw_transcript.md

output/                                 # All processed outputs
  DDMM/
    DDMMYY_edited_transcript.md         # Polished, readable transcript
    DDMMYY_problems_summary.md          # Each problem described individually
    DDMMYY_problems_categorised.md      # Problems grouped by theme
    DDMMYY_priority.md                  # Suggested priority ordering

USER_PROFILE.md                         # User's support context and preferences (created by /init)
project-idea/                           # Project concept and background notes
```

## Slash Commands

| Command | Purpose |
|---------|---------|
| `/init` | Onboarding — create your user profile with support context and output preferences |
| `/process-memo` | Full pipeline: ingest audio, transcribe, edit, generate all analysis outputs |
| `/analyse` | Re-run analysis on an existing edited transcript (skips transcription) |
| `/review` | Read-only summary of the latest outputs |
| `/delete-demo` | Remove all demo/example data to start fresh |

## Subagents

| Agent | Model | Purpose |
|-------|-------|---------|
| `transcribe` | haiku | Sends audio to AssemblyAI and saves raw transcript |
| `edit-transcript` | sonnet | Polishes raw transcript into clean, readable prose |
| `problems-summary` | sonnet | Extracts and describes each discrete problem mentioned |
| `problems-categorisation` | sonnet | Groups problems into thematic categories with cross-cutting themes |
| `priority-assessment` | sonnet | Orders problems by suggested priority with summaries |

## AssemblyAI

Transcription is handled by AssemblyAI, configured in `.mcp.json`. The `ASSEMBLYAI_API_KEY` environment variable must be set.

## User Profile

`USER_PROFILE.md` (created by `/init`) stores:
- What support the user currently has (therapy, counselling, none, etc.)
- What modalities they're open to
- Constraints (cost, availability, etc.)
- How they want outputs framed (personal notes vs shareable documents)

Analysis subagents read this file to tailor their output tone and framing.

## Important Notes

- This tool organises information — it does not provide advice, diagnosis, or treatment
- All analysis is based solely on what the user said in their voice memo
- Outputs are starting points for reflection or conversation, not clinical assessments
- The demo data in `input/2603/` is real context provided for demonstration purposes
- This is a template — fork it and use it with your own voice memos
