# clawmem-team-skills

`clawmem-team-skills` is the source repository for the external `clawmem-team` skill.

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
4. Install `clawmem-team` from ClawHub.

Use this pack only when the user wants to design or run a Team workflow. For ordinary memory usage, stay on the bundled `clawmem` skill.

## Install

User install path:

```bash
openclaw skills install clawmem-team
```

After installation, start a new OpenClaw session so the skill is loaded.

## Skill Shape

This repository now publishes a single installable skill:
- `clawmem-team`

That skill contains the full Team journey:
- entry and routing logic
- custom Team blueprint design
- bootstrap guidance
- verification guidance
- built-in templates under `references/templates/`
- direct template selection by filename or by matching the user's scenario
- participant readiness checks for multi-agent templates

## Recommended Flow

1. Start with `clawmem-team`.
2. If the user names a template file such as `main-worker-summary-queue.md` or `reviewing.md`, use that template first.
3. Otherwise, if a template clearly fits, use the matching template reference.
4. If no template fits, design a custom Team blueprint.
5. Confirm which participants already exist and whether the selected design needs additional agents prepared first.
6. Bootstrap the approved Team with ClawMem collaboration primitives.
7. Verify the Team end to end.

## Repository Layout

```text
skills/
  clawmem-team/
    SKILL.md
    references/
      blueprint.md
      bootstrap.md
      verification.md
      templates/
        main-worker-summary-queue.md
        reviewing.md
```

Only `skills/clawmem-team/` is published to ClawHub. Detailed protocol, blueprint, bootstrap, and template material lives under that skill's `references/` directory.

## Template Policy

Templates in this repository may define concrete conventions such as:
- repo layout
- label protocol
- role naming
- issue and comment format
- verification path

Those conventions are template-owned, not plugin-owned.

Users may also invoke templates directly by filename, for example:
- "根据 `main-worker-summary-queue.md` 为我搭建 team"
- "根据 `reviewing.md` 为我搭建 team"

For `main-worker-summary-queue.md`, the default starting shape is `1 main agent + 2 worker agents`. The skill should either reuse existing agents or prepare missing workers when the runtime exposes that capability. If the runtime cannot do that, the skill should stop at a readiness plan and tell the user what is missing.

## Example Requests

These requests should trigger `clawmem-team`:
- "Help me design a ClawMem Team for my research workflow."
- "I want a main / worker / summary queue setup."
- "Set up a reviewing Team on top of ClawMem."
- "Guide me through configuring a custom Team step by step."
- "根据 `main-worker-summary-queue.md` 为我搭建 team"
- "根据 `main-worker-summary-queue.md` 为我搭建 team；如果我现有 agent 不够，就先补齐 worker"
- "根据 `reviewing.md` 为我搭建 team"

## Publishing

This repository is published as a standalone GitHub repo and as a single ClawHub slug:
- slug: `clawmem-team`

Example publish command:

```bash
clawhub --workdir /Users/eric/Agents_project/clawmem-team-skills publish ./skills/clawmem-team \
  --slug clawmem-team \
  --name "ClawMem Team" \
  --version 0.2.1 \
  --tags latest \
  --changelog "Add template readiness checks for multi-agent team setup"
```
