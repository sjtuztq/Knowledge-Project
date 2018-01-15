# Git notebook

## Tricks
### View history
1. Show diff between 2 branches:
    ```bash
    git diff commit_before commit_after
    git diff HEAD~1 HEAD
    ```

1. Show diff between commit and its parent
    ```bash
    git show
    ```

1. Futhermore, to only list files (or with state) only, you can use:
    ```bash
    git diff --name-only commit_before commit_after
    git diff --name-state commit_before commit_after
    ```

1. List git log with files changed:
    ```bash
    git log --stat
    ```

1. Show different branches
    ```bash
    git log --graph --oneline
    ```

### View diff
 1. diff between working dir and staging area:
    ```bash
    git diff
    ```
 2. diff between staging area and last commit 
    ```bash
    git diff --staged
    ```

### Commit
To append change to the last commit:
```bash
git commit --amend
```
