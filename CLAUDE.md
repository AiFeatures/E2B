Use pnpm for node and poetry for python to install and update dependencies.
Run `pnpm run format`, `pnpm run lint` and `pnpm run typecheck` before commiting changes.
To re-generate the API client run `make codegen` in the repository root.
Run tests on affected codepaths using `pnpm run test`.
Default credentials are stored in .env.local in the repository root or inside ~/.e2b/config.json.

## AgentHub
- Central hub: `~/AgentHub/`
- Skills: `.agents/skills/` (symlinked to AgentHub shared skills)
- MCP: 12 servers synced across all agents
- Agents: 14 shared agents available
- Hooks: Safety, notification, and logging hooks

## Deployment

**Not a container target.** This repo is an SDK monorepo that publishes to npm (TypeScript packages) and PyPI (Python SDK). There is intentionally no `Dockerfile` or `ci-docker.yml` at the repo root.

The release flow is:

- Node packages: pnpm workspace + changesets + `release.yml@v1` → npm registry
- Python SDK: `pyproject.toml` + `release-python.yml@v1` → PyPI via OIDC Trusted Publishers
- Users who want sandbox images build their own from `packages/cli/templates/`

Policy set 2026-04-08 (Wave 4). See `_shared/exec-logs/wave3-dockerfiles.md` for original escalation.
