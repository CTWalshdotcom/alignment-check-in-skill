# Alignment check-in: a Claude skill

Say "check in" in the middle of a task and Claude stops, rereads the whole conversation, and asks you about everything it is unsure of before doing any more work.

## Why I built it

I have ADHD (inattentive type). I often think in non-linear patterns, connecting ideas quickly and several steps ahead, and my instructions can arrive with too much context and too many ideas at once. Claude rarely says when it's filling a gap; it guesses what I meant and carries on. With people, I manage this by asking clarifying questions and recapping before we move on. This skill does the same with Claude.

## How it works

1. **Restates the goal** in a line or two, so you can catch a misread straight away.
2. **Lists every open item** that would change the work: scope, unstated assumptions, missing facts, instructions that don't sit together, several ideas packed into one message, and steps you skipped while thinking ahead.
3. **Asks in short rounds**, most important first, with tappable options where your environment has them.
4. **Goes back to the task** without a recap.

It never asks something the conversation already settled, and it doesn't pad the list to look thorough.

## Using it

Copy `skills/alignment-check-in` into your Claude skills folder (`~/.claude/skills/` or your project's `.claude/skills/`). Trigger it with "check in", "are we aligned" or "any questions before you continue".

## Licence

MIT. See `LICENSE`.
