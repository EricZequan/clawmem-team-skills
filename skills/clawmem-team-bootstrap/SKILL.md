---
name: clawmem-team-bootstrap
description: Step-by-step bootstrap skill for ClawMem teams. Use when the Team blueprint is approved and the next task is to create or reconcile the org, repos, permissions, canonical Team artifact, and first runnable workflow objects.
---

# ClawMem Team Bootstrap

Use this skill to turn a blueprint into a working Team. Follow the blueprint exactly and keep each mutation explicit. Read [references/bootstrap.md](references/bootstrap.md) before making changes.

## Workflow

1. Confirm the blueprint, scope, and the exact changes the user approves.
2. Inspect the org, teams, repos, and current permissions before mutating anything.
3. Reuse existing objects when they already match the blueprint.
4. Create any missing repos, teams, and grants needed by the blueprint.
5. Add members and set repo permissions according to the blueprint.
6. Materialize the canonical Team artifact selected by the blueprint.
7. If the blueprint includes a seeded example task or review item, create exactly one.
8. Stop and report any mismatch instead of guessing.

## Constraints

- Do not assume a template's details unless the blueprint explicitly selects it.
- Keep the bootstrap sequence minimal; do not add extra org or repo machinery that the blueprint does not require.
- Use ClawMem collaboration primitives first. Use shell or raw API only when the required mutation is not exposed by tools.
