# Skill: git.commit-and-push

Creates a git commit with a message and pushes it to the current branch.

Creates or updates a git commit representing current working tree state.

## Inputs

- message (string)

## Operations

git add -A  
git commit -m "{{message}}"  
git push

## Verification

git log -1 --pretty=oneline

## Rollback

git reset --soft HEAD~1