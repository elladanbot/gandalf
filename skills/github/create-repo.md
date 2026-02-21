# skills/github/create-repo.md

# Skill: github.create-repo

Creates a GitHub repository using GitHub CLI.

Inputs:
- repo_name (string)
- visibility (public|private)

Operation:
gh repo create "$repo_name" --"$visibility" --confirm

Verification:
gh repo view "$repo_name"

Rollback:
gh repo delete "$repo_name" --yes