<!--
  Template: root README for a Move package + TypeScript SDK repository
  (minato layout). The root owns the product story and the cross-component
  example. move/README.md owns the on-chain surface; sdk/README.md owns the
  npm package. Never duplicate content across the three — link instead.
-->

# {{Name}}

{{Name}} is a Sui Move package and TypeScript SDK for {{what}}.

## Components

- [`move/`](./move) — {{one line: the on-chain package and its entry points}}
- [`sdk/`](./sdk) — {{one line: the npm package and its capabilities}}

<!-- 1-2 paragraphs: the encoding or wire format, what the planner/verifier
validates, and what the SDK does and explicitly does not do (no RPC, no gas
selection, no signing — or state what it does do). -->

{{Component behavior and boundaries.}}

## Install

```sh
npm install @unconfirmedlabs/{{name}} @mysten/sui
```

## Usage

```ts
import { {{symbols}} } from "@unconfirmedlabs/{{name}}";

{{minimal end-to-end example: plan, verify, build transaction}}
```

{{One line on what the caller still has to supply: gas, execution, the ID of a
compatible published package, ...}}

## Reference

- [Move package](./move/README.md)
- [SDK usage](./sdk/README.md)
- {{docs / format specs / golden vectors / measured results, or delete}}

## Development

```sh
(cd move && sui move test)
(cd sdk && bun install && bun run golden:check && bun run typecheck && bun test && bun run build)
```

<!-- OPTIONAL: only if the package has measured on-chain results worth
publishing:

## {{Network}} benchmark

{{date, package ID, what was executed, and a results table. State which
numbers were measured and which were normalized, and link the artifacts.}}
-->

## License

MIT — see [LICENSE](LICENSE).
