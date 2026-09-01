<!--
  Template: the sdk/ directory of a Move + SDK repository. This file is what
  npm renders, so it must be self-contained: install, example, API, tests —
  without requiring the root README. The on-chain source of truth for
  signatures is ../move.
-->

# @unconfirmedlabs/{{name}}

{{One line: what the SDK does (codec, planner, builders) and what it does not
do.}}

## Install

```sh
npm install @unconfirmedlabs/{{name}} @mysten/sui
```

## Usage

```ts
import { {{symbols}} } from "@unconfirmedlabs/{{name}}";

{{minimal example}}
```

## {{Key API}}

<!-- One paragraph per exported entry point, or a link to generated docs.
Keep at most one example per feature; the full API reference lives in the
docs site or the JSDoc. -->

## {{Limits and constraints}}

<!-- The numbers callers must respect: pure-input and signed-transaction byte
limits, protocol versions, gas handling. -->

## Testing

```sh
bun install
bun run golden:check
bun run typecheck
bun test
bun run build
```

## License

MIT — see [../LICENSE](../LICENSE).
