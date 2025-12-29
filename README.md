# Lessons in AI

Welcome — this repository collects notes, whitepapers, experiments, and practical examples created while exploring AI and machine-learning agents. It's intended as a lightweight, public lab where ideas, designs, and reproducible demos can live and evolve.

## Purpose

- Centralize research notes, design documents, and reproducible examples.
- Host drafts of whitepapers and agent designs that are open for feedback.
- Share small, runnable examples and templates to help others reproduce experiments.

## Basic Structure

- `docs/` — design docs, whitepapers, and long-form notes.
- `examples/` — small runnable examples, notebooks, and demos.
- `src/` — experimental code or utilities (language-specific conventions apply).

This layout is flexible and will grow as new experiments and notes are added.

## How to Use

- Browse `docs/` to read design notes and whitepapers.
- Try the demos in `examples/` to reproduce experiments and learn by doing.
- Open issues to discuss ideas, request reviews, or propose new material — collaboration is welcome.

## Contributing

Contributions are very welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on branches, PRs, and verification steps. Keep changes focused and include clear reproduction or verification instructions for experiments.

## Markdown Style

This repository enforces a set of Markdown rules (see `.markdownlint.json`). Key rules summarized in plain English:

- Headings:
    + The first line must be a top-level heading (`#`).
    + Use ATX-style headings (`#`, `##`, ...); ensure a single space after the `#` characters.
    + Heading levels should only increment by one level at a time (no skipping levels).
    + Only one H1/title is allowed per file.

- Code blocks and fences:
    + Use fenced code blocks (backticks) rather than indented code blocks.
    + Place blank lines before and after fenced code blocks.
    + Include the language identifier for fenced code blocks where applicable.

- Lists:
    + Keep consistent list indentation (4 spaces for sublists).
    + Always include a single space after the list marker.
    + Avoid multiple blank lines around lists; ensure blank lines surround lists where appropriate.

- Links and images:
    + Avoid bare URLs; use explicit links or reference-style links instead.
    + Images must include alt text (no empty alt attributes).
    + Avoid empty link destinations and ensure fragment and reference link validity.

- Emphasis and strong text:
    + Use underscores for emphasis (italic) and asterisks for strong where configured.
    + Do not use emphasis as a heading substitute.
    + Do not include spaces inside emphasis, code, or link markers.

- Spacing and formatting:
    + Do not use multiple consecutive blank lines.
    + Enforce a single trailing newline at end of file.
    + No trailing spaces; trailing punctuation rules are applied where configured.

- Structural checks and other rules:
    + Duplicate sibling headings are flagged.
    + Inline HTML and hard tabs are allowed by configuration (these are optional project choices).
    + Line-length checking is disabled (no hard maximum enforced here).

If you'd like, I can add a short example demonstrating correctly formatted headings, lists, and code blocks.

## Code Style & Verification

This repo primarily uses Rust for experiments; I include a `rustfmt.toml` with preferred settings. When opening PRs, please include verification steps and run relevant checks locally (formatters, linters, and tests) as described in [CONTRIBUTING.md].

All code changes will be run through the appropriate build, test, and lint tooling before merging.

## Issues & Pull Requests

- Use the issue templates when reporting bugs or requesting features.
- Provide a clear description, steps to reproduce (if applicable), and expected behavior.

## License

See the repository `LICENSE` file for licensing details.
