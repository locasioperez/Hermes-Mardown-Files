# MEMORY.md – Stable Facts & Environment

This file holds durable facts that should remain true across sessions. Update it when environment or architecture changes.

## Multi‑Agent Architecture

- Hermes is the top‑level orchestrator / chief of staff.
- Claw (OpenClaw) is the lead implementer and technical foreman.
- A Node/Express task‑worker acts as the HTTP bridge between Hermes and Claw.
- Claw may create and coordinate its own sub‑agents (e.g., researcher, code reviewer, summarizer) inside the OpenClaw workspace.
- Sub‑agents work inside their own tools/workspace and never orchestrate further agents.

Rule of thumb:

- Hermes orchestrates projects and priorities.
- Claw orchestrates implementation details and sub‑agents.
- Sub‑agents do focused work.

## Hosts & Access Patterns

High‑level homelab context (IPs and secrets are stored elsewhere):

- homelab‑nas – primary NAS; user: larry.
- k8s‑control‑plane – Kubernetes control node; user: ubuntu.
- proxmox‑node‑1 – Proxmox hypervisor; user: root (be especially careful).

Treat any root‑level or infra‑level access as sensitive. Prefer read‑only inspection and clear confirmation from Larry before destructive changes.

## LLMs & Agents

- primary‑llm – local Ollama instance running coding‑focused models.
- Hermes – orchestrator and main conversational entrypoint.
- Claw (OpenClaw) – execution agent for delegated tasks such as coding, file edits, and infra commands.
- Task‑worker – HTTP bridge service wiring Hermes and Claw together.

When unsure which agent should act:

- Use Hermes for planning, scoping, and deciding what to delegate.
- Use Claw for concrete code implementation and filesystem work.
- Treat the task‑worker as transport, not a place for business logic.

## Repositories & Notes

Key repositories and paths on Larry’s machine:

- openclaw‑workspace – OpenClaw workspace and skills (e.g., ~/dev/openclaw).
- infra‑iac – infrastructure‑as‑code (e.g., ~/dev/infra).
- personal‑knowledge‑base – personal notes (e.g., ~/notes).

Prefer:

- Opening PRs or clearly described diffs over ad‑hoc edits when touching infra‑iac.
- Adding or updating notes in the personal knowledge base instead of scattering one‑off files.

## Preferred Tools & Conventions

- Editor: nvim in the terminal, with VS Code as GUI backup.
- Package manager: apt on Debian/Ubuntu.
- Container runtimes: docker and/or podman.
- OS context: Linux / WSL‑first, often Ubuntu‑based.

When suggesting commands:

- Default to bash‑compatible shell on Linux.
- Assume NVM‑managed Node.js for Node/npm usage.
- Call out when commands are destructive or long‑running.

---

Revise this file when Larry’s hardware, repos, or agent architecture change in non‑trivial ways.
