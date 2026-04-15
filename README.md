# clawmem-team-skills

`clawmem-team-skills` is the external skill pack for ClawMem Team workflows.

ClawMem plugin itself should stay team-agnostic:
- memory
- repo routing
- schema
- repair / verification guidance
- atomic collaboration tools for orgs, repos, teams, invitations, access, issues, and comments

This repository owns everything above that layer:
- Team design
- Team bootstrap
- Team verification
- Team workflow templates
- Team onboarding docs

## Purpose

This repo exists to keep the product boundary clean:
- `ClawMem plugin` = capability layer
- `clawmem-team-skills` = Team workflow layer

That means the plugin does not hardcode any `main / worker / summary queue` contract, queue label protocol, or Team runtime instruction. Any such convention belongs here as a skill-level choice.

## Prerequisites

Before using this repository:
1. Install and enable the ClawMem plugin.
2. Confirm ClawMem is the active memory slot in OpenClaw.
3. Confirm the bundled `clawmem` runtime skill is available.
4. Install this repository as an additional external skill pack.

Use this pack only when the user wants to design or run a Team workflow. For ordinary memory usage, stay on the bundled `clawmem` skill.

## Skill Map

- `clawmem-team`
  - Entry skill
  - Decide between template path and custom design path
- `clawmem-team-designer`
  - Produce a reusable Team blueprint from user goals
- `clawmem-team-bootstrap`
  - Turn a blueprint into concrete org / repo / team / permission / workflow setup
- `clawmem-team-verify`
  - Verify the Team is actually ready to use
- `clawmem-team-template-main-worker-queue`
  - Template for `main / worker / summary queue`
- `clawmem-team-template-reviewing`
  - Template for review-oriented collaboration

## Recommended Flow

1. Start with `clawmem-team`.
2. If a template clearly fits, use that template skill to produce the Team blueprint.
3. If no template fits, use `clawmem-team-designer`.
4. Use `clawmem-team-bootstrap` to execute the approved blueprint.
5. Use `clawmem-team-verify` to confirm the Team is usable end to end.

## Repository Layout

```text
skills/
  clawmem-team/
  clawmem-team-designer/
  clawmem-team-bootstrap/
  clawmem-team-verify/
  clawmem-team-template-main-worker-queue/
  clawmem-team-template-reviewing/
```

Each skill stays small and procedural. Detailed protocol, blueprint, bootstrap, and getting-started material lives under that skill's `references/` directory.

## Template Policy

Templates in this repository may define concrete conventions such as:
- repo layout
- label protocol
- role naming
- issue and comment format
- verification path

Those conventions are template-owned, not plugin-owned.

## Example Requests

These requests should trigger this repository:
- "Help me design a ClawMem Team for my research workflow."
- "I want a main / worker / summary queue setup."
- "Set up a reviewing Team on top of ClawMem."
- "Guide me through configuring a custom Team step by step."

## Publishing

This repository is intended to be published as a standalone GitHub repo and optionally mirrored into a skill marketplace such as ClawHub.
