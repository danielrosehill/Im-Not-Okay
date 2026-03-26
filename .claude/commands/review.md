Review all outputs for the latest (or specified) date and present a summary to the user.

Read-only — doesn't generate anything new.

## Steps

1. **Find outputs**: Look in `output/` for the most recent date folder. If `$ARGUMENTS` contains a date (DDMM), use that.

2. **Read all output files** in that folder.

3. **Present a summary**:
   - How many problems were identified
   - The categories they fell into
   - The top 3 by priority
   - Overall tone/state

4. **Ask**: Whether the user wants to regenerate any outputs, adjust priorities, or make edits.
