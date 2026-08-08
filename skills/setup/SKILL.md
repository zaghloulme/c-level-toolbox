---
name: Setup
version: 2.0.0
description: First-run onboarding for the C-Level Toolbox. Asks the user four short questions, one at a time, and writes user-config.md so every other skill in the toolbox knows how to talk to them.
---

# Setup

You are running first-time setup for the C-Level Toolbox.

## Absolute rules for this skill

1. **One question at a time.** Ask a question, stop, wait for the user's reply, then ask the next one. Never batch. Never number.
2. **Never guess.** Do not answer any of these questions on the user's behalf, even if you can infer the answer from prior conversation. Ask.
3. **Do not preview the questions.** No "I'm going to ask you a few things." No lists of what's coming. Just ask.
4. **No parentheticals explaining the question.** The questions below are already self-explanatory. If a question needs explaining, it's the wrong question.
5. **Plain prose only.** No headers, no bullet lists, no bold labels while asking. This is a conversation.

## Turn 1 — Welcome and first question

If a name is already in this conversation's context, open with:

> Hey [name].
>
> What should I call you?

If no name is known, open with:

> Hi.
>
> What should I call you?

Stop. Wait for their reply.

## Turn 2 — Age

Ask exactly this:

> What's your age? Optional — say skip if you'd rather not.

Stop. Wait for their reply. If they skip, note that and move on.

## Turn 3 — Use case

Ask exactly this:

> What are you going to use me for?

Stop. Wait for their reply. If the answer is broad ("everything", "work stuff"), ask one clarifying question in plain prose. Otherwise move on.

## Turn 4 — Tone

Ask exactly this:

> How do you want me to talk to you?

Stop. Wait for their reply. Accept whatever they say in their own words — do not offer options like "blunt / warm / formal". If they ask for options, then and only then give them two examples: "some people want blunt and terse, some want warm and thorough — but say it however feels right."

## Turn 5 — The disappointment question

Ask exactly this:

> Think of a time an AI answered you and it fell flat. What made it fall flat?

Stop. Wait for their reply. This is the most useful answer of the whole setup. Whatever they say, extract from it: what they hate, what they want more of, what they never want to see again. Save that as `avoid_notes` in the config below.

## After all five answers

Silently write `user-config.md` in the current directory. Use this exact structure:

```
# User Profile

**Name:** [what they said in turn 1]
**Age:** [what they said in turn 2, or "not provided"]

## What they use me for
[their answer to turn 3, in their own words]

## How to talk to them
[their answer to turn 4, in their own words]

## What to avoid
[what you extracted from turn 5 — the specific things this user hates in AI responses]

---
*Last updated: [today's date in YYYY-MM-DD]*
```

Do not add fields the user did not answer. Do not invent fields. Do not add a "notes" section unless they said something that clearly belongs there.

## Confirm and hand off

After writing the file, in one short paragraph:

- Tell them setup is done.
- Tell them they can update anything anytime with `/update-profile`.
- Tell them what to do next: pick a skill by typing its slash command. Do not list every skill in the toolbox — the browsable catalog is `skills.html` at the plugin root and they can find it themselves.

That's it. No welcome banner, no "you're all set!", no emoji.
