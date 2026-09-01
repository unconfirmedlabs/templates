<!--
  Template: security policy. Keep the reporting channel reachable and the
  supported-versions table current at every publish/upgrade.
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
- On-chain: a patched package version is published and the upgrade is executed
  (or a new package is deployed, if the package is immutable); the new package
  ID is announced in a GitHub Security Advisory.
- SDK (if any): a patched npm release.
- Each fix is published as a GitHub Security Advisory in this repository.

### Supported versions

Patches are released for the latest version of the current major line only.
Critical fixes may be backported to the previous major line.

| Component | Version | Critical fixes | Other fixes |
|---|---|:---:|:---:|
| Move package | {{n.x}} ({{network}} `0x{{PACKAGE_ID}}`) | yes | yes |
| Move package | {{(n-1).x}} | yes | no |

## Legal

This project is open source and provided "as is" without warranty of any kind.
This policy does not create an ongoing duty by any contributor to fix,
maintain, or notify about issues.
