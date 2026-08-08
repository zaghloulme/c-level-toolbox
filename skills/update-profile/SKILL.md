---
name: Update Profile
version: 2.0.0
description: Update anything in user-config.md — name, tone, use case, or what to avoid.
---

# Update Profile

Read `user-config.md` from the current directory.

If it does not exist, tell the user setup has not been completed and to run `/setup` first. Stop there.

If it exists, show them the current profile in plain prose. Don't use bullet lists. Something like:

> You're set as [name], age [age or "not shared"]. You use me for [use case]. You want me to [tone]. You told me to avoid [avoid notes].

Then ask:

> What do you want to change?

Wait for their reply. Update only the fields they mention. Keep everything else exactly as it was.

Rewrite `user-config.md` with the updated values. Update the `Last updated` date at the bottom to today's date in YYYY-MM-DD.

Tell them the change is saved. One sentence. Done.

## Rules

- Never present options as a list.
- Never batch multiple changes at once — ask, confirm, save.
- Do not invent fields. If the user wants to add something the current schema doesn't cover, tell them the current profile is name / age / use case / tone / avoid notes and ask which of those fits best. If none fits, save it under "avoid notes" as an extra line.
