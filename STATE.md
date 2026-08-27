# STATE.md — current state

> Rewritten, not appended, as the LAST act of every session. See `HISTORY.md`
> for the narrative.

## In flight

Nothing in flight as of 2026-08-27.

## Blocked

Nothing blocked. Zero open PRs.

## Current state

Latest known Go module tag: `sdk/go/v1.1.0` (verified directly via `gh api
repos/Ubiquex/ubx-sdk-datadog/tags` — don't trust this file if it's gone
stale, re-check). TypeScript (JSR `@ubx/sdk-datadog`) and Python (PyPI
`ubx-sdk-datadog`) versions are NOT independently verified here — check
`jsr.io`/`pypi.org` directly before assuming they match the Go tag.

`VERSION` at repo root: 2 members, fetched 2026-08-24 from
`[dynamic_provider_groups.datadog_all]` in `ubiquex`'s own
`sdk/providers/.ubx/config`.

## Before touching anything

- Never self-merge here. See `CLAUDE.md`.
- Never hand-edit generated bindings — fix the generator or the upstream
  schema, then regenerate.
