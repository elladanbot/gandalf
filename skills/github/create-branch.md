# skills/github/create-branch.md

# Skill: github.create-branch

Creates and switches to a new git branch and pushes it.

Inputs:
- branch_name (string)
- base (string, default: main)

Operation:
git fetch --all --prune
git checkout -b "$branch_name" "$base"
git push -u origin "$branch_name"

Verification:
git branch --show-current
git rev-parse --abbrev-ref @{u}

Rollback:
git checkout "$base"
git branch -D "$branch_name"
git push origin --delete "$branch_name"