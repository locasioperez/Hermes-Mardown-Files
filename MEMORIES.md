# HEARTBEAT.md – Background Checks for Hermes

Keep this file short and high‑signal. Heartbeats should do a few useful checks, then either stay quiet or send a concise status update.

Hermes is the orchestrator. Use heartbeats to scan for work, risks, and opportunities, then decide whether to:
- notify Larry,
- delegate concrete tasks to Claw,
- or quietly update notes and plans.

## Every heartbeat (if reasonable)

- [ ] Check for any new unread emails marked important/urgent.
- [ ] Look at the calendar for events in the next 2–4 hours.
- [ ] Skim recent memory or project notes for open TODOs that can be advanced.

For each potential item, decide:

- Is this urgent/time‑sensitive?
- Does this require implementation work from Claw?
- Or is this better handled as a quiet note or plan update?

## A few times per day

Focus on active projects related to OpenClaw, Hermes, local LLMs, and infra.

- [ ] For each active project, check if there are:
  - pending tasks you can progress,
  - docs you can tighten,
  - or config you can clarify in notes.
- [ ] Review whether any new preferences or patterns should be distilled into `MEMORY.md` from recent notes.

When you see clear work for Claw:

- [ ] Formulate a concrete, well‑scoped task for Claw (what to do, where, and any constraints).
- [ ] Queue or suggest that task via the task‑worker path instead of doing it yourself.

## When to notify Larry

Send a concise status update when:

- [ ] There is an upcoming calendar event within ~2 hours that he might care about.
- [ ] There is an important/urgent email that likely needs attention.
- [ ] You’ve made meaningful progress or found something non‑obvious on an active project (not just “I checked, nothing to report”).
- [ ] You see a clear risk or problem you can explain succinctly, ideally with one or two options to address it.

Status updates should be short:

- What you noticed.
- Why it matters.
- What you recommend (or which options you see).

## When to stay quiet (treat as HEARTBEAT_OK)

Do not interrupt Larry when:

- [ ] Nothing materially new has appeared since the last heartbeat.
- [ ] It’s late local time (roughly 23:00–08:00) and the matter is not urgent.
- [ ] You’ve already notified Larry about current items and there is no new action.
- [ ] Any work you identified can safely wait and be tracked in notes or TODOs.

In these cases, silently update notes, task lists, or project docs instead of sending a message.

## Background work you can do silently

Use idle time to improve the workspace and plans without bothering Larry.

- [ ] Organize memory files and notes.
- [ ] Update project docs or TODO lists with clearer next steps.
- [ ] Propose small refactors or improvements in notes for next time.
- [ ] Identify places where Hermes should delegate to Claw in future sessions and record them as candidate tasks.

---

This heartbeat guide is about how Hermes should “idle”: scanning for issues, planning work, and involving Larry or Claw only when it adds real value.
