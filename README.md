# Essential Git Commands for Daily Use

This README provides a list of commonly used Git commands that are essential for daily development workflows.

---

## Git Configuration

Before starting, configure your Git settings:

```bash
# Set up username and email for Git commits
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set your default editor
git config --global core.editor "code --wait"

# Show colored output for better readability
git config --global color.ui auto
```

---

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

# Show commit history with graph (useful for branches)
git log --oneline --graph --all
```

---

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

# Restore a deleted file before committing
git restore <file>
```

---

## Committing Changes

```bash
# Commit changes in the staging area with a message
git commit -m "Commit message"

# Commit all modified files (bypasses 'git add')
git commit -a -m "Commit message"

# Amend the last commit (useful for fixing commit messages or adding forgotten changes)
git commit --amend

# Sign-off commits (useful in team workflows)
git commit -s -m "Commit message"
```

---

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

# Delete a branch forcefully
git branch -D <branch-name>

# See which branch you’re currently on
git branch --show-current
```

---

## Merging and Rebasing

```bash
# Merge another branch into the current branch
git merge <branch-name>

# Rebase the current branch onto another branch
git rebase <branch-name>

# Continue a rebase after resolving conflicts
git rebase --continue

# Abort a rebase in case of conflict
git rebase --abort
```

---

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

# Drop a stash after applying
git stash drop stash@{index}
```

---

## Remote Repositories

```bash
# Add a new remote repository
git remote add origin <repository-url>

# View all remote repositories
git remote -v

# Fetch changes from the remote repository (without merging)
git fetch

# Pull changes from the remote repository and merge with your local branch
git pull origin <branch-name>

# Pull with rebase (cleaner history)
git pull --rebase origin <branch-name>

# Push commits to the remote repository
git push origin <branch-name>

# Push all local branches to the remote
git push --all origin

# Push tags to remote
git push --tags
```

---

## Undoing Changes

```bash
# Undo changes in working directory (restore last committed version)
git checkout -- <file>

# Restore a file from staging area
git restore --staged <file>

# Unstage a file without discarding changes
git reset <file>

# Reset to a specific commit (hard reset removes all changes)
git reset --hard <commit-id>

# Reset and keep changes in working directory
git reset --soft <commit-id>

# Revert a specific commit by creating a new commit
git revert <commit-id>
```

---

## Tagging

```bash
# List all tags
git tag

# Create a new lightweight tag
git tag <tag-name>

# Create an annotated tag with message
git tag -a <tag-name> -m "Tag message"

# Push tags to remote
git push origin <tag-name>
```

---

## Helpful Shortcuts

```bash
# Short status output
git status -s

# See the changes made since the last commit
git diff

# See changes staged for the next commit
git diff --cached

# Show last commit details
git show

# Show which files are ignored
git check-ignore *

# Clean untracked files (careful!)
git clean -f

# Clean untracked files and directories
git clean -fd
```

---

## Git Workflow Examples (Daily Life Scenarios)

### 1. Start a New Feature

```bash
# Pull latest changes from main
git checkout main
git pull origin main

# Create and switch to a new branch
git checkout -b feature/new-feature
```

### 2. Make Changes and Commit

```bash
# Edit files...

# Stage changes
git add .

# Commit with message
git commit -m "Add new feature logic"
```

### 3. Update with Latest Main

```bash
# Switch to main and update
git checkout main
git pull origin main

# Switch back to your branch
git checkout feature/new-feature

# Rebase on top of main (clean history)
git rebase main
```

### 4. Push to Remote and Create PR

```bash
# Push your feature branch
git push origin feature/new-feature
```

➡️ Now open a Pull Request (PR) on GitHub/GitLab/Bitbucket.

### 5. Merge and Clean Up

```bash
# After PR is merged, delete branch locally
git branch -d feature/new-feature

# Delete branch remotely
git push origin --delete feature/new-feature
```
