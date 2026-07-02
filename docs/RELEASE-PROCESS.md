# Release process

How a Termwright build gets from source to a public download here.

## Overview

```
term-wright-desktop (PRIVATE)                 term-wright-releases (PUBLIC, this repo)
  push tag vX.Y.Z                                     Release vX.Y.Z
  └─ CI: build universal ─ sign (Developer ID)        ├─ TermWright_X.Y.Z_universal.dmg
        ─ notarize (Apple) ─ staple                   ├─ TermWright_universal.app.tar.gz (+ .sig)
        └─ publish artifacts here ───────────────────►├─ latest.json   ← updater feed
                                                       └─ release notes (+ CHANGELOG entry)
```

The **source stays private**; only the finished, signed artifacts are published
here, where they're world-downloadable and the auto-updater can reach `latest.json`.

## Steps

1. In `term-wright-desktop`, bump the version (`tauri.conf.json`, `package.json`,
   `src-tauri/Cargo.toml`) and update its `CHANGELOG`.
2. Tag `vX.Y.Z` and push — the release workflow builds, signs (Apple Developer ID),
   and notarizes a universal macOS build.
3. The artifacts are published as a Release **in this repo** (`vX.Y.Z`):
   `*.dmg`, `*.app.tar.gz`, `*.app.tar.gz.sig`, `latest.json`.
4. Add this repo's `CHANGELOG.md` entry for `vX.Y.Z` (mirror the release notes) and
   fill the release body from [`.github/release-notes-template.md`](../.github/release-notes-template.md).
5. Publish the release. `.../releases/latest` now points at it, so the download link
   and the updater feed are live.

## The updater feed

- The app polls `https://github.com/Termwright/term-wright-releases/releases/latest/download/latest.json`.
- GitHub's `/releases/latest/...` resolves to the newest **non-prerelease** release,
  so **publish stable updates as normal releases** (not "pre-release") for the
  updater to serve them. Beta/pre-release builds are still downloadable from their
  own release page, but won't be offered as an auto-update.
- `latest.json`'s asset URLs must point at **this** repo's assets (not the private
  repo), or the updater download 404s.

## Cross-repo publishing (setup note)

Publishing from the private repo's CI into this public repo requires a token with
`contents: write` on `term-wright-releases` (a fine-grained PAT or a GitHub App
installation token), stored as a secret in `term-wright-desktop`. The default
`GITHUB_TOKEN` cannot write across repositories. Until that token is wired, releases
can be published here manually with `gh release create`.
