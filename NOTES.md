## Skill test — blank version

Prompt: Use the check-release skill to review my release note.
Expected: Version should be missing. The other three fields should pass.
Actual: Ticket, Environment, and Validation passed. Version was missing.
Result: The skill correctly marked the release note incomplete.
Tool approval: No approval prompt appeared.

## Permissions test — Ask

I asked Antigravity to run git status --short.
It paused and asked for approval. I approved it once.
The command then listed my untracked files.

## Hook test

Allowed: I asked Antigravity to run ls release.md. It printed release.md.
Denied: I asked it to run rm --help. My hook replied “Course hook blocks rm.”

## Detection pass

Slop: None. The skill reported the four fields I asked it to check.
Drift: None. It stayed focused on reviewing the TEST release note.
Hallucination: None. It correctly reported the blank version and the three values I entered.
One fix I would make next time: I would run a second test with a version filled in to check that the skill can also report a complete checklist.

## File permissions

Allow: Antigravity can read this project’s release.md so it can check the four fields.
Deny: Antigravity cannot read this project’s .env file because it could contain a password or API key.
Rule order: Deny wins first, then Ask, then Allow. Even if I allow reads across a folder, a Deny rule for .env still blocks that file.