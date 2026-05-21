# Security Policy

## Scope

This policy covers vulnerabilities in:

- The Cypress launcher (C# / WebView2 frontend)
- The server DLL (C++ / GW1, GW2, BFN)
- The master server and relay server (Go)

It does **not** cover vulnerabilities in the underlying games, or issues that require physical access to the host machine.

## Reporting a Vulnerability

**Do not open a public GitHub issue for security bugs.** This gives attackers a head start before a fix is available.

Instead, report privately via one of:

- **Discord DM:** reach out to `@v0e` or any other project maintainer in the [PvZ FB Modding Server](https://discord.gg/yGrY7dJKVg)
- **GitHub private advisory:** use [Security -> Report a vulnerability](../../security/advisories/new) on this repo

Include:
- A description of the vulnerability and its impact
- Steps to reproduce or a proof-of-concept (even partial is fine)
- Which component and version is affected
- Whether you believe it is being actively exploited

## What to Expect

We'll acknowledge your report within **48 hours** and aim to release a fix within **14 days** for critical issues. We'll credit you in the release notes unless you prefer to remain anonymous.

## Supported Versions

Only the latest release is actively maintained. If you're on an older version, please update before reporting.
