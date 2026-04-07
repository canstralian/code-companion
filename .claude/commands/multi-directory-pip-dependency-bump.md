---
name: multi-directory-pip-dependency-bump
description: Workflow command scaffold for multi-directory-pip-dependency-bump in code-companion.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /multi-directory-pip-dependency-bump

Use this workflow when working on **multi-directory-pip-dependency-bump** in `code-companion`.

## Goal

Updates Python dependencies (pip group) across multiple directories by modifying requirements.txt and/or pyproject.toml files to newer versions, typically via automation (e.g., Dependabot).

## Common Files

- `**/requirements.txt`
- `**/pyproject.toml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify directories with requirements.txt or pyproject.toml files.
- Update dependency versions for specified packages in each file.
- Commit all updated files together with a message listing updated packages and versions.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.