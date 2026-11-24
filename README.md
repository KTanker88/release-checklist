# TEST Release Checklist

I use this project to check a release note before a TEST deployment. I look for a ticket, environment, version, and validation step.

## Skill
My skill is a saved checklist. It reads release.md, checks the four fields, and tells me what is missing.

## Hook
My hook runs before Antigravity uses the terminal. It checks the command and blocks the rm pattern so the agent cannot delete my release note with that command.

## Permissions
Allow lets an action go ahead. Ask pauses for my approval. Deny blocks the action. When rules conflict, Antigravity checks Deny first, then Ask, then Allow.