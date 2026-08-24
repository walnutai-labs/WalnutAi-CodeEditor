# WalnutAI Editor — Releases

This repository hosts **release builds** of the WalnutAI Editor. The source code
lives in a private repository; nothing here but this file, the release
pipeline, and the published builds.

## Download

Grab the latest build from the [Releases](../../releases) page:

| Asset | What it is |
|---|---|
| `WalnutAI-Setup-x64-<tag>.exe` | Windows 10/11 x64 installer (per-user, no admin needed) |
| `WalnutAI-win32-x64-<tag>.zip` | Portable build — unzip anywhere and run `WalnutAI.exe` |

> **Windows SmartScreen:** current builds are not yet code-signed. If Windows
> shows "Windows protected your PC", click **More info → Run anyway**.

## First run

1. Install (or unzip) and launch **WalnutAI**.
2. Sign in with your Walnut account when prompted — the editor connects to
   your Walnut workspace and loads your projects.
3. For test-case recording and local execution, install and run the Walnut
   Agent on the same machine.

## For maintainers — cutting a release

1. Push the release tag to the source repository (GitLab), e.g. `editor-v0.1.0`.
2. Make sure the engine branch to bundle is pushed as well.
3. Here on GitHub: **Actions → Release Editor → Run workflow**, enter the tag
   (and engine ref, default `cloud-agent`).
4. The workflow builds on `windows-latest` and uploads both assets to the
   release for that tag. Tags containing a `-` suffix (e.g. `-alpha.1`) are
   published as pre-releases.

Required repository secret: `GITLAB_TOKEN` — a read token for the source
repositories.
