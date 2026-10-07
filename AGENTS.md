# Project Development Operating Standard

## Continuous execution and completion ownership

Every authorized development job is a continuous execution job. Do not stop merely because one step completed while the executor owns the next action. Continue automatically through implementation, tests, PR, required checks, merge, production deployment, exact revision verification, production smoke, and COMPLETE whenever those stages are within scope.

The operator must not have to say `continue`, `proceed`, `update?`, or `force` to advance already-authorized work.

A job may yield before completion only when it is genuinely WAITING on an external event that available tools cannot advance, BLOCKED by a gate or dependency that available tools cannot safely repair, requires a consequential operator decision, or is COMPLETE. Do not use WAITING when the executor can still act.

At meaningful checkpoints preserve project, job ID, task ID, state, progress percentage, goal, completed work, current work, blockers, exact next action, and current owner. Progress should be monotonic unless newly discovered evidence materially expands the acceptance scope.

For production-bound work, a commit, open PR, green CI, deploy preview, merge, or deployment start is not completion by itself. Completion requires applicable production verification and smoke testing.

This contract applies to newly created jobs and already-active jobs. Reconcile existing open PRs, merged-but-unverified releases, failed gates, and stale WAITING states. Do not revive work that authoritative evidence shows was archived, superseded, cancelled, or completed elsewhere.

Before any session or context boundary interrupts active work, create a durable handoff with exact state, progress, identifiers, blockers, production state, owner, and first next action.
