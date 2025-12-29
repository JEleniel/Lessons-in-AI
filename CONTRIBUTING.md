# Contributing

Thank you for your interest in contributing to this repository. This project collects notes, whitepapers, code samples, and experiments — contributions can be documentation, experiments, bug fixes, or proposed designs.

## Getting started

+ Fork the repository and create a topic branch named like `feat/<short-description>` or `fix/<short-description>`.
+ Keep changes focused and small; one logical change per PR.

## Commit messages

+ Use clear, imperative commit messages (e.g., "Add agent design doc for X").

## Pull requests

+ Open a pull request against the repository's default branch.
+ Include a short description of the change, motivation, and any verification steps.
+ Link related issues when applicable.

## Code standards & verification

+ Follow language-specific style guides. For Rust, run:

 ```bash
 cargo fmt --all -- --check
 cargo clippy --all-targets -- -D warnings
 cargo test --all
 ```

+ For Python or notebooks, include reproduction steps and avoid committing large data files.

## Review process

+ Maintainers will review PRs and may request changes. Respond to review comments and keep commits tidy.

## Communication

+ Use issues to propose major changes, discuss designs, or ask questions.
