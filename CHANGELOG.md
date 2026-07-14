# Changelog

All notable changes to this project are documented in this file.

## v0.1.0

This is the first release of Rust Workflow Snippets, based on the original Rust Snippets for Zed extension by Bobby Mannino.

### Added

* Function templates returning `Result` and `anyhow::Result`
* Tokio runtime, task, channel, timeout, interval, and shutdown snippets
* Async test snippets
* `thiserror` error enum and error variant snippets
* Serde structure, enum, and field attribute snippets
* Structured `tracing` event and instrumentation snippets
* Common trait implementation snippets
* Async trait snippets
* Clap parser and subcommand snippets
* Cargo feature-gating snippets
* File-system and environment-variable snippets
* Property-testing and temporary-directory snippets

### Changed

* Renamed the extension to Rust Workflow Snippets
* Changed the extension ID to `rust-workflow-snippets`
* Updated the extension description and repository metadata
* Expanded the author list to retain the original author and identify the current maintainer
* Refocused the snippet collection on practical workflows not already covered by rust-analyzer

### Removed

* Snippets that duplicate rust-analyzer completion and postfix functionality
* Redundant variants of basic Rust syntax snippets

---

## Upstream history

Versions `0.0.1` through `0.0.4` were released as part of the original
[Rust Snippets for Zed](https://github.com/bobbymannino/rust-snippets-for-zed)
project by Bobby Mannino.

## v0.0.4

### Added

* `win-only` — Windows-only configuration attribute
* `mac-only` — macOS-only configuration attribute
* `linux-only` — Linux-only configuration attribute
* `ios-only` — iOS-only configuration attribute
* `android-only` — Android-only configuration attribute

## v0.0.3

### Added

* `if-some` — `if let Some` pattern matching
* `clone-struct` — structure deriving `Clone`
* `debug-struct` — structure deriving `Debug`
* `clone-and-debug-struct` — structure deriving `Clone` and `Debug`

## v0.0.2

### Added

* `match-option` — match an `Option`
* `match-result` — match a `Result`

## v0.0.1

### Added

* `let-vec` — initialize an immutable vector
* `mut-vec` — initialize a mutable vector
