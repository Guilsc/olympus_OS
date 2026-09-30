# Olympus_OS project rules

This directory is the canonical Olympus_OS project root.

- Treat files under this directory as the project source of truth.
- Do not create or import project instructions from legacy locations outside this workspace.
- Read `OLYMPUS.md` for canonical Olympus architecture.
- Read `ZEUS_INSTRUCTIONS.md` when acting as Zeus or handling Zeus governance.
- Preserve provenance when moving or importing project artifacts.
- Keep Hermes runtime/configuration under `C:\Users\nomeusuario\AppData\Local\hermes`; keep Olympus project files here.

## Agent-specific instructions

- When operating as the `hermes-agent` profile, retrieve and follow the canonical `04_SYSTEM/Agents/Hermes-agent/HERMES_AGENT_INSTRUCTIONS.md` for Olympus orchestration work.
- This Hermes-agent instruction does not replace or modify the Zeus instruction chain. When acting as Zeus, follow `ZEUS_INSTRUCTIONS.md` instead.

# Repository AI & Engineering Standards

This file also defines the shared engineering, Git, pull request, and documentation standards for this repository.

These rules apply regardless of which tool or agent performs the work, including Codex, ChatGPT, Hermes, GitHub Copilot, cloud agents, local IDE agents, or human contributors.

The repository is the source of truth.

## General Behavior

- Follow the existing architecture, conventions, and project structure before introducing new patterns.
- Prefer minimal, focused changes over broad unrelated refactors.
- Do not overwrite unrelated work.
- Do not expose secrets, credentials, tokens, private keys, or sensitive configuration.
- Use placeholders such as `<YOUR_API_KEY>` in examples and documentation.
- Preserve backward compatibility unless a breaking change is explicitly required.
- Inspect existing code and documentation before creating duplicate abstractions or files.
- Run relevant validation before considering implementation work complete.
- Report validation failures clearly instead of hiding or bypassing them.

## Git Workflow

Git operations are conditional.

Do not assume that every task requires a branch, commit, pull request, or merge.

When Git operations are requested or are part of the current workflow, follow the standards below.

### Branches

- Never commit directly to a protected default branch when the repository workflow requires a feature branch.
- Use short, descriptive branch names.
- Prefer Conventional Commit types as branch prefixes when appropriate.

Examples:

```text
feat/add-user-auth
fix/payment-timeout
docs/update-setup-guide
refactor/api-client
chore/update-ci
```

## Commit Messages

Strictly follow Conventional Commits.

Format:

```text
<type>[optional scope]: <description>
```

Allowed types:

- `feat`: a new feature
- `fix`: a bug fix
- `docs`: documentation-only changes
- `style`: formatting or whitespace changes without logic changes
- `refactor`: code restructuring without changing behavior or fixing bugs
- `test`: adding or updating tests
- `chore`: build, configuration, tooling, dependency, or maintenance changes

Rules:

1. Write commit messages in English.
2. Use imperative mood.
3. Start the description with a lowercase letter.
4. Do not end the subject line with a period.
5. Keep the first line under 72 characters.
6. Keep each commit focused on one logical change when practical.

Examples:

```text
feat(auth): add OAuth login
fix(api): handle expired access tokens
docs: update local setup instructions
refactor(storage): simplify file adapter
test(auth): add login failure coverage
chore(ci): update node version
```

## Pull Requests

Do not create a pull request unless the current workflow requires one.

When creating a pull request, use the following standards.

### Pull Request Title

Format:

```text
<type>[optional scope]: <short description in imperative mood>
```

### Pull Request Description

Use this structure:

```markdown
## Summary

Describe what changed and why.

## Changes

- List the major modifications.
- Keep the list focused on meaningful changes.

## How to Test

1. Provide clear verification steps.
2. Include commands when useful.
3. Mention automated tests or checks that were run.

## Breaking Changes

Describe breaking changes, migrations, required configuration changes,
or environment variable updates.
```

Omit the `Breaking Changes` section when there are no breaking changes.

### Pull Request Quality

Before opening a pull request:

- run relevant tests
- run linting when available
- run type checking when available
- run the relevant build when practical
- verify changed behavior
- review the diff for accidental changes
- remove temporary debugging code
- ensure no secrets were committed

If a validation step cannot be completed, state exactly which check was not run and why.

## Merging

Do not merge a pull request unless explicitly requested or the active workflow authorizes automated merging.

Before merging:

- required CI checks must pass
- blocking review requirements must be satisfied
- unresolved conflicts must be fixed
- required migrations or environment changes must be documented

Do not bypass repository protections.

## README Standards

When creating or substantially updating `README.md`, use the following structure where applicable.

1. Title & Tagline
2. Table of Contents for long documents
3. Features
4. Tech Stack & Prerequisites
5. Getting Started / Setup
6. Usage
7. Project Structure
8. Contributing & License

README rules:

- Use standard Markdown.
- Keep wording direct and practical.
- Avoid unnecessary marketing language.
- Prefer examples over vague explanations.
- Keep commands copy-paste friendly.
- Use placeholders instead of real secrets or environment-specific credentials.
- Keep documentation consistent with the current implementation.

## Code Changes

Before changing code:

1. inspect the relevant files
2. understand existing patterns
3. identify tests or validation associated with the area
4. avoid introducing duplicate functionality

When implementing:

- keep changes scoped to the requested task
- preserve existing behavior unless intentionally changing it
- prefer existing utilities and abstractions when appropriate
- avoid speculative architecture
- add or update tests when behavior changes
- update documentation when developer-facing behavior changes

## Validation

Use the repository's existing validation commands when available.

Typical examples include:

```bash
npm test
npm run lint
npm run typecheck
npm run build
```

Do not invent commands that are not supported by the repository.

When no automated validation exists, perform the strongest reasonable manual verification available.

## Repository-Specific Rules

More specific instructions may exist deeper in the repository.

When a nested `AGENTS.md` or equivalent project instruction file exists, apply the most specific instructions relevant to the files being changed.

Repository-specific instructions may extend these standards.

They should not silently weaken security, testing, Git safety, or secret-handling requirements.

## Tool Independence

These standards do not depend on a specific IDE, agent, or automation platform.

Any tool performing repository work should:

- inspect these instructions before making changes
- follow repository conventions
- apply Git standards when Git operations are performed
- apply pull request standards when a pull request is created
- apply documentation standards when documentation is modified
- respect existing repository protections and CI requirements

The repository remains the canonical source of engineering instructions.
