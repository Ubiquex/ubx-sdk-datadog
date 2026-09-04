# STATE.md — current state

> Rewritten, not appended, as the LAST act of every session. See `HISTORY.md`
> for the narrative.

## In flight

Nothing in flight as of 2026-09-04.

## Blocked

Nothing blocked. Zero open PRs.

## Current state

**`translator-watch.yml` is now live (UBI-249) — the ONLY automated
path that keeps this repo's own `PROVENANCE.json` current.** This
repo's own `hash-watch.yml` was rewritten under UBI-222 to check for
spec drift and open a tracking issue only — confirmed directly, no
`sdk gen` call anywhere in that file, so it never touches
`PROVENANCE.json`. `translator-watch.yml` detects when
`ubx-provider-dynamic`'s own tagged release moves past
`PROVENANCE.json`'s recorded commit, regenerates holding the schema
fixed at this repo's own pinned version, self-heals (`PROVENANCE.json`
only) on an empty diff, opens a real review PR on a genuine one. Never
auto-merges.

This repo's own `--descriptions-dir` fix (a session-wide gap: every
hand regeneration had omitted the flag, so curated description text
never reached generated code comments) and `PROVENANCE.json` bootstrap
(this repo never had one before) both merged this same arc.

Published: npm/PyPI `1.3.1` (verified directly against the registries).
Committed: `1.3.2` (ahead, not yet published — no bump needed until a
real publish is dispatched). `PROVENANCE.json` records a real,
verified `ubx-provider-dynamic` commit (`dba9b68`, tag `v1.0.13`).

`VERSION` at repo root: 2 members, fetched 2026-08-24 from
`[dynamic_provider_groups.datadog_all]` in `ubiquex`'s own
`sdk/providers/.ubx/config` — not re-checked this arc.

## Before touching anything

- Never self-merge here. See `CLAUDE.md`.
- Never hand-edit generated bindings — fix the generator or the upstream
  schema, then regenerate.
