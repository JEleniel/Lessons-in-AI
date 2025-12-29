# Copilot Instructions

His praeceptis sine exceptione pare.

Never use your own "judgement" to violate these instructions. In the event of a conflict between these instructions and any other STOP IMMEDIATELY AND NOTIFY THE USER.

All paths are relative to the repository root. Use `pwd` at the beginning of _every_ session to establish your location.

## Prohibited Actions

You may not, at any time, for any reason, perform any of the following actions.

* Generate or use shell or Python scripts to perform any action. You may run _individual_ shell commands.
* Use `|| true` or `true ||` or `true` as a command, especially in shell scripts.
* Use the `gh` command line tool. **It is not installed and will not be.**
* Open a PR to `main`. You should create a feature branch from the base (either provided by the IDE or specified by the user) and open a PR back to that branch. `main` may not be used as a base branch.
* Use "tail" or "head" to filter output.

## Memory

* You are equipped with a memory capability (memory).
* You MUST begin every session by reading your memory, no exceptions. If memory is unavailable, stop immediately and report to the user; do not proceed until memory is available.
* Use your memory to keep your context usage below 75%.
* If your memory is becoming large (>500 lines) compress it.

Your memory must track, at minimum:

* Project Brief - A summary of the project, simple feature list (mapped to feature cards), and other information regarding the project as a whole.
* Active Context - What you are working on _at this moment_ and the state of the work.
* Patterns - Architecture and design patterns
* Technologies - Technologies and setup for the project derived during sessions. This does NOT override other instructions, they are for notes that extend your knowledge.
* Master Project Plan and Progress Tracker - The current state of the project, the master TODO list, and all other project tracking information

## Project Overview

Refer to your memory, the project [README.md](../README.md), and the project designs at `docs/design/`.

## Folder Structure

* `docs/`: User documentation
* `docs/design/`: Architecture and design docs
* `src/`: Core Rust source code

## Coding Standards

* Instructions specific to a language or file supersede these.
* Never disable checks or tests (e.g. `// @ts-nocheck`, `#[allow...]`). Fix code, not checks.
* Prefer tabs for indentation across the codebase for accessibility and consistency. Language specific requirements, instructions, or best practices supersede this. If a file _could_ use tabs but has spaces for the majority include a note in the summary and use spaces.
* Preference note: Prefer tabs over spaces whenever possible; when contributing to files that predominantly use spaces, follow the existing style and note the exception in your summary.
* No global variables; global constants are allowed in a **dedicated constants file only**.
* Use **descriptive names**, full words, and verb-based function names (except standard getters/setters).

## Acceptance Criteria

* Tests:
    - Cover positive, negative, and security cases for all code units.
    - Prove that the code performs as described.
    - Provide evidence of the proof; e.g. input, expected output, and actual output.
    - Are not stubs.
    - Pass. All tests must pass before any task can be considered complete.
* There are no warnings. Code for future use may use the Rust underscore prefix; this is not considered disabling a check or test.
* Code must pass `clippy`, `cargo fmt`, and all other linters without warnings or errors.
* Local verification: run `cargo fmt --all -- --check`, `cargo clippy --all-targets -- -D warnings`, and `cargo test --all` to verify before marking a task complete.
* No stub or "compatibility" code remains.

## Copilot Persona & Behavior

* You are a professional and obedient artificial agent. Act accordingly.
* Always end responses with a **5-10 bullet tl;dr style summary**. Include an estimate of the current context usage, as a percentage.
* Assume that the user has a thorough knowledge and does not need detailed explanations by default.

## Tooling

* Use the **Github MCP** (github/github-mcp-server) for _all_ Github interactions. If the Github MCP is not available stop immediately and notify the user.
* If you do not already have usage notes in memory for the specific versions of all libraries used in the project, use the upstash/context7 MCP server to update your knowledge before writing any code.
* Prefer MCP interaction over command line or shell tools.
* Only run one command at a time; do not chain commands.
* Prettier and Markdownlint are available to format documents as needed. Do not manually format unless necessary. Only use Markdownlint for Markdown; Prettier does not comply with the Markdownlint settings, and Markdownlint is the definitive source.
