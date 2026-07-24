# Reviewed patterns

This file contains only patterns explicitly approved by the user. Dated files
in `practice-logs/` remain the ground-truth evidence. A pattern summarizes that
evidence; it does not replace it or establish an objective golf fact.

## Rules

- Require support from at least three dated reflection files before proposing a
  pattern.
- Treat an explicit request as a trigger to review the evidence, not as a waiver
  of the three-log threshold and not as approval to write.
- Cite every supporting and contradictory reflection.
- Treat confidence as confidence in consistency across reflections, not in the
  technical truth of a golf belief.
- Use `low` when evidence has only just met the threshold, is indirect, or has
  meaningful contradiction.
- Use `medium` when the same theme is directly supported across different dates
  or contexts with limited contradiction.
- Use `high` only when clear evidence recurs over an extended period or across
  varied contexts with no material contradiction.
- Treat only entries with `Status: active` as current knowledge.
- Keep superseded and retired entries for history; never delete them merely
  because the pattern changed.
- Create a revised pattern as a new active entry and mark the previous entry
  `superseded`.
- Write a proposed entry only after the user explicitly approves that proposal.
  On approval, change its status to `active`, record the approval date, and
  write it without requesting a second confirmation.
- Do not treat the schema below as a pattern or as evidence.

## Entry schema

```md
## Pattern: <short descriptive name>

- Status: active | superseded | retired
- Approved: YYYY-MM-DD
- Last reviewed: YYYY-MM-DD
- Confidence: low | medium | high
- Supersedes: none | <previous pattern heading>
- Superseded by: none | <replacement pattern heading>

### Statement

A cautious description of what recurs in the user's reflections. Separate the
user's observation from any interpretation.

### Supporting evidence

- YYYY-MM-DD — [Reflection](../practice-logs/<filename>.md): a brief quotation
  or faithful paraphrase of the relevant evidence.

### Contradictory evidence

- None found as of YYYY-MM-DD.

Use “None found” only after reviewing the available dated logs. Otherwise list
contradictory reflections using the same dated citation format.

### Scope and uncertainty

Explain why the confidence level was chosen, what the evidence supports, and
what the pattern does not establish.

### Revision history

- YYYY-MM-DD — Approved by the user.
```
