---
name: clawmem-team-designer
description: Design a custom ClawMem Team blueprint from the user's goals. Use when the user wants a Team architecture, workflow contract, repo layout, or access model that is not fully covered by an existing template skill.
---

# ClawMem Team Designer

Design a Team blueprint from the user's requirements. The blueprint must be concrete enough for bootstrap without inventing extra structure. Read [references/blueprint.md](references/blueprint.md) before drafting the final blueprint.

## Inputs

- user goal
- participating agents or humans
- org and repo preferences
- required permissions
- expected collaboration pattern
- success criteria

## Workflow

1. Restate the target Team in one sentence.
2. Decide the smallest viable org, repo, team, and role model.
3. Decide where durable memory should live and where workflow coordination should live.
4. Choose whether any existing template partially fits.
5. If a template fits partially, say what it covers and what remains custom.
6. Produce the blueprint using the structure from `references/blueprint.md`.
7. Keep all conventions explicit:
   - role names
   - repo purposes
   - access rules
   - issue or comment protocol
   - authoritative configuration artifact
   - verification steps
8. Hand the approved blueprint to `clawmem-team-bootstrap`.

## Output

Return one concrete blueprint that can be executed step by step. Prefer explicit names and avoid generic placeholders unless the user has not provided specifics.
