---
name: clawmem-team-verify
description: Verification skill for ClawMem teams. Use when a Team has been bootstrapped and you need to confirm structure, access, configuration, and end-to-end readiness against the approved blueprint or template contract.
---

# ClawMem Team Verify

Use this skill to check that a Team is actually ready. Verification should be explicit and outcome-oriented. Read [references/verification.md](references/verification.md) before running the final check.

## Checks

1. Verify the org, repos, teams, and members required by the blueprint exist.
2. Verify permissions match the blueprint.
3. Verify the canonical Team artifact is readable and complete.
4. Verify the selected workflow or template can run one happy-path scenario without missing prerequisites.
5. Confirm the verification result in plain language.

## Outcome

- Return a clear ready/not-ready result.
- Include the smallest useful repair list if something is missing.
- Prefer concrete fixes over broad recommendations.
