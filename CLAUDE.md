Use pnpm for node and poetry for python to install and update dependencies.
Run `pnpm run format`, `pnpm run lint` and `pnpm run typecheck` before commiting changes.
To re-generate the API client run `make codegen` in the repository root.
Run tests on affected codepaths using `pnpm run test`.
Default credentials are stored in .env.local in the repository root or inside ~/.e2b/config.json.

## Quick Start

```bash
# JavaScript/TypeScript
npm i e2b          # or: pnpm add e2b

# Python
pip install e2b

# Set API key
export E2B_API_KEY=e2b_***
```

For monorepo dev:

```bash
pnpm install       # install all workspace deps
pnpm run build     # build all packages
pnpm run test      # run tests
make codegen       # regenerate API client from OpenAPI spec
```

## Architecture

SDK monorepo — publishes to npm (TypeScript) and PyPI (Python). No top-level Dockerfile.

- `packages/js-sdk/` — JavaScript/TypeScript SDK (npm: `e2b`)
- `packages/python-sdk/` — Python SDK (PyPI: `e2b`)
- `packages/cli/` — CLI tool; `templates/` contains sandbox base images for self-hosting
- `packages/code-interpreter/` — Code interpreter sandbox extension

Release flow: Node → pnpm workspace + changesets + `release.yml@v1` → npm. Python → `pyproject.toml` + `release-python.yml@v1` → PyPI via OIDC Trusted Publishers.

## Conventions

- Kebab-case package/file names
- Conventional commits (`feat:`, `fix:`, `docs:`, `chore:`)
- Always run format + lint + typecheck before committing (enforced via CI)
- pnpm workspaces — do not use npm or yarn in this repo

## Shared Resources

| Resource | Location |
| --- | --- |
| Reusable CI workflows | `Ai-road-4-You/enterprise-ci-cd` |
| Release workflow | `enterprise-ci-cd/.github/workflows/release.yml@v1` |
| AgentHub | `~/AgentHub/` (central hub, 12 MCP servers) |

## Deployment

**Not a container target.** Users who want sandbox images build their own from `packages/cli/templates/`.
Policy set 2026-04-08 (Wave 4). See `_shared/exec-logs/wave3-dockerfiles.md` for original escalation.

## AgentHub

- Central hub: `~/AgentHub/`
- Skills: `.agents/skills/` (symlinked to AgentHub shared skills)
- MCP: 12 servers synced across all agents
- Agents: 14 shared agents available
- Hooks: Safety, notification, and logging hooks
