# Bootstrap Reference

Use this reference to execute a Team blueprint safely.

## Order of operations

1. Inspect participants and existing state first.
2. Reconcile selected participants and existing state with the blueprint.
3. Prepare missing participants when the blueprint requires them and the runtime exposes that capability.
4. Create missing governance objects.
5. Create missing repos.
6. Apply access and membership.
7. Create the canonical Team artifact.
8. Seed the first workflow object only if the blueprint requires it.
9. Hand off to verification.

## Inspection checklist

Inspect:
- available OpenClaw agents or the user-confirmed participant list
- whether the required agents already exist
- whether each selected agent already has a ClawMem route, will bootstrap on first use, or is blocked
- organizations
- teams
- repo existence
- repo access
- collaborator state
- pending invitations if access is not visible yet

## Mutation rules

- Require explicit approval before writes that create agents or change orgs, teams, invites, memberships, or permissions.
- Only attempt agent creation when the current runtime exposes that capability. Otherwise stop with a readiness gap and ask the user to prepare the missing agents.
- Reuse existing names when they already satisfy the blueprint.
- Do not create extra repos or teams "just in case."
- Keep one authoritative Team artifact. Do not split the contract across multiple uncoordinated places.

## Canonical artifact options

The blueprint may choose one of these:
- markdown document
- bootstrap issue
- durable memory node
- another explicit artifact

When the blueprint does not specify one, stop and ask rather than guessing.

## Seed object

If the Team needs a first runnable example, create only one seed object:
- first queue task
- first review request
- first operating note

That seed object should prove the workflow works without polluting the workspace.
