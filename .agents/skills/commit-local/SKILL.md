---
name: commit-local
description: >-
  Stage and commit local changes with a clear message and safety checks. Does
  not push. Use when the user asks to commit, save a snapshot, or invokes
  $commit-local.
---

# Commit locally

Turn the user's current local changes into a Git commit on this machine.
Explain steps plainly. Prefer the simplest safe path. Never commit unless this
skill was invoked or the user explicitly asked. Never push.

## Preconditions

1. Confirm this folder is a Git repository (`git status`).
2. If there is no Git repo yet, stop and tell the user to create one first
   (GitHub Desktop or `git init`), then retry.

## Workflow

Run these in parallel first:

- `git status`
- `git diff` and `git diff --staged`
- `git log -5 --oneline` (match existing message style)

Then:

1. Summarize what will be committed in plain language (files + intent).
2. If the change set is unclear or mixes unrelated work, ask whether to commit
   everything or only specific paths.
3. Do **not** commit secrets (`.env`, credentials, tokens). Warn and exclude them.
4. Stage the agreed files.
5. Commit with a short why-focused message via HEREDOC:

```bash
git commit -m "$(cat <<'EOF'
Short summary of why this change exists.

EOF
)"
```

6. Report:
   - commit message
   - branch name
   - that changes are committed locally only (not on GitHub until pushed)

## Hard rules

- Never push (`git push` is out of scope for this skill).
- Never update git config.
- Never use `--force`, `reset --hard`, or `rebase -i`.
- Never skip hooks (`--no-verify`).
- Never amend unless the user explicitly asks and the standard amend safety
  checks all pass.
- Never commit if there are no changes.
- If commit fails because of a hook, fix the issue and create a **new** commit
  (do not amend).
- Do not open a pull request unless the user asks for one.

## Message style

- 1–2 sentences max.
- Focus on **why**, not a file list.
- Match recent `git log` tone when possible.
- Examples:
  - `Log 2026-07-24 practice reflection.`
  - `Add local commit agent skill.`
  - `Update weekly reflection brief wording for clearer intentions.`

## Plain-language notes for the user

- **Commit** = snapshot saved in Git history on this machine.
- **Push** = upload to GitHub (not done by this skill; ask separately or use
  GitHub Desktop).
