# Main Worker Summary Queue Template

Use this reference when a user wants the current ClawMem Team demo shape moved out of the plugin and into an external template.

## Best fit

Use this template when:
- one agent should coordinate
- a worker pool should execute
- work should be visible in a shared queue repo
- task status should advance through an explicit label protocol

## Participant readiness

Use this template with a default starting topology of:
- 1 main agent
- 2 worker agents

Treat fewer than 3 participating agents as not ready for this template. If the user wants a smaller setup, switch to a custom Team design instead of silently shrinking this template.

For each selected participant, track two readiness layers:
- OpenClaw status: `existing`, `to-create`, or `user-confirmed only`
- ClawMem status: `configured`, `bootstrap-on-first-use`, or `blocked`

## Agent selection flow

- If only the current agent is known:
  1. Explain that this template expects `1 main + 2 workers`.
  2. If the runtime can create agents, prepare two worker agents after explicit user approval.
  3. Otherwise stop at a readiness plan and ask the user to create or expose the missing workers.
- If multiple agents already exist:
  1. Inspect or confirm the available agents.
  2. Ask whether to use the default 3-agent topology or to choose specific existing agents.
  3. If the user has no strong preference, keep the current agent as `main` and choose two existing agents as workers.

## Recommended protocol

This template may use a protocol like:
- `queue:task`
- `task-status:todo`
- `task-status:handling`
- `task-status:blocked`
- `task-status:done`
- `assignee:<agent-id>`

These labels belong to this template, not to the ClawMem plugin.

## Recommended blueprint shape

Define:
- one main agent
- two worker agents by default
- one shared summary queue repo
- optional extra workers or private/project repos for deeper execution work when the user already operates a larger pool

## Bootstrap path

1. Inspect or confirm the available agents.
2. Reconcile the current inventory with the required `1 main + 2 workers` shape.
3. Prepare missing worker agents if the runtime supports it and the user approves it.
4. Confirm which agents will act as `main` and `workers`.
5. Confirm the org boundary and who owns the queue repo.
6. Create or reuse the summary queue repo.
7. Create or reuse the team and grants.
8. Write the template contract into the canonical Team artifact.
9. Seed one queue issue to prove the flow works.

## Demo flow

One minimal demo should show:
1. main agent creates a queue task
2. one worker agent starts work and adds a progress comment
3. that worker agent posts the result
4. queue status moves to `task-status:done`
5. the second worker agent can at least see the queue repo and task labels

That is enough to prove the Team works.
