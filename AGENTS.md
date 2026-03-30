# AGENTS.md — AI Agent Guidelines for os-e

This file provides instructions and context for AI coding agents working in this repository.

## Project Overview

**os-e** is a project hosted in a Sprite environment. Contributions should follow the conventions outlined below.

## Repository Structure

```
/
├── README.md          # Project overview
├── AGENTS.md          # This file — agent guidelines
└── *.md               # Documentation and test files
```

## General Guidelines

- **Keep it simple**: Prefer clear, straightforward solutions over clever ones.
- **Small commits**: Each commit should represent a single logical change.
- **Descriptive naming**: Use clear, intention-revealing names for files, variables, and functions.
- **No secrets**: Never commit API keys, credentials, or environment variables. The Sprite environment may expose HTTP services publicly.

## Code Style

- Use consistent formatting across all files.
- Prefer markdown for documentation files.
- When adding new source files, include a brief comment or header explaining the file's purpose.
- Write self-documenting code; avoid redundant comments that just restate what the code does.

## Commit Conventions

- Use present-tense, imperative mood in commit messages (e.g., "add feature" not "added feature").
- Keep the subject line under 72 characters.
- Reference issue numbers in the commit body when applicable (e.g., `Fixes #12`).

## Testing

- Add or update tests when introducing new functionality.
- Verify changes work before committing — run any applicable test suites.
- Test files follow the `test-*.md` naming pattern for documentation tests.

## Pull Requests

- Provide a clear summary of what changed and why.
- Include a test plan or checklist for reviewers.
- Keep PRs focused — avoid bundling unrelated changes.

## Security

This project runs in a Sprite VM where HTTP services can be publicly accessible.

- **Never** create endpoints that expose environment variables or credentials.
- **Never** serve arbitrary file contents without explicit authorization.
- **Never** create debug or admin routes that dump system internals.
- Sanitize all user input in any web-facing code.

## Working with the Sprite Environment

- Use `sprite-env services` for managing backing services (databases, caches, etc.).
- Use `sprite-env checkpoints` to save and restore project state.
- Refer to `/.sprite/llm.txt` for platform documentation and `/.sprite/llm-dev.txt` for language runtime details.

## File Conventions

| Pattern | Purpose |
|---------|---------|
| `README.md` | Project overview and setup instructions |
| `AGENTS.md` | AI agent guidelines (this file) |
| `test-*.md` | Test and verification documents |
| `.cursor/rules/*.mdc` | Cursor AI rule definitions |

## Adding New Features

1. Understand the existing structure before making changes.
2. Follow established patterns in the codebase.
3. Update documentation (README, AGENTS.md) if the change affects project conventions.
4. Create a checkpoint after confirming the change works.
