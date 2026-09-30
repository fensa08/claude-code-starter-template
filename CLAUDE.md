# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is a **reusable Claude Code setup template** — not an application. It holds baseline `.claude/` configuration meant to be copied into new projects to bootstrap their Claude Code environment, rather than code to be built or shipped from this directory itself.

## Structure

- `.claude/settings.json` — baseline permissions template (allow/deny lists for common read-only Bash commands). Adjust per project before use.
- `.claude/agents/` — example custom subagent definition(s). Replace with real project-specific agents or delete.
- `.claude/commands/` — example custom slash command(s). Replace with real project-specific commands or delete.

## Using this template

To bootstrap a new project with this setup, copy the `.claude/` directory into the new project's root, then:
1. Update `.claude/settings.json` permissions to match the new project's actual toolchain (build/test/lint commands).
2. Replace or remove the example agent/command files with ones specific to the new project.
3. Write a project-specific `CLAUDE.md` for the new project describing its own build/test/architecture — do not reuse this file's content, as it only describes this template repo.

## Maintaining this template

When adding a new reusable convention (a permission pattern, an agent, a command) here, keep it generic — nothing project-specific belongs in this repo.
