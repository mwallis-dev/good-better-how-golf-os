---
name: log-reflection
description: Capture a transcribed post-round or post-practice voice note as a dated Good-Better-How Markdown reflection. Use when the user asks to log, save, capture, or format a golf reflection, provides a voice-note transcript, or invokes $log-reflection.
---

# Log reflection

Turn the user's transcript into a faithful, structured reflection in
`practice-logs/`. Preserve the user's voice and agency; do not add golf advice,
diagnoses, patterns, or interpretations.

## Workflow

1. Read the transcript and identify:
   - the session date;
   - the session type: `practice` or `round`;
     - Treat an explicit statement such as “this is a round reflection,” “I
       played a round,” or “I played 9/18 holes” as the round trigger.
     - Do not infer `round` from isolated references to a course, hole, score,
       or club; these can also occur during practice.
   - the session time, only when the user supplied it or clearly said the
     session just finished;
   - the user's Good, Better, and How answers.
2. Ask only essential follow-up questions before preparing the log:
   - Ask for the date if it cannot be established reliably.
   - Ask whether the session was practice or a round if the transcript does not
     make this clear.
   - Ask the missing Good, Better, or How question when the transcript does not
     answer it.
   - If How expresses only a broad aspiration, ask one neutral question such
     as: “What specific action will you take, and when?”
   - Ask no more than three focused questions at once. Allow the user to keep an
     incomplete or broad answer if they do not want to elaborate.
3. Once the session type is established:
   - For `practice`, omit the round questions.
   - For `round`, check whether the transcript answers all four round questions:
     - What did I learn?
     - What experience do I want to remember?
     - What was the one critical decision I made?
     - If I could have done one thing differently, what would it be?
   - Ask any unanswered round questions before preparing the log. Ask no more
     than two round questions in one message, then ask the remaining questions
     in a second message if necessary.
   - Do not repeat questions the transcript already answered.
   - Allow the user to skip any or all unanswered round questions. Record only
     the answers supplied; do not block capture after the user chooses to skip.
4. Prepare the complete proposed Markdown and show it to the user before
   writing. Do not write until the user confirms the proposal, unless they
   explicitly asked to skip confirmation.
5. After confirmation, create one new file in `practice-logs/`. Never overwrite
   or append to an existing reflection unless the user explicitly identifies
   that file and asks for an edit.
6. Confirm the saved path. Do not update `knowledge/`; pattern review and
   promotion are separate workflows.

## Fidelity rules

- Keep the raw transcript exactly as supplied.
- In the structured sections, make only conservative punctuation, obvious
  transcription, and formatting corrections.
- Do not strengthen, validate, or reinterpret causal or technical claims.
- Treat technical statements as the user's experienced observations, not
  established golf facts.
- Do not invent missing content or complete an intention for the user.
- Keep score or outcome comments when the user made them. If helpful, ask what
  they revealed about process, commitment, learning, or future intentions;
  never erase the original comment.
- Do not identify recurring patterns during capture.

## Filename

Use Europe/Dublin local dates.

- When the time is known, use `YYYY-MM-DD-HHMM-<type>.md`.
- When the time is unknown, use `YYYY-MM-DD-<type>.md`.
- If that path exists, add the lowest available numeric suffix, for example
  `YYYY-MM-DD-practice-2.md`.
- Never fabricate a session time to make a filename.

## Log format

Omit `time` when it is unknown. Omit the entire `Round reflection` section for
practice sessions. Within a round reflection, include only the questions the
user answered.

```md
---
date: YYYY-MM-DD
time: "HH:MM"
timezone: Europe/Dublin
session_type: practice
---

# Good–Better–How reflection

## Good

The user's answer.

## Better

The user's answer.

## How

The user's intended action.

## Round reflection

### What did I learn?

The user's answer.

### What experience do I want to remember?

The user's answer.

### What was the one critical decision I made?

The user's answer.

### What would I do differently?

The user's answer.

## Raw transcript

The transcript exactly as supplied.
```
