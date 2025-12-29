---
applyTo: '*'
---

# Rust Style Guide

This document defines formatting and style conventions for all Rust source code. These rules are enforced by the project's `rustfmt.toml` configuration.

---

## Formatting Rules

-   **Version** Always use the Rust 2024 or later edition.
-   **Organization** Organize code into modules logically, and use submodules as needed. Minimize top level `*.rs` files by grouping related functionality into modules. Use the 2024 style of `<name.rs>` and `<name>/` directories for modules. Do NOT use `mod.rs` files.
-   **Minimize Lines per File** Aim for a maximum of 200 lines per file. Count all non-blank lines (code, tests, examples, and documentation). Single blank lines do not add to the line count; for consecutive blank lines, count the second and each additional blank line as 1 each. Split large files into smaller, focused modules. Modules should be in files named for the module. Do not mix multiple modules in a single file. Generally, aim to have one significant 'struct' per file. The `#[path = "..."]` attribute may be used to separate tests into separate files.
-   **Function Length:** Limit functions to a maximum of 25 lines. Follow the Single Responsibility Principle. Split large functions into smaller helper functions.
-   **Indentation:** Use hard tabs for indentation. Do not use spaces. Ensure the project's `rustfmt.toml` enforces hard tabs (for example, `hard_tabs = true`). Follow `rustfmt.toml` settings for formatting rules.
-   **Line Endings:** Use Unix-style newlines (`\n`).
-   **Comment Width:** Limit comments to 100 characters per line.
-   **Comment Formatting:** Normalize comments and doc attributes. Wrap comments for readability.
-   **Doc Comments:** Format code in documentation comments. Use `//!` for module/crate docs and `///` for item docs.
-   **Imports:** Group imports by standard, external, and crate. Use crate-level granularity and reorder implementation items.
-   **Hex Literals:** Use uppercase for hex literals.
-   **Macros:** Format macro matchers for clarity.
-   **General:** Normalize all code and documentation attributes.
-   Follow the [2024 Rust Style Guide](https://doc.rust-lang.org/stable/style-guide/index.html) for idiomatic code for all rules not covered here.
-   **Error Handling** `unwrap`, `expect`, and similar calls are not permitted. Use proper error handling instead. (See best practices.)

---

## Best Practices

-   `#[allow...]` is not permitted.
-   Use `thiserror` to define typed error enums for libraries; libraries should return typed errors. Use `anyhow` for binary top-level error handling where appropriate. Avoid `unwrap` and `expect` in library code; binaries may perform top-level handling, log errors, and exit cleanly.
-   Use `clippy` lints to enforce code quality. Address all warnings.
-   Write clear, concise, and well-documented code.
-   Include comments for non-obvious logic.
-   Do not use unsafe code; all code must be 100% safe Rust.
-   Ensure code compiles and passes all tests and lints.

---

## Enforcement

Run rustfmt, clippy, and tests as part of the CI pipeline to enforce these rules. Verify locally with `cargo fmt --all -- --check`, `cargo clippy --all-targets -- -D warnings`, and `cargo test --all`. All code must pass formatting and linting checks before merging.
