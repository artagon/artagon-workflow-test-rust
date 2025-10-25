# Artagon Workflows - Rust CI Test Repository

This repository will test the [artagon-workflows](https://github.com/artagon/artagon-workflows) Rust CI reusable workflow once it's available.

## Status

⚠️ **Placeholder Repository** - The artagon-workflows repository does not yet have a Rust CI workflow. This repository contains a basic Rust project and placeholder CI configuration that will be updated once the Rust workflow is added.

## Purpose

Once the Rust workflow is available, this repository will validate that it:
- Builds Rust projects correctly
- Runs tests and reports results
- Supports different Rust versions (stable, beta, nightly)
- Runs clippy and rustfmt checks
- Handles custom cargo features
- Uploads build artifacts
- Works with various configurations

## Current Configuration

The placeholder CI workflow currently:
- Builds the project with stable Rust
- Runs all tests
- Runs clippy with warnings as errors
- Checks code formatting with rustfmt

## Triggers

This workflow runs on:
- **Push to main** - Validates changes to this test repo
- **Pull requests** - Validates PRs before merge
- **Daily schedule** (2 AM UTC) - Ensures the project still builds
- **Manual dispatch** - On-demand testing with custom Rust version
- **Repository dispatch** - Can be triggered by artagon-workflows

## Project Structure

```
.
├── Cargo.toml             # Rust package manifest
├── src/
│   ├── lib.rs             # Library code
│   └── main.rs            # Binary code
└── .github/
    └── workflows/
        └── ci.yml         # Placeholder workflow
```

## Test Project

This is a minimal Rust project with:
- **Edition**: Rust 2021
- **Type**: Binary and library crate
- **Tests**: Unit tests and integration tests
- **Dependencies**: None (minimal project)

## Running Locally

```bash
# Build the project
cargo build

# Run tests
cargo test

# Run with verbose output
cargo test --verbose

# Check code with clippy
cargo clippy -- -D warnings

# Format code
cargo fmt

# Check formatting without modifying
cargo fmt -- --check

# Build release version
cargo build --release
```

## Future Test Matrix

Once the Rust workflow is available, this repository will test:

| Test | Rust Version | Features | Tests | Clippy | Rustfmt |
|------|--------------|----------|-------|--------|---------|
| Default | stable | - | ✓ | ✓ | ✓ |
| Stable | stable | - | ✓ | ✓ | ✓ |
| Beta | beta | - | ✓ | ✓ | ✓ |
| Nightly | nightly | - | ✓ | ✓ | ✓ |
| Custom Features | stable | feature1 | ✓ | ✓ | ✓ |
| Skip Tests | stable | - | ✗ | ✓ | ✓ |

## TODO

- [ ] Wait for artagon-workflows to add Rust CI workflow
- [ ] Update `.github/workflows/ci.yml` to call reusable workflow
- [ ] Add test matrix configurations
- [ ] Add coverage upload configuration if supported

## Related

- [artagon-workflows](https://github.com/artagon/artagon-workflows) - Main workflow repository
- [Testing Strategy](https://github.com/artagon/artagon-workflows/blob/main/.model-context/TESTING_STRATEGY.md) - Overall testing approach
