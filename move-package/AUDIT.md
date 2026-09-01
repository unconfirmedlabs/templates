<!--
  Template: audit / security review report for a single Move package.
  One AUDIT.md per package revision, based on the actual review. Do not copy
  conclusions from a prior revision without re-checking them.
-->

# Security Audit — `{{name}}`

**Base revision:** `{{REVISION}}` (`main`; {{network}} `0x{{PACKAGE_ID}}`) ·
**Date:** {{YYYY-MM-DD}} · **Toolchain:** sui {{VERSION}}
{{· **Pinned framework:** `{{FRAMEWORK_REV}}`}}

<!-- One or two sentences up front: is it safe to depend on, and with what
caveats. -->

{{Verdict.}}

## What it is

<!-- Surface inventory: files, line counts, public functions, objects,
capabilities, events, transfers — and explicitly note the absence of each
kind that does not exist. -->

{{Inventory.}}

## {{Why it's safe / Threat analysis}}

<!-- One bullet per security property: privilege, forgery, overdraw/overflow,
access gates, caller patterns. Cite the framework primitives the safety
argument relies on. -->

- **{{Property.}}** {{Analysis.}}

## Verification

<!-- What was run and what passed: test counts per build environment, coverage,
lint status, mutation controls, boundary sweeps, deployed-bytecode source
verification. -->

- {{N/N tests passing under both Testnet and Mainnet build environments,
linted, warnings as errors}}
- {{coverage / mutation / boundary evidence}}

<!-- OPTIONAL: only if the review found issues:

## Findings

| # | Severity | Description | Status |
|---|---|---|---|
| 1 | {{low/medium/high/critical}} | {{description}} | {{open / fixed in REVISION}} |
-->

## Load-bearing assumptions

<!-- Framework or runtime behavior the review depends on; re-verify when the
pinned framework changes. -->

- {{assumption, verified at the pinned revision}}

<!-- OPTIONAL: only for already-published packages:

## Published bytecode

{{`sui client verify-source` result for each network recorded in
`Published.toml`: does the deployed bytecode match the reviewed revision?}}
-->
