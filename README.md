# Termwright — Releases

Public **downloads** and **auto-update feed** for [Termwright](https://github.com/Termwright/term-wright-desktop),
a modern terminal workspace for macOS.

> This repository intentionally contains **no product source code**. The app is
> proprietary; its source lives in the private `term-wright-desktop` repo. This
> repo exists only to host the signed, notarized build artifacts so anyone can
> download the app and so the in-app auto-updater has a public feed to check.

## Download

Get the latest macOS build from the **[Releases page](https://github.com/Termwright/term-wright-releases/releases/latest)**.

- **macOS (Apple Silicon + Intel):** `TermWright_<version>_universal.dmg`
- The build is **signed with an Apple Developer ID and notarized by Apple**, so it
  opens without security warnings. Open the `.dmg` and drag **TermWright** to
  `Applications`.

## Auto-update

The app checks this repo's latest release for updates and installs them after
verifying an Ed25519 signature. Each release ships:

- `TermWright_<version>_universal.dmg` — the installer.
- `TermWright_universal.app.tar.gz` (+ `.sig`) — the update package the app applies.
- `latest.json` — the update manifest the app polls.

## What's in each release

Every release includes human-readable notes (features, fixes, known issues); the
full running history is in [`CHANGELOG.md`](./CHANGELOG.md).

## Links

- Product / source (private): `Termwright/term-wright-desktop`
- Landing page: `Termwright/term-wright-landing-page`
- How releases get published here: [`docs/RELEASE-PROCESS.md`](./docs/RELEASE-PROCESS.md)

---

© 2026 Termwright. All rights reserved. The Termwright application is proprietary
software; downloading it does not grant any license to its source code.
