---
name: check-release
description: Reviews a local TEST release note and reports missing fields. Use when asked to check a release before deployment.
---

# Check a release note

1. Run `pwd` and `ls release.md`. If the file is missing, report which folder you checked and stop.
2. Read `release.md`. Look for four labels: Ticket, Environment, Version, and Validation.
3. For each label, report PASS if it has a value after the colon. Report MISSING if the label is absent or the value is blank.
4. Report whether Environment says TEST. If any field is missing or the environment is different, mark the checklist incomplete and explain why.
5. Leave the file as you found it. Report the results without filling in missing values or running a deployment.