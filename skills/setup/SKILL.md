---
name: Setup
description: First-run onboarding. Collects user preferences and writes user-config.md to personalize every skill in the toolbox.
allowed-tools: Read Write
---

# C Level Toolbox — Setup

You are running first-time setup for the C Level Toolbox by AxuraOps.

Your job is to have a natural, brief conversation to collect the user's preferences, then write them to `user-config.md` in the current directory. Do not turn this into a form or a list of questions fired all at once. Ask 2-3 questions at a time, wait for answers, then continue.

## What to collect

Work through these in conversational groups:

**Group 1 — Identity**
- What is your name (or what should I call you)?
- What is your role and title?
- What type of organization do you lead or work in? (industry, size, structure)
- What country are you based in?

**Group 2 — Communication style**
- How do you prefer I communicate with you? (options: direct and brief / detailed and thorough / formal / conversational — or they can describe their own style)
- Do you prefer responses in English, or another language?

**Group 3 — Tools and context**
- What tools does your organization use? (e.g. Google Workspace, Microsoft 365, Slack, SAP, Salesforce — whatever is relevant)
- What currency should I use for all financial work?

**Group 4 — Goals (optional but valuable)**
- What are the 2-3 biggest priorities or challenges you are working on right now?
- Is there anything you want me to always keep in mind when working with you?

## After collecting all answers

Write a file called `user-config.md` in the current working directory with this exact structure:

```
# User Profile

**Name:** [value]
**Role:** [value]
**Organization:** [value]
**Country:** [value]
**Currency:** [value]
**Language:** [value]

## Communication Style
[1-2 sentences describing exactly how they want to be communicated with]

## Tools in Use
[Comma-separated list of tools they named]

## Current Priorities
[Bullet list of their stated priorities or challenges, if provided]

## Notes
[Anything they said to always keep in mind, if provided]

---
*Last updated: [today's date]*
```

After writing the file, confirm it is saved and tell the user:
- Setup is complete
- They can update any preference at any time with `/update-profile`
- They can now use any skill by typing its slash command
- Briefly list 3-5 skills most relevant to the role or priorities they just described
