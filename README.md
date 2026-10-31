# Alignment check-in: a Claude skill

Say "check in" in the middle of a task and Claude stops, rereads the whole conversation, and asks you about everything it is unsure of before doing any more work.

## How it works

1. **Restates the goal** in a line or two, so you can catch a misread straight away.
2. **Lists every open item** that would change the work: scope, unstated assumptions, missing facts, instructions that don't sit together.
3. **Asks in short rounds**, most important first, with tappable options where your environment has them.
4. **Goes back to the task** without a recap.

It never asks something the conversation already settled, and it doesn't pad the list to look thorough.

## Using it

Copy `skills/alignment-check-in` into your Claude skills folder (`~/.claude/skills/` or your project's `.claude/skills/`). Trigger it with "check in", "are we aligned" or "any questions before you continue".

## Licence

MIT. See `LICENSE`.
