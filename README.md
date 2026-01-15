# Artagon Workflow Test - Rust

[![CI](https://github.com/artagon/artagon-workflow-test-rust/actions/workflows/ci.yml/badge.svg)](https://github.com/artagon/artagon-workflow-test-rust/actions/workflows/ci.yml)

Test repository for validating [artagon-workflows](https://github.com/artagon/artagon-workflows) Rust CI reusable workflow (when available).

## Status

**Placeholder** - The artagon-workflows repository does not yet have a Rust CI workflow. This repository contains a basic Rust project with a standalone CI that will be converted to use the reusable workflow once available.

## Purpose

Once the Rust workflow is available, this repository will validate:
- Build Rust projects correctly
- Run tests and report results
- Support different Rust versions (stable, beta, nightly)
- Run clippy and rustfmt checks
- Handle custom cargo features
- Generate code coverage

## Project Structure

```
.
├── Cargo.toml
├── src/
│   ├── lib.rs
│   └── main.rs
└── .github/workflows/
    └── ci.yml
```

## Current CI

The placeholder workflow:
- Builds with stable Rust
- Runs tests
- Runs clippy with `-D warnings`
- Checks formatting with rustfmt

## Triggers

- **Push to main** - Validates changes
- **Pull requests** - Pre-merge validation
- **Daily schedule** (2 AM UTC) - Ensure project builds
- **Manual dispatch** - On-demand testing
- **Repository dispatch** - Triggered by [trigger_test_repos.yml](https://github.com/artagon/artagon-workflows/blob/main/.github/workflows/trigger_test_repos.yml)

## Running Locally

```bash
cargo build
cargo test
cargo clippy -- -D warnings
cargo fmt -- --check
```

## TODO

- [ ] Create `rust_ci.yml` reusable workflow in artagon-workflows
- [ ] Update CI to call reusable workflow
- [ ] Add test matrix configurations

## Related

- [artagon-workflows](https://github.com/artagon/artagon-workflows) - Main workflow repository
- [Testing Guide](https://github.com/artagon/artagon-workflows/blob/main/docs/TESTING.md)
