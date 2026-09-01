# Release checklist

Work through this before publishing or tagging a release. Each item maps to a
template section that must be updated in the same commit.

## Code

- [ ] Linted builds and tests pass under both `--build-env testnet` and
      `--build-env mainnet` with `--warnings-are-errors`.
- [ ] `Move.lock` is committed and its framework revisions match the intended
      environments.
- [ ] Dependencies in `Move.toml` are pinned by revision or checksum, never
      by branch.
- [ ] New public abort constants are documented in the README `Aborts` table.
- [ ] Behavior changes have tests that land with the code.

## Documentation

- [ ] README description and guarantees match current behavior (when sources
      disagree, verify against source and tests).
- [ ] No template leftovers: `grep -rn '{{' --include='*.md' .` and
      `grep -rn '<!--' --include='*.md' .` return nothing.
- [ ] The `API` table matches the actual public surface (compare normalized
      pre/post package summaries when the API changes).
- [ ] The `Deployments` table has one row per environment and matches
      `Published.toml`.

## Deployment

- [ ] `Published.toml` is committed and reflects the new publish.
- [ ] Deployed bytecode is verified against source (`sui client
      verify-source`) for each network recorded in `Published.toml`.
- [ ] The package is published as immutable (`make_immutable` destroys the
      `UpgradeCap`), and the publish transaction digests are recorded in the
      README `Deployments` table.

## Security

- [ ] `AUDIT.md` exists for the deployed revision (required for packages that
      manage user assets or hold capabilities); conclusions are not copied
      from a prior revision without re-checking.
- [ ] `SECURITY.md` lists a reachable private reporting channel and a current
      supported-versions table.
- [ ] `LICENSE` matches the `license` field in `Move.toml` and the README
      `License` section.
