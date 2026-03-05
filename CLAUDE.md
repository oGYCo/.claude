# Global Claude Code Configuration

This file provides persistent instructions for all Claude Code sessions on this machine.

## Package Managers Preference

- **Prefer `bun`** over `npm`/`yarn`/`pnpm` for JavaScript/TypeScript projects when available
- **Use `uv`** for Python projects (not pip directly)
- When multiple package managers are available, ask the user which they prefer

## Build and Test Commands

- **Node.js projects**: Run `bun install` or `pnpm install` to install dependencies
- **Python projects**: Use `uv sync` to install dependencies from pyproject.toml
- **Rust projects**: Use `cargo build`, `cargo test`, and `cargo clippy` for linting
- **Go projects**: Use `go mod tidy` to manage dependencies, `go build` and `go test`

## Code Style

- Use **2-space indentation** for Python and YAML files
- Use **ES modules** (import/export) syntax, not CommonJS (require)
- Destructure imports when possible (e.g., `import { foo } from 'bar'`)
- Use **snake_case** for Python variables and functions, **camelCase** for JavaScript/TypeScript
- Use **PascalCase** for React components and TypeScript classes

## Git Workflow

- Create feature branches from `main` or `master`
- Branch naming: `feature/description`, `fix/description`, or `bugfix/description`
- Write descriptive commit messages (imperative mood: "Add feature" not "Added feature")
- Run tests before committing when applicable
- Use `git rebase` to keep history clean before merging

## Verification

- **Always verify changes** by running tests, building the project, or checking output
- When implementing new features, run the existing test suite to ensure no regressions
- For bug fixes, write a failing test first that reproduces the issue, then fix it
- When unsure about verification steps, ask the user how to verify the changes

## Communication

- Ask clarifying questions when requirements are unclear
- Provide options with tradeoffs when there are multiple approaches
- Point out potential issues or edge cases in the implementation
- If stuck for more than 2-3 attempts, ask the user for guidance instead of continuing blindly

## Permissions

- Sensitive operations (deleting files, force pushing, running sudo) require explicit user approval
- Never read files containing credentials, secrets, or API keys
- Do not execute commands that could cause data loss without explicit confirmation

## Preferences

- Prefer **type-safe** solutions (TypeScript over JavaScript, Rust over Go when applicable)
- Use **composition over inheritance** for code reuse
- Keep functions small and focused on a single responsibility
- Add inline comments only when the logic is non-obvious
- Document public APIs but not internal implementation details
