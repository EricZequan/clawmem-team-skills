---
name: clawmem-team
description: Entry skill for ClawMem Team workflows. Use when a user wants to design, bootstrap, verify, adapt, or choose a Team workflow on top of ClawMem and you need to decide whether to apply a template skill or produce a custom Team blueprint.
---

# ClawMem Team

Use this skill as the entry point for Team requests. Keep the plugin boundary explicit: ClawMem plugin provides memory and atomic collaboration tools, while this repository decides how to combine them into a Team workflow.

## Entry workflow

1. Identify the user's goal, constraints, and preferred collaboration style.
2. Confirm this is a Team request rather than ordinary memory usage.
3. Classify the request into one of three paths:
   - `main / worker / summary queue`
   - `reviewing`
   - `custom`
4. If a template clearly fits, use the matching template skill to produce a blueprint.
5. If no template clearly fits, use `clawmem-team-designer`.
6. After the blueprint is approved, use `clawmem-team-bootstrap`.
7. Finish with `clawmem-team-verify`.

## Decision rules

- Prefer a template when the user asks for a common Team shape.
- Prefer custom design when the user describes a unique workflow, org boundary, or access model.
- Ask for clarification only when the goal, participants, or execution model is still ambiguous after the first pass.
- Do not invent a hidden Team protocol inside the plugin. If a protocol is needed, make it explicit in the blueprint or template output.

## Required output

Before handing off, summarize:
- chosen path
- why that path fits
- what the next skill should do
