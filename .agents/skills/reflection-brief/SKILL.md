---
name: reflection-brief
description: Produce an ad-hoc golf reflection brief from the last 14 days of dated practice and round reflections plus longitudinal pattern evidence. Use when the user asks for a reflection brief or invokes $reflection-brief.
---

# Reflection brief

1. Use the Europe/Dublin timezone.
2. Treat the reporting window as today plus the previous 13 dates.
3. Read every dated Markdown reflection in `practice-logs/` within that window.
   - Use these recent reflections for the 14-day summary and suggested focus.
   - Extract only observations and intentions expressed by the user.
4. Check recent observations and intentions against every older dated Markdown
   reflection in `practice-logs/`.
   - Use older reflections only to test whether a recent theme recurs or is
     contradicted; do not broaden the 14-day summary with unrelated history.
   - Count supporting reflection files, not repeated mentions within one file.
   - Treat similar wording as the same theme only when it clearly expresses the
     same underlying observation or intention. Keep ambiguous themes separate.
   - Cite every supporting and contradictory reflection date.
   - Do not treat silence in a later reflection as resolution or contradiction.
5. Read all Markdown files in `knowledge/`.
   - Read and follow the canonical entry schema in `knowledge/patterns.md`.
   - Do not treat schema templates or fenced examples as knowledge.
   - Treat only entries with `Status: active` as current knowledge.
   - Retain superseded and retired entries as historical context.
   - Treat reviewed knowledge as more authoritative than inferred patterns.
   - Use only dated practice reflections as evidence for observations and intentions.
   - Check whether recent evidence supports, contradicts, or may revise an
     approved knowledge item.
6. Separate observations from patterns.
   - One reflection is an observation, not a pattern.
   - Two supporting reflection files are an emerging recurring signal, not
     enough for a knowledge proposal.
   - Three or more supporting reflection files form a candidate pattern that is
     eligible for a knowledge-base proposal.
   - State confidence and contradictory evidence for every recurring signal or
     candidate pattern.
   - Offer at most one knowledge-base proposal in a brief. Choose the
     best-supported candidate relevant to the current 14-day window.
   - Include all supporting and contradictory dates in the proposal.
   - Format the proposal using the canonical schema, with `Status: proposed`
     and `Approved: pending user approval`.
   - Explain that confidence measures consistency across reflections rather
     than the technical truth of the pattern.
   - Do not edit `knowledge/` while generating the brief or proposal.
7. If the user explicitly approves a displayed knowledge proposal:
   - Treat approval as authorization to write immediately; do not ask for a
     second confirmation.
   - If the approval does not clearly identify a proposal, ask which proposal
     the user means before writing.
   - Re-read `knowledge/patterns.md` and confirm the evidence links still
     resolve.
   - Write a new approved pattern as `Status: active`, set `Approved` and
     `Last reviewed` to the Europe/Dublin approval date, and preserve the
     approved statement, evidence, contradictions, confidence, and uncertainty.
   - For an approved revision, append the new active entry and mark the replaced
     entry `superseded`, linking both entries through the schema fields.
   - For an approved retirement, mark the entry `retired` and record the reason
     and date in its revision history.
   - Verify the written entry and report its heading and file path.
8. Suggest exactly one practice focus.
   - Ground it in the user's own words and intentions.
   - Do not introduce technical golf instruction.
   - Present it as a recommendation, not a decision.
9. Do not edit practice logs. Do not edit knowledge unless step 7 applies.

Return:

# Reflection brief — YYYY-MM-DD

## Last 14 days
A concise account of how practice sessions and rounds were experienced,
including what helped, what could have gone better, and unresolved intentions.

## Longer-term signals
Recurring signals or candidate patterns relevant to the recent reflections,
with supporting dates, contradictory dates, and confidence. If none are
supported, say so plainly.

## Knowledge proposal
Include this section only when a candidate pattern has support from three or
more dated reflection files and is not already accurately represented in
reviewed knowledge. Present one proposal using the canonical knowledge schema,
with approval pending; do not write it until the user explicitly approves it.

## Suggested focus
One user-derived focus, its supporting dated evidence, and confidence level.

## Evidence
A short list separated into recent reflection files used for the 14-day
summary and older reflection files used only for longitudinal comparison.
