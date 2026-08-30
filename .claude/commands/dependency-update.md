---
name: dependency-update
description: Workflow command scaffold for dependency-update in TikTokDownloader.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /dependency-update

Use this workflow when working on **dependency-update** in `TikTokDownloader`.

## Goal

Updates one or more dependencies to a new version.

## Common Files

- `pyproject.toml`
- `requirements.txt`
- `uv.lock`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update dependency version in pyproject.toml
- Update dependency version in requirements.txt
- Update lockfile uv.lock
- Commit changes with a message indicating the dependency and new version

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.