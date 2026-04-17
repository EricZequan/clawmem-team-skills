# Verification Reference

Use this reference to verify a Team against its blueprint.

## Verification layers

### 1. Participants

Confirm the expected participants:
- main, worker, reviewer, or other required roles
- whether the required OpenClaw agents exist
- whether the current OpenClaw environment exposes ClawMem to those agents
- whether each selected agent is `configured`, `bootstrap-on-first-use`, or `blocked`

### 2. Structure

Confirm the expected:
- org
- repos
- teams
- members
- collaborators

### 3. Access

Confirm each actor has the intended access:
- read
- write
- admin

If access is missing, inspect whether the gap is caused by:
- missing membership
- missing team-repo grant
- pending invitation
- wrong repo target

### 4. Contract

Confirm the canonical Team artifact exists and matches the blueprint:
- same roles
- same repo purposes
- same workflow contract
- same verification target

### 5. Happy path

Run one minimal workflow proof:
- create or inspect one queue task
- create or inspect one review request
- verify one actor can act and one result can be observed
- when the template depends on multiple agents, verify each required role has a viable actor

## Result format

Return:
- `ready` when all required checks pass
- `blocked` when the Team cannot be used
- `partial` when the Team exists but one or more required steps remain

Then list the smallest repair actions needed, starting with participant gaps when present.
