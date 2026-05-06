# Hermes Workspace Notes

This repository contains Markdown guidance files for a Hermes-centered agent workspace designed to work alongside OpenClaw/Claw in a multi-agent setup.

The files here are intended to make the workspace easier to understand, maintain, and evolve over time. They define the assistant's persona, the user's preferences, durable environment context, and optional heartbeat behavior for background checks.

## Purpose

This repo is meant to support a practical local agent system where:

- Hermes acts as the top-level orchestrator.
- Claw (OpenClaw) acts as the lead implementer.
- A task-worker can bridge communication between agents when needed.
- Markdown files hold the stable human and system context that should persist across sessions.

These files are not application code. They are operating context for the agent system.

## Files

### `SOUL.md`
Defines the assistant's identity, tone, boundaries, and behavioral principles.

Use this file to shape how Hermes behaves across sessions, especially around communication style, caution, autonomy, and continuity.

### `USER.md`
Captures durable information about the human operator: preferences, work style, technical habits, and collaboration expectations.

Use this file for stable user context that helps the agent respond better over time.

### `MEMORY.md`
Stores durable facts about the environment, architecture, repos, tools, and long-lived operational patterns.

Use this file for information that should remain true across sessions and should not need to be rediscovered repeatedly.

### `HEARTBEAT.md`
Describes optional background-check behavior for the assistant.

Use this file if the agent should periodically scan for important events, open work, or risks, and decide whether to notify the user, stay quiet, or queue concrete implementation work.

### `AGENTS.md`
Defines role boundaries in a multi-agent system.

This is useful when multiple agents have different responsibilities and the workspace needs a clear contract for orchestration versus implementation.

### `TOOLS.md`
Provides a lightweight reference for hosts, repos, services, and preferred tools.

This file is best kept concise and updated only when the environment changes in meaningful ways.

## Suggested Layout

A practical Hermes layout may look like this:

```text
~/.hermes/
├── config.yaml
├── SOUL.md
└── memories/
    ├── USER.md
    ├── MEMORY.md
    └── HEARTBEAT.md
```

If `AGENTS.md` and `TOOLS.md` are used, they can live in the repo and be copied into the workspace or referenced when refining the main files.

## Editing Guidelines

Keep these files:

- Short enough to stay readable.
- Stable enough to avoid churn.
- Specific enough to be actionable.
- Free of secrets, tokens, passwords, and private keys.

A good rule of thumb:

- Put identity and behavior in `SOUL.md`.
- Put user preferences in `USER.md`.
- Put durable environment facts in `MEMORY.md`.
- Put recurring background-check policy in `HEARTBEAT.md`.
- Put role boundaries in `AGENTS.md`.
- Put quick infrastructure references in `TOOLS.md`.

## What To Avoid

Try not to use these files for:

- Temporary debugging notes.
- Long session transcripts.
- Secrets or credentials.
- Rapidly changing operational state.
- Overly detailed project plans that belong in task tracking instead.

If something changes often, it usually belongs in notes, logs, or project documents rather than long-term memory files.

## Maintenance

Review these files when:

- The system architecture changes.
- New tools or repos become part of the normal workflow.
- The user's preferences become clearer.
- The agent's role or tone needs adjustment.
- Heartbeat behavior becomes too noisy or too passive.

Small, deliberate updates work better than constant rewriting.

## Repo Use

This repository works best as a versioned home for agent guidance files.

That makes it easier to:

- track how the workspace evolves,
- compare revisions,
- reuse patterns across machines,
- and keep persona/memory documents under source control.

## Notes

Before committing changes, redact anything sensitive and keep the files focused on durable context rather than transient state.
