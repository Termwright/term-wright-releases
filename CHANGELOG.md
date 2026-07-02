# Changelog

All notable changes to distributed Termwright builds are documented here.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

_Changes landing in the next release accumulate here._

## [0.1.0] — 2026-07-02

First public build — an early **beta** of Termwright for macOS.

### Added
- Signed (Apple Developer ID) and **notarized** universal macOS build
  (Apple Silicon + Intel), distributed as a `.dmg` — opens without Gatekeeper
  warnings.
- In-app **auto-update**: the app checks this repo's release feed and installs
  signature-verified updates.
- Terminal workspace: tabs, split & floating panes, saved workspaces and layouts.
- Widgets: file explorer with previews, embedded web browser (with devtools),
  system/process monitor, clock.
- Warp-style command **blocks**, command **palette** (⌘K), and autocompletion.
- SSH remote terminals with saved connections.
- AI assistant panel and per-command "explain/fix" actions.
- Deep theming: ~50 themes, per-pane transparency, fonts, and customization.

### Known issues
- This is an early beta (`0.1.0`); expect rough edges. Feedback welcome.

[Unreleased]: https://github.com/Termwright/term-wright-releases/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/Termwright/term-wright-releases/releases/tag/v0.1.0
