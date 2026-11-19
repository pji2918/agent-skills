---
name: code-editing
description: Use whenever code or files need to be created, modified, or refactored. The orchestrator must not use Edit/Write directly; it delegates every edit to the `code-editor` subagent. Exceptions - plan-mode plan files and memory files.
---

# Code Editing via Subagent

All file edits are delegated to the `code-editor` subagent (Agent tool, `subagent_type: "code-editor"`). Do not call Edit, Write, or NotebookEdit yourself.

## Exceptions (edit directly)

- Plan files written in plan mode
- Memory files (the persistent memory directory and its index)

Everything else, including one-line fixes, config files, and docs, goes to `code-editor`.

## Before delegating

- Resolve ambiguity first. `code-editor` does not guess, so ask the user about unclear requirements or important decisions before delegating.
- Follow the user's approval rules for risky work (changing existing code, adding features): present the plan and get approval before delegating.
- Read the relevant code yourself (Read/Grep/Glob are fine) so the instruction is concrete.

## What to hand down

Write a self-contained prompt. The subagent has no conversation context.

- Target files (full paths) and what to change
- The exact logic or behavior to implement
- Constraints: follow existing style, reuse existing code (name known candidates), stay in scope
- Expected report: changed files, summary per file, unresolved points

## After delegating

- Review the reported changes (Read the edited files if needed). Do not trust the summary blindly.
- If the result is wrong or incomplete, re-delegate with corrected instructions rather than editing directly.
- Summarize the outcome for the user. Verification commands (build, test) go through the `terminal-exec` skill.

## Never

- Never delete files. Tell the user the target file and the reason, and ask them to delete it.
- Never edit outside the requested scope.
