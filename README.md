[![Listed in Claude Code Repos Index](https://img.shields.io/badge/Claude%20Code-Repos%20Index-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-Code-Repos-Index)

# I'm Not Okay

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) template that turns voice memos into structured problem summaries — for personal reflection or to share with a therapist, counsellor, or anyone you're getting support from.

## What This Is

You record a voice memo talking about what's going on in your life. The tool:

1. **Transcribes** it (via [AssemblyAI](https://www.assemblyai.com/))
2. **Edits** the transcript into clean, readable prose
3. **Extracts** every discrete problem or stressor you mentioned
4. **Categorises** them by theme (health, work, relationships, etc.)
5. **Prioritises** them by urgency and impact, with concise summaries

The result is a set of structured documents you can use however you want — bring them to a therapy session, share with a friend, or just use them to get clarity on what's weighing on you.

## What This Is Not

**This is not "AI therapy."** Claude does not diagnose, treat, advise, or counsel. It doesn't interpret your feelings or tell you what to do.

What it does is much simpler: it **organises information you provide**. Think of it like dictating a messy set of notes and having someone type them up neatly, group them, and help you see the full picture. The thinking and the meaning are entirely yours.

## How It Works

This is a Claude Code template — a repository with pre-configured slash commands and subagents that automate the workflow.

### Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed
- An [AssemblyAI API key](https://www.assemblyai.com/) (free tier available)
- The `ASSEMBLYAI_API_KEY` environment variable set

### Quick Start

```bash
# Clone the template
git clone https://github.com/danielrosehill/Im-Not-Okay.git
cd Im-Not-Okay

# Start Claude Code
claude

# Set up your profile (optional but recommended)
/init

# Process a voice memo
/process-memo ~/Desktop/my-voice-note.mp3
```

### Commands

| Command | What it does |
|---------|-------------|
| `/init` | Set up your user profile — tells the tool about your support context and output preferences |
| `/process-memo <path>` | Full pipeline: copies your audio in, transcribes, edits, and generates all analysis |
| `/analyse` | Re-run analysis on an existing transcript (useful after edits) |
| `/review` | Get a summary of the latest outputs |
| `/delete-demo` | Remove the included demo data and start fresh |

### Output Structure

```
output/DDMM/
  DDMMYY_edited_transcript.md      # Your memo, cleaned up and readable
  DDMMYY_problems_summary.md       # Each problem listed and described
  DDMMYY_problems_categorised.md   # Problems grouped by theme
  DDMMYY_priority.md               # Suggested priority ordering
```

## Demo Data

The repository includes a real voice memo and its outputs as a demonstration. Run `/delete-demo` to remove it when you're ready to use the tool with your own data.

## User Profile

Running `/init` creates a `USER_PROFILE.md` where you can note:

- Whether you're in therapy, open to it, or not interested
- What kind of support you have or want
- Any constraints (cost, time, location)
- Whether you want outputs framed as personal notes or as documents to share with someone

The analysis agents read this file to tailor their tone and framing.

## Privacy

Your voice memos and transcripts live in this repository on your local machine. Audio is sent to AssemblyAI for transcription — review their [privacy policy](https://www.assemblyai.com/legal/privacy-policy). All AI analysis happens through Claude Code on your machine.

## Disclaimer

This tool is provided as-is for personal use. It is not a medical device, therapeutic tool, or substitute for professional mental health care. The outputs are automated summaries of information you provide — they are not clinical assessments, diagnoses, or recommendations.

If you are in crisis, please contact a crisis helpline in your country or go to your nearest emergency department.

## License

Open source. Use it, fork it, adapt it.

---

For more Claude Code projects, visit [my index](https://github.com/danielrosehill/Claude-Code-Repos-Index).
