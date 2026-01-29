name: Generate Conventional Commit
description: Generates a conventional commit message based on staged changes
---

# Goal
Analyze the current `git diff --staged` and generate a commit message following the Conventional Commits specification.

# Steps
1.  **Analyze Changes**: Run `git diff --staged` (or check currently changed files) to understand the context of the changes.
2.  **Determine Type**: Classify the change into one of the following types:
    - `feat`: A new feature
    - `fix`: A bug fix
    - `docs`: Documentation only changes
    - `style`: Changes that do not affect the meaning of the code (white-space, formatting, etc)
    - `refactor`: A code change that neither fixes a bug nor adds a feature
    - `perf`: A code change that improves performance
    - `test`: Adding missing tests or correcting existing tests``
    - `build`: Changes that affect the build system or external dependencies
    - `ci`: Changes to our CI configuration files and scripts
    - `chore`: Other changes that don't modify src or test files
    - `revert`: Reverts a previous commit
3.  **Identify Scope**: (Optional) specific section of the codebase (e.g., `auth`, `api`, `ui`).
4.  **Draft Subject**: Write a concise description (imperative mood, no capitalization at start, no period at end).
5.  **Draft Body**: (Optional) If the change is complex, explain *what* and *why* (not *how*). Use bullet points if necessary.

# Output Format
Please output **only** the commit message inside a code block so I can easily copy it. Do not wrap it in quotes.

Example:
```text
feat(auth): add google oauth login support

- Implemented OAuth2 flow for Google
- Added callback handler in AuthController
- Updated user schema to store provider ID