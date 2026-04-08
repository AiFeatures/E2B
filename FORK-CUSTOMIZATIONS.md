# Fork Customizations

> Upstream: [e2b-dev/E2B](https://github.com/e2b-dev/E2B)
> Fork maintained by: @ashsolei
> Last reviewed: 2026-04-08
> Fork type: **active-dev**
> Sync cadence: **monthly**

## Purpose of Fork

E2B secure code-execution sandbox runtime integrated with iAiFy agent stack.

## Upstream Source

| Property | Value |
|---|---|
| Upstream | [e2b-dev/E2B](https://github.com/e2b-dev/E2B) |
| Fork org | AiFeatures |
| Fork type | active-dev |
| Sync cadence | monthly |
| Owner | @ashsolei |

## Carried Patches

Local commits ahead of `upstream/main` at last review:

- `97adc9c5 chore(ci): adopt enterprise-ci-cd reusables (#12)`
- `03596242 chore(deps-dev): bump requests in /packages/python-sdk (#7)`
- `7b8dc466 chore(deps): bump pygments from 2.19.2 to 2.20.0 in /packages/python-sdk (#9)`
- `e8b05fe8 chore(deps): bump tar from 6.2.1 to 7.5.12 (#11)`
- `adb2562c chore: sync CLAUDE.md and copilot-instructions docs`
- `c466a395 ci: add github-actions ecosystem to dependabot`
- `558dface docs: update FORK-CUSTOMIZATIONS.md with upstream source`
- `485d6a53 docs: add FORK-CUSTOMIZATIONS.md per enterprise fork governance`
- `65d42693 ci: add copilot-setup-steps.yml for Copilot Workspace`
- `dab32c48 chore: add AGENTS.md`
- `d576e08d chore: add copilot-instructions.md`
- `e9e60993 chore: add Copilot Coding Agent setup steps`
- `8090c1ae chore: remove misplaced agent files from .github/copilot/agents/`
- `869f8edc chore: deploy core custom agents from AgentHub`
- `12b6884b chore: deploy core Copilot agents from AgentHub`
- `8db71d5f docs: add FORK-CUSTOMIZATIONS.md`
- `2918582c chore: add CODEOWNERS`
- `a9433b0d chore: add dependabot.yml [governance-orchestrator]`
- `1200fa26 chore: remove workflow typecheck.yml — enterprise cleanup`
- `41f7bc1e chore: remove workflow templates.yml — enterprise cleanup`
- `591922ad chore: remove workflow supabase.yml — enterprise cleanup`
- `69947a09 chore: remove workflow sdk_tests.yml — enterprise cleanup`
- `db34d41b chore: remove workflow release.yml — enterprise cleanup`
- `b04cbcf6 chore: remove workflow python_sdk_tests.yml — enterprise cleanup`
- `5c3f78f6 chore: remove workflow publish_packages.yml — enterprise cleanup`
- ... (6 more commits ahead of `upstream/main`)

## Supported Components

- Root governance files (`.github/`, `CLAUDE.md`, `AGENTS.md`, `FORK-CUSTOMIZATIONS.md`)
- Enterprise CI/CD workflows imported from `Ai-road-4-You/enterprise-ci-cd`

## Out of Support

- All upstream source directories are tracked as upstream-of-record; local edits to core source are discouraged.

## Breaking-Change Policy

1. On upstream sync, classify per `governance/docs/fork-governance.md`.
2. Breaking API/license/security changes auto-classify as `manual-review-required`.
3. Owner triages within 5 business days; conflicts are logged to the `fork-sync-failure` issue label.
4. Revert local customizations only after stakeholder sign-off.

## Sync Strategy

This fork follows the [Fork Governance Policy](https://github.com/Ai-road-4-You/governance/blob/main/docs/fork-governance.md)
and the [Fork Upstream Merge Runbook](https://github.com/Ai-road-4-You/governance/blob/main/docs/runbooks/fork-upstream-merge.md).

- **Sync frequency**: monthly
- **Conflict resolution**: Prefer upstream; reapply iAiFy customizations on a sync branch
- **Automation**: [`Ai-road-4-You/fork-sync`](https://github.com/Ai-road-4-You/fork-sync) workflows
- **Failure handling**: Sync failures create issues tagged `fork-sync-failure`

## Decision: Continue, Rebase, Refresh, or Replace

| Option | Current Assessment |
|---|---|
| Continue maintaining fork | yes - active iAiFy product scope |
| Full rebase onto upstream | feasible on request |
| Fresh fork (discard local changes) | not acceptable without owner review |
| Replace with upstream directly | not possible (local product value) |

## Maintenance

- **Owner**: @ashsolei
- **Last reviewed**: 2026-04-08
- **Reference runbook**: `ai-road-4-you/governance/docs/runbooks/fork-upstream-merge.md`
