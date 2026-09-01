<!--
  Template: the move/ directory of a Move + SDK repository. The root README
  owns the product story; this file owns the on-chain surface: modules,
  aborts, deployments, build and test.
-->

# {{Name}} (Move)

<!-- 1-2 sentences: what the on-chain package does and its entry points. -->

{{Summary.}}

## Modules

<!-- One row or short paragraph per module and public entry point. -->

| Entry point | Purpose |
|---|---|
| `{{module}}::{{function}}` | {{one line}} |

## Aborts

<!-- One row per public abort constant; delete if there are none. -->

| Code | Constant | When |
|---|---|---|
| {{0}} | `{{EName}}` | {{condition}} |

## Deployments

<!-- One row per environment. `Published.toml` is the source of truth; update
both in the same commit. Unconfirmed Labs packages are published as immutable,
so there is no version column. -->

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

## License

MIT — see [../LICENSE](../LICENSE).
