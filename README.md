# Rust Workflow Snippets

Practical Rust snippets for the [Zed editor](https://zed.dev/) focused on common application-development workflows.

The extension provides templates for Tokio, Serde, `thiserror`, `tracing`, Clap, testing, error handling, async traits, and common trait implementations.

Basic syntax already covered by rust-analyzer completions and postfix completions is intentionally excluded.

## Features

* Functions returning `Result` and `anyhow::Result`
* Tokio runtime, tasks, channels, timers, and graceful shutdown
* Error definitions with `thiserror`
* Serialization models and attributes with Serde
* Structured logging and instrumentation with `tracing`
* Common trait implementations
* Async traits
* Clap command-line interfaces
* Cargo feature flags
* Async filesystem operations
* Testing helpers

## Installation

### From the Zed extension gallery

After the extension is published:

1. Open Zed.
2. Open the Extensions page.
3. Search for `Rust Workflow Snippets`.
4. Click **Install**.

### Development installation

Clone the repository:

```shell
git clone https://github.com/Teamofeyy/rust-snippets.git
cd rust-snippets
```

Then:

1. Open Zed.
2. Open the Extensions page.
3. Click **Install Dev Extension**.
4. Select the cloned repository directory containing `extension.toml`.

You can also invoke the following command from the Zed command palette:

```text
zed: install dev extension
```

## Usage

Open a Rust file, enter a snippet prefix, and select the snippet from the completion menu.

For example, enter:

```text
tokio-spawn
```

to produce:

```rust
let handle = tokio::spawn(async move {
    
});
```

Use `Tab` and `Shift+Tab` to move between snippet placeholders.

## Dependencies

This extension only inserts source code. It does not automatically add dependencies to your `Cargo.toml`.

Some snippets require one or more of these crates:

```toml
[dependencies]
anyhow = "1"
async-trait = "0.1"
clap = { version = "4", features = ["derive", "env"] }
serde = { version = "1", features = ["derive"] }
thiserror = "2"
tokio = { version = "1", features = ["full"] }
tracing = "0.1"

[dev-dependencies]
proptest = "1"
tempfile = "3"
```

Only add the dependencies required by the snippets you use.

## Available Snippets

### Functions and error handling

* `fn-result` — Create a function returning `Result`
* `pub-fn-result` — Create a public function returning `Result`
* `async-fn-result` — Create an async function returning `Result`
* `pub-async-fn-result` — Create a public async function returning `Result`
* `fn-anyhow` — Create a function returning `anyhow::Result`
* `async-fn-anyhow` — Create an async function returning `anyhow::Result`

### Tokio runtime and tasks

* `tokio-main` — Create a Tokio async entry point
* `tokio-test` — Create an asynchronous Tokio test
* `tokio-test-result` — Create an asynchronous Tokio test returning `Result`
* `tokio-spawn` — Spawn an asynchronous Tokio task
* `tokio-spawn-blocking` — Run a blocking operation using Tokio
* `tokio-select` — Create a `tokio::select!` block
* `tokio-timeout` — Run a future with a timeout
* `tokio-sleep` — Sleep asynchronously using Tokio
* `tokio-interval` — Create a Tokio interval loop
* `tokio-shutdown` — Wait for a graceful Ctrl+C shutdown signal

### Tokio channels

* `tokio-mpsc` — Create a Tokio MPSC channel
* `tokio-oneshot` — Create a Tokio oneshot channel
* `tokio-watch` — Create a Tokio watch channel

### Tokio filesystem

* `tokio-read-file` — Read an entire file asynchronously
* `tokio-write-file` — Write a file asynchronously
* `tokio-create-dir` — Create a directory and its parent directories asynchronously

### Error types

* `thiserror` — Create an error enum using `thiserror`
* `error-transparent` — Create a transparent `thiserror` variant
* `error-source` — Create a `thiserror` variant containing a source error

### Serde

* `serde-struct` — Create a serializable and deserializable struct
* `serde-default-struct` — Create a Serde struct implementing `Default`
* `serde-tagged-enum` — Create an internally tagged Serde enum
* `serde-rename` — Rename a field during serialization and deserialization
* `serde-skip-none` — Skip serializing an `Option` when it is `None`

### Tracing

* `tracing-instrument` — Instrument a function using `tracing`
* `tracing-instrument-all` — Instrument a function while skipping all arguments
* `tracing-info` — Create a structured info event
* `tracing-debug` — Create a structured debug event
* `tracing-warn` — Create a structured warning event
* `tracing-error` — Create a structured error event
* `tracing-error-debug` — Log an error using both `Display` and `Debug`

### Trait implementations

* `impl-display` — Implement `std::fmt::Display`
* `impl-from-str` — Implement `std::str::FromStr`
* `impl-try-from` — Implement `TryFrom`
* `impl-as-ref` — Implement `AsRef`
* `impl-default` — Implement `Default` manually
* `builder-method` — Create a consuming builder method

### Async traits

* `async-trait` — Create an async trait using `async-trait`
* `impl-async-trait` — Implement an async trait using `async-trait`

### Clap

* `clap-parser` — Create a Clap command-line parser
* `clap-subcommand` — Create a Clap subcommand enum

### Cargo features

* `cfg-feature` — Compile an item only when a Cargo feature is enabled
* `cfg-feature-mod` — Declare a module behind a Cargo feature
* `cfg-feature-pub-mod` — Declare a public module behind a Cargo feature

### Testing

* `test-result` — Create a synchronous test returning `anyhow::Result`
* `proptest` — Create a property-based test using `proptest`
* `tempdir` — Create a temporary test directory using `tempfile`

### Environment variables

* `env-required` — Read a required environment variable

## Design

Rust Workflow Snippets focuses on higher-level application patterns rather than basic Rust syntax.

The extension intentionally avoids snippets that duplicate features already provided by rust-analyzer, including:

* Basic functions, structures, enums, and implementation blocks
* `Option` and `Result` matching
* `if let` and `let else` patterns
* Basic loops
* `Some`, `Ok`, and `Err` wrappers
* `Box`, `Rc`, and `Arc` wrappers
* Basic debug expressions

This keeps the completion menu smaller and reduces conflicts with language-server suggestions.

## Attribution

This project is based on [Rust Snippets for Zed](https://github.com/bobbymannino/rust-snippets-for-zed), originally created by Bobby Mannino.

The original extension provided the initial project structure and basic Rust snippets.

This fork is maintained by [Teamofeyy](https://github.com/Teamofeyy) and focuses on practical Rust workflows that are not already covered by rust-analyzer.

The original copyright notice and MIT license have been retained.

## Contributing

Contributions are welcome.

When proposing a new snippet, please ensure that it:

* Saves a meaningful amount of repetitive code
* Represents a commonly used Rust workflow
* Does not duplicate an existing rust-analyzer completion
* Uses clear and consistent placeholders
* Has a unique and descriptive prefix

Before submitting a pull request, install the repository as a Zed development extension and test the snippet in a Rust file.

## License

This project is distributed under the MIT License. See [LICENSE](./LICENSE) for details.
