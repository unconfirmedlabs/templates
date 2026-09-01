<!--
  Template: security policy. Keep the reporting channel reachable and the
  supported-versions table current at every publish.
-->

# Security Policy

Security vulnerabilities in the `{{name}}` package or its components should be
reported privately to {{security@unconfirmedlabs.com}}. Do not open a public
issue.

<!-- OPTIONAL: delete if there is no bounty program.

## Bug bounty

Responsible disclosure is rewarded via {{program link}}.
-->

## Security patches

- Security fixes ship as soon as reasonably possible.
- On-chain: the package is immutable, so a security fix is a new deployment;
  the new package ID is announced in a GitHub Security Advisory.
- SDK (if any): a patched npm release.
- Each fix is published as a GitHub Security Advisory in this repository.

### Supported versions

The latest deployment receives security fixes. Because the package is
immutable, earlier deployments cannot be patched; integrators are responsible
for migrating to a patched package ID.

| Component | Deployment | Critical fixes | Other fixes |
|---|---|:---:|:---:|
| Move package (mainnet) | `0x{{PACKAGE_ID}}` | yes | yes |
| Move package (testnet) | `0x{{PACKAGE_ID}}` | yes | yes |
<!-- Keep the SDK row only if the repository ships an SDK.
| TS SDK (npm) | >= {{n.0.0}} | yes | yes |
-->

## Legal

This project is open source and provided "as is" without warranty of any kind.
This policy does not create an ongoing duty by any contributor to fix,
maintain, or notify about issues.
