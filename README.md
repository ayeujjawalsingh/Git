# Essential Git Commands for Daily Use

This README provides a list of commonly used Git commands that are essential for daily development workflows.

---
## Git Configuration

Before starting, configure your Git settings:

```bash
# Set up username and email for Git commits
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Basic Commands

```bash
# Initialize a new Git repository
git init

# Clone an existing repository
git clone <repository-url>

# Check the status of your working directory and staging area
git status

# View commit history
git log

# Display a concise one-line log of commits
git log --oneline
```

## Working with Files

```bash
# Add a file or directory to the staging area
git add <file-or-directory>

# Add all changed files to staging area
git add .

# Remove a file from the working directory and stage the removal
git rm <file>

# Move or rename a file
git mv <old-filename> <new-filename>
```

## Committing Changes

```bash
# Commit changes in the staging area with a message
git commit -m "Commit message"

# Commit all modified files (bypasses 'git add')
git commit -a -m "Commit message"

# Amend the last commit (useful for fixing commit messages or adding forgotten changes)
git commit --amend
```

## Branching

```bash
# List all branches
git branch

# Create a new branch
git branch <branch-name>

# Switch to a branch
git checkout <branch-name>

# Create and switch to a new branch
git checkout -b <branch-name>

# Delete a branch (locally)
git branch -d <branch-name>
```

## Merging and Rebasing

```bash
# Merge another branch into the current branch
git merge <branch-name>

# Rebase the current branch onto another branch
git rebase <branch-name>

# Abort a rebase in case of conflict
git rebase --abort
```

## Stashing

```bash
# Save changes temporarily and clean working directory
git stash

# Apply the most recent stash and remove it from the stash list
git stash pop

# List all stashes
git stash list

# Apply a specific stash
git stash apply stash@{index}
```

## Remote Repositories

```bash
# Add a new remote repository
git remote add origin <repository-url>

# View all remote repositories
git remote -v

# Fetch changes from the remote repository
git fetch

# Pull changes from the remote repository and merge with your local branch
git pull origin <branch-name>

# Push commits to the remote repository
git push origin <branch-name>

# Push all local branches to the remote
git push --all origin
```

## Undoing Changes

```bash
# Undo changes in working directory (restore last committed version)
git checkout -- <file>

# Unstage a file without discarding changes
git reset <file>

# Reset to a specific commit (hard reset removes all changes)
git reset --hard <commit-id>

# Revert a specific commit by creating a new commit
git revert <commit-id>
```

## Tagging

```bash
# List all tags
git tag

# Create a new tag
git tag <tag-name>

# Push tags to remote
git push origin <tag-name>
```

## Helpful Shortcuts

```bash
# Short status output
git status -s

# See the changes made since the last commit
git diff

# See changes staged for the next commit
git diff --cached
```
