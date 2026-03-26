Onboarding workflow — set up a user profile so that outputs can be tailored to the user's situation and preferences.

Ask the user the following questions conversationally (not as a clinical intake form). Be warm and casual. If the user doesn't want to answer something, skip it.

## Questions

1. **What kind of support do you currently have?** (e.g. therapist, counsellor, psychiatrist, support group, trusted friend/family member, none currently)
2. **Are you open to any particular modalities?** (e.g. therapy, counselling, peer support, self-help, journaling — or "I just want to organise my thoughts")
3. **Are there any constraints?** (e.g. cost, availability, language, location, time)
4. **How would you like the outputs framed?** Options:
   - "For me only" — first person, casual, like organised notes
   - "To share with someone" — third person, professional tone, suitable to hand to a therapist or support person
   - "Both" — generate both versions
5. **Anything else you'd like noted?** (e.g. topics to avoid, preferred language, anything about their situation that helps contextualise)

## Output

Save the profile as `USER_PROFILE.md` at the repo root with the following structure:

```markdown
# User Profile

*Created: [date]*

## Support Context
[What support they have or are open to]

## Output Preferences
[How they want outputs framed]

## Constraints
[Any constraints mentioned]

## Additional Notes
[Anything else they shared]
```

Tell the user the profile has been saved and that they can update it any time by running `/init` again or editing `USER_PROFILE.md` directly. Let them know they can now use `/process-memo` to process their first voice memo.
