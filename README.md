# My Golf Game

A personal Good–Better–How reflection notebook that catches what I would
otherwise forget after practice sessions and rounds.

## System contract

This README is the product contract: it defines what the system is and what it
does. `AGENTS.md` is the behavioral policy for how Codex should act.
`.agents/skills/` contains the execution instructions for individual workflows.

Skills must follow this product contract and the behavioral policy. If an
execution instruction conflicts with either, update the skill rather than
expanding or changing the product implicitly.

## Workflow

### 1. Capture

Record a voice note immediately after a practice session or round. Answer:

- What was good?
- What could have been better?
- How will I improve it?

Use `$log-reflection` to structure the transcript and save it as a dated
Markdown file in `practice-logs/`. The raw transcript is preserved.

For a round, also reflect on:

- What did I learn?
- What experience do I want to remember?
- What was the one critical decision I made?
- If I could have done one thing differently, what would it be?

### 2. Review

Run `$reflection-brief` once a week—or whenever useful. It summarizes the latest
14 days and compares current observations and intentions with older
reflections.

The brief may recommend exactly one focus derived only from my recorded words
and intentions. It does not introduce technical golf instruction.

### 3. Build knowledge

Dated reflection logs are the ground-truth evidence. Reviewed knowledge
contains user-approved patterns derived only from cited reflection logs.

- One supporting log is an observation.
- Two supporting logs are an emerging signal.
- Three or more supporting logs can become a pattern proposal.
- Nothing is written to `knowledge/` until I explicitly approve the displayed
  proposal.

Approved patterns are stored in `knowledge/patterns.md`. Superseded and retired
patterns remain there as history rather than being deleted.
