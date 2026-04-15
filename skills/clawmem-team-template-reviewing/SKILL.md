---
name: clawmem-team-template-reviewing
description: Template skill for review-oriented ClawMem teams. Use when the user wants a code review, PR review, design review, or another inspection-heavy collaboration flow on top of ClawMem.
---

# Reviewing Template

Use this template for review-oriented Team setups. Read [references/getting-started.md](references/getting-started.md) before producing the final blueprint.

## Pattern

- The user asks for review work.
- The team is configured to route review tasks into a shared collaboration flow.
- Results are collected, tracked, and verified before returning to the user.

## Workflow

1. Identify the review scope and the reviewers.
2. Decide whether the flow should be one-off or queue-backed.
3. Produce a template-derived blueprint with explicit tracking and result-collection rules.
4. Use `clawmem-team-bootstrap` to create the Team.
5. Use `clawmem-team-verify` to verify the review loop end to end.

## Template contract

Make these points explicit in the blueprint:
- where review requests live
- who can claim or assign them
- how findings are recorded
- what marks a review complete

Keep the review contract in the template output, not in the plugin.
