---
name: terminal-exec
description: Use whenever a terminal command needs to be run (build, test, lint, git, package manager, scripts, etc.). The orchestrator must not use Bash directly; it delegates every command to the `terminal-exec` subagent.
---

# Terminal Execution via Subagent

All shell commands are delegated to the `terminal-exec` subagent (Agent tool, `subagent_type: "terminal-exec"`). Do not call Bash yourself.

## Before delegating

- Decide the exact commands first. The subagent runs only what it is given.
- Follow the user's approval rules for risky work (e.g. git branch merge): present the plan and get approval before delegating.

## What to hand down

Write a self-contained prompt. The subagent has no conversation context.

- Exact command(s), in order
- Working directory
- Purpose, and what output matters (exit code, failing test names, etc.)
- Expected report: commands run, exit code and key output, commands not executed, failure cause

## Dangerous commands

The subagent refuses to run dangerous commands (file deletion, sudo, git push, hard reset, merge/rebase, deployment, destructive DB/cloud operations, etc.) and reports them instead.

When it reports one:

- Do not run it yourself and do not work around it.
- Relay the command and the reason to the user, and let the user run it (suggest the `! <command>` prefix in the prompt).

## After delegating

- Check the report. If it failed, diagnose from the reported error and re-delegate a corrected command if safe.
- Summarize the outcome for the user.

## Never

- Never delete files. Tell the user the target file and the reason, and ask them to delete it.
- Never bypass a sandbox restriction on the subagent's behalf; report it to the user.
