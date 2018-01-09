# Git notebook

## Tricks
### View history
Show diff between 2 branches:
```bash
git diff commit_before commit_after
git diff HEAD~1 HEAD
```

Futhermore, to only list files (or with state) only, you can use:
```bash
git diff --name-only commit_before commit_after
git diff --name-state commit_before commit_after
```

### Commit
To append change to the last commit:
```bash
git commit --amend
```
