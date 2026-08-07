---
name: Update Profile
description: Update any preference in user-config.md — tone, currency, tools, priorities, or anything else stored during setup.
allowed-tools: Read Write
---

# Update Profile

Read `user-config.md` from the current working directory.

Show the user a summary of their current settings in a clean, readable format.

Then ask: "What would you like to change?"

Allow them to update any field — name, role, organization, country, currency, language, communication style, tools, priorities, or notes. They can update one thing or several.

After they confirm the changes, rewrite `user-config.md` with the updated values. Keep all fields that were not changed exactly as they were.

Update the `*Last updated*` date at the bottom to today's date.

Confirm the file is saved and tell them the changes are active immediately.

If `user-config.md` does not exist, tell the user setup has not been completed yet and ask them to run `/setup` first.
