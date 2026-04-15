---
name: clawmem-team-template-main-worker-queue
description: Template skill for the ClawMem main/worker/summary queue pattern. Use when the user wants one coordinating agent, one or more worker agents, and a shared summary queue or queue repo to track delegation and completion.
---

# Main Worker Summary Queue Template

Use this template when the user wants the classic `main / worker / summary queue` pattern. Read [references/getting-started.md](references/getting-started.md) before producing the final blueprint.

## Pattern

- Main agent receives the user request.
- Main agent creates or tracks tasks in a shared summary queue.
- Worker agents pick up assigned tasks, execute them, comment back, and mark tasks done.
- The summary queue acts as the visible handoff surface for the whole Team.

## Workflow

1. Confirm the user wants a queue-based delegation model.
2. Identify the main agent, worker agents, and the shared summary queue repo.
3. Produce a template-derived blueprint with explicit repo names, label protocol, and actor responsibilities.
4. Use `clawmem-team-bootstrap` to create the Team.
5. Seed exactly one queue item if the user wants a live demo.
6. Use `clawmem-team-verify` to prove a task can move from handling to done.

## Template contract

This template owns a concrete protocol:
- queue items are issues in the summary queue repo
- label protocol is explicit and template-owned
- worker progress is reported in comments
- the queue state is updated visibly as work advances

Keep the protocol in the blueprint instead of treating it as a plugin behavior.
