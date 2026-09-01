# unconfirmedlabs/templates

Standardized documentation templates for Unconfirmed Labs open source Move
packages.

## Templates

| Template | Use for | Contents |
|---|---|---|
| [`move-package/`](move-package/) | A repository with a single Sui Move package (e.g. `bps`, `hikida`) | `README.md`, `AUDIT.md`, `SECURITY.md` |
| [`move-sdk/`](move-sdk/) | A repository with a Move package plus a TypeScript SDK (e.g. `minato`) | root `README.md`, `move/README.md`, `sdk/README.md` |
| [`CHECKLIST.md`](CHECKLIST.md) | Pre-release verification for any package layout | Release checklist |

## How to use

1. Copy the files for the layout that matches your repository:

   ```sh
   # Single Move package (bps/hikida layout)
   cp templates/move-package/README.md   /path/to/package/
   cp templates/move-package/AUDIT.md    /path/to/package/
   cp templates/move-package/SECURITY.md /path/to/package/

   # Move package + TypeScript SDK (minato layout)
   cp templates/move-sdk/README.md       /path/to/repo/
   cp templates/move-sdk/move/README.md  /path/to/repo/move/
   cp templates/move-sdk/sdk/README.md   /path/to/repo/sdk/
   ```

2. Replace every `{{PLACEHOLDER}}` with the real value.
3. Delete every `<!-- ... -->` guidance comment, and delete any section
   marked `<!-- OPTIONAL ... -->` that does not apply.
4. Verify nothing is left behind:

   ```sh
   grep -rn '{{' --include='*.md' .
   grep -rn '<!--' --include='*.md' .
   ```

5. Work through [CHECKLIST.md](CHECKLIST.md) before publishing or upgrading.

## Template conventions

- `{{UPPER_SNAKE}}` — a value to replace.
- `<!-- ... -->` — author guidance; delete before publishing.
- `<!-- OPTIONAL ... -->` — the section may be removed entirely if it does
  not apply; delete the marker either way.
- Sections are in the recommended order. Do not reorder required sections.
- Keep the same prose style as the existing packages: factual, terse, no
  marketing copy. Every behavioral claim must be verifiable against source
  and tests.

## Grounding

Section choices follow observed conventions from prominent open source smart
contract projects:

- **Sui Move packages:** DeepBook V3 and SuiNS (links block, per-module
  reference, per-environment deployment records, `Published.toml` as source
  of truth), plus docs.sui.io production-readiness requirements.
- **EVM contract projects:** OpenZeppelin (section skeleton, security
  policy), Uniswap v2/v3 (vulnerability disclosure format), Aave v3
  (per-release audit listing).
- **TypeScript SDKs:** `@mysten/sui`, viem, and the Aptos TS SDK (SDK README
  order, and the root-vs-`move/`-vs-`sdk/` responsibility split for
  package+SDK repositories).

Deliberate additions beyond the surveyed field: abort-code tables, a
per-environment deployments table pointing at `Published.toml`, and a
required security section with a private reporting channel — none of the
surveyed Sui projects have all three.
