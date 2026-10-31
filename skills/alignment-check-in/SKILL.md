---
name: alignment-check-in
description: "Run a user-triggered alignment check-in that pauses the current task, reviews the whole conversation so far, and surfaces every open question, unstated assumption, knowledge gap, ambiguity, or possible misalignment Claude is carrying, then resolves them with the user through the environment's Q&A tool before continuing. Use this whenever the user wants to confirm you and they are fully aligned before you proceed - triggers include 'check in', 'alignment check', 'are we aligned', 'are we on the same page', 'any questions before you continue', 'what do you need from me before starting', 'surface your assumptions', 'anything unclear', 'sync up', or any request to confirm shared understanding mid-task. Works in chat, Claude Cowork, and Claude Code. This is a mid-task sync, distinct from end-of-session audits, conversation handovers, or folder context setup - reach for it when the goal is to eliminate misunderstanding before doing more work."
---

# Alignment check-in

A user-triggered pause that surfaces everything Claude is unsure about, guessing at, or silently assuming, and resolves it with the user through a structured Q&A before any further work happens. The point is simple: get the user and Claude completely aligned so the work that follows is right the first time.

## When to use this

The user invokes this deliberately, mid-task, when they want to be sure nothing is being misunderstood before Claude continues. It is not run autonomously and it is not an end-of-session sweep. It runs forward: resolve the ambiguity now, then proceed.

## How it works

1. Review the entire conversation so far.
2. Build a list of everything that could cause a wrong or misaligned output.
3. Ask the user about it in rolling rounds using the Q&A tool, tappable options preferred.
4. Keep going round by round until nothing material is left open.
5. Resume the original task silently, with no recap.

## Step 1: Review the conversation

Read back through every message in the current thread before asking anything. The goal is to find what is unresolved, not to re-summarise what is clear. Pay attention to:

- The stated goal, and whether "done" and "good" are actually defined.
- Anything the user said once and may have assumed was understood.
- Corrections the user already made, and whether they were fully absorbed.
- Defaults Claude has quietly chosen without checking.
- Points where two things the user said do not fully reconcile.
- Several ideas packed into one message. Separate them and check which one is the task.
- Steps the user jumped over while thinking ahead. Name the gap instead of filling it with a guess.

Open the check-in with one or two lines restating your current understanding of the goal. This lets the user catch misalignment they did not think to raise. Keep it short. Do not turn it into a summary of the whole thread.

## Step 2: Build the question list

Run through these categories and collect every genuine open item. Only keep a question if a wrong answer would change the output.

- **Goal and success criteria** - what does a great result look like, concretely?
- **Scope** - what is in, what is out, where does this stop?
- **Unstated assumptions** - what am I currently taking for granted that, if wrong, breaks the work?
- **Silent decisions** - where did I pick a default instead of asking?
- **Knowledge and context gaps** - facts, files, access, names, or preferences I am missing.
- **Conflicting signals** - places the user gave two instructions that do not sit together.
- **Format and output** - shape, length, file type, destination, naming.
- **Constraints** - standing rules, voice, or guardrails I might be about to cross.

Drop anything the conversation already answers. Do not pad the list to look thorough.

## Step 3: Ask, in rolling rounds

### Choosing the Q&A tool for your environment

Use the structured question tool your environment provides:

- **Chat**: the tappable multiple-choice question tool. Caps at a small number of questions per call, so batch accordingly.
- **Cowork / Code**: the equivalent ask-the-user input tool.
- **Plain-text only environments**: if no interactive tool exists, present numbered questions inline with lettered options and ask the user to reply with their picks.

### Writing good questions

- Prefer tappable multiple-choice. Offer 2 to 4 distinct, plausible options that map to genuinely different paths forward.
- Use open free-text only when the answer truly cannot be reduced to options.
- Where useful, include an escape-hatch option ("none of these / let me explain") so a forced choice never distorts the answer.
- Surface the assumption inside the question, so the user sees what you currently believe and can correct it.
- One idea per question. Do not bundle.
- Never re-ask something the conversation already settled.

### Rolling rounds

Ask the most decision-critical questions first. When there are more open items than fit in one round, ask a round, take the answers, then ask the next round. New answers often resolve or reshape later questions, so rebuild the remaining list after each round rather than firing a fixed script. Continue until nothing material is unresolved.

## Step 4: Resume silently

Once everything material is settled, go straight back to the original task with the corrected understanding. No "here is what we agreed" recap unless the user asks for one.

If the user stopped the work before the check-in, do not resume on your own: ask whether they have more notes, and resume only on their go.

## What good looks like

- Every question would actually change the work if answered differently.
- The user mostly taps rather than types.
- Misalignment is caught before output, not after.

## Anti-patterns

- Asking questions the thread already answered.
- Free-text where options would do.
- Bundling several decisions into one question.
- Summarising the conversation instead of resolving what is open.
- Continuing to ask once nothing material remains.
