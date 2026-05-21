# Contributing to Cypress

Thanks for wanting to contribute. Here's what you need to know.

## What to work on

Check the [issue tracker](../../issues) for open bugs and feature requests. If you want to work on something that isn't filed yet, open an issue first so we can discuss it before you invest time.

## Building

**Requirements:** Visual Studio 2022+ with the .NET desktop and C++ desktop workloads, plus Go 1.22+ for the backend tools.

```sh
# Server DLL (pick one game)
cd Server
cmake --fresh -S . -B build -DCYPRESS_GW2=ON
cmake --build build --config Release

# Launcher
cd Launcher
dotnet publish CypressLauncher.csproj -c Release -f net8.0-windows -o build /p:LangVersion=latest

# Backend (master + relay)
cd tools/cypress-servers
go build ./...
```

See [`.github/workflows/`](.github/workflows/) for the full CI matrix.

## Project layout

```
Server/Source/       C++ server DLL (Frostbite hooks, anticheat, presence)
Launcher/            C# backend (Photino.NET) + HTML/CSS/JS frontend
tools/cypress-servers/  Go master server and relay server
```

## Pull requests

- **One concern per PR.** A bug fix and an unrelated refactor should be separate PRs.
- **Test on the affected game(s).** If you change server DLL code, test it with the relevant game before opening a PR. If you can't test locally, say so in the PR body.
- **Keep the diff small.** Avoid reformatting code outside the lines you're changing.
- **No new warnings.** The C++ build treats warnings as errors on CI.
- Fill out the PR template.

## Code style

- **C++:** follow the style of the surrounding code. No trailing whitespace, no em dashes in comments.
- **C#:** standard .NET conventions. Nullable enabled - don't suppress warnings without reason.
- **Go:** `gofmt`-formatted. Run `go vet` before pushing.
- **JS/HTML:** match the existing style, no external dependencies.

## Reporting bugs

Use the [bug report template](../../issues/new?template=bug_report.yml). Include your Cypress version, OS, game, and steps to reproduce. Logs from the launcher's log panel are very helpful.

## Security vulnerabilities

**Do not open a public issue for security bugs.** See [SECURITY.md](SECURITY.md) for the private disclosure process.
