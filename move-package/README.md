<!--
  Template: single Sui Move package, one package per repository (bps/hikida
  layout). Replace every {{PLACEHOLDER}}, delete every comment, remove any
  section marked OPTIONAL that does not apply. See ../README.md and
  ../CHECKLIST.md.
-->

# {{NAME}}

<!-- 1-3 sentences: what it does, which chain, and the headline guarantee or
invariant. No marketing copy. -->

{{One or two sentences describing the package and its key invariant.}}

<!-- OPTIONAL: badge row, e.g.
[![CI](https://github.com/unconfirmedlabs/{{NAME}}/actions/workflows/ci.yml/badge.svg)](https://github.com/unconfirmedlabs/{{NAME}}/actions/workflows/ci.yml)
-->

## Links

<!-- Required once published; delete the section while unreleased. -->

- **Documentation:** {{docs site URL, or "this repository" if none}}
- **SDK:** {{companion npm package or repo, or delete this line}}
- **Deployments:** [`Published.toml`](Published.toml)
- **Audit:** [`AUDIT.md`](AUDIT.md)

## Overview

<!-- What the package is and why it exists, in 1-2 paragraphs. If the package
defines domain objects, capabilities, or key types, list each with one line of
explanation before anything else. -->

{{Overview.}}

<!-- OPTIONAL: only if the package has shared objects, capabilities, or other
stateful domain types:

## Objects and capabilities

| Name | Purpose | Held by |
|---|---|---|
| `{{AdminCap}}` | {{one line}} | {{multisig / owner}} |
-->

## Usage

<!-- How to depend on the package, then one minimal example that compiles and
tests as written. Pin the dependency by revision or checksum, never by
branch. If the package is on the Move Registry, show `mvr add {{name}}`
instead of the git dependency. -->

```toml
# Move.toml
[dependencies]
{{name}} = { git = "https://github.com/unconfirmedlabs/{{name}}.git", rev = "{{PINNED_REVISION}}" }
```

```move
use {{name}}::{{module}};

{{minimal working example}}
```

## API

<!-- One table row per function group (bps style) or one short paragraph per
module (SuiNS style). Keep signatures exact; this is the API surface summary.
Note defaults and width variants explicitly (e.g. "unsuffixed functions take
u64"). -->

| Group | Functions |
|---|---|
| {{Constructors}} | {{`new(...)`, ...}} |

## Behavior and guarantees

<!-- Invariants, exactness, rounding, and total-domain claims that callers can
rely on without re-deriving them. State what is exact and what is not. -->

- {{guarantee 1}}
- {{guarantee 2}}

## Aborts

<!-- Required if the package defines public abort constants; otherwise delete.
One row per constant. Raw abort codes are part of the integration contract. -->

| Code | Constant | When |
|---|---|---|
| {{0}} | `{{EName}}` | {{condition}} |

## Deployments

<!-- Required once published; delete while unreleased. The table is a
convenience pointer: `Published.toml` is the source of truth. Keep one row per
environment — testnet and mainnet package IDs differ. Update the table in the
same commit that updates `Published.toml`. Unconfirmed Labs packages are
published as immutable, so there is no version column. -->

| Network | Package ID | Transaction digest |
|---|---|---|
| Mainnet | [`0x{{PACKAGE_ID}}`](https://suiexplorer.com/package/0x{{PACKAGE_ID}}) | `{{DIGEST}}` |
| Testnet | [`0x{{PACKAGE_ID}}`](https://testnet.suivision.xyz/package/0x{{PACKAGE_ID}}) | `{{DIGEST}}` |

Both deployments are immutable.

## Development

```sh
sui move build --build-env testnet --lint --warnings-are-errors
sui move test --build-env testnet --lint --warnings-are-errors
sui move build --build-env mainnet --lint --warnings-are-errors
sui move test --build-env mainnet --lint --warnings-are-errors
```

`Move.lock` pins the framework revision and dependency graph separately for
Testnet and Mainnet and must be committed with release changes.

<!-- If large suites hit the default gas budget, add the flag and note:
`--gas-limit 100000000000` (Sui 1.66+ lowered the default test gas budget). -->

## Security

<!-- Required for packages that manage user assets or hold capabilities; keep
the reporting line in all cases. List audits per revision: auditor, date,
scope, report. Never claim an audit covers a revision it was not run against.
-->

{{This package was audited at revision {{REVISION}} on {{DATE}} by {{AUDITOR}}.
See [`AUDIT.md`](AUDIT.md).}} Using this package is not a substitute for a
security audit of your own deployment.

Report security issues privately to {{contact@unconfirmed.com}} per
[`SECURITY.md`](SECURITY.md). Do not open a public issue.

<!-- OPTIONAL:

## Formal verification

{{What the prover suite proves, how CI runs it, and where the specs live:
[`formal/README.md`](formal/README.md).}}
-->

<!-- OPTIONAL:

## Design notes

- {{decision and why; include rejected alternatives with measured numbers
when relevant}}
-->

## License

MIT — see [LICENSE](LICENSE).
