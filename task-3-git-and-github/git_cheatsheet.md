# Git & GitHub Command Cheatsheet

> **Quick Reference for FinTech Data Analysts & Engineers**

---

## 1. Setup & Configuration
```bash
# Set global author name and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# View current configuration
git config --list

# Set default initial branch name to main
git config --global init.defaultBranch main
```

---

## 2. Starting & Cloning Repositories
```bash
# Initialize a new Git repository in current directory
git init

# Clone an existing remote repository
git clone https://github.com/user/repo-name.git

# Clone into a specific folder name
git clone https://github.com/user/repo-name.git my-local-folder
```

---

## 3. Basic Snapshotting & Commits
```bash
# Check working tree status (untracked, modified, staged files)
git status

# Stage a specific file
git add filename.py

# Stage all modified and new files
git add .

# View unstaged line-by-line diffs
git diff

# View staged diffs (ready to be committed)
git diff --staged

# Commit staged changes with an inline message
git commit -m "feat(module): description of changes"

# Modify the most recent commit message or include forgotten staged files
git commit --amend -m "refactor(module): updated commit message"
```

---

## 4. Branching & Switching
```bash
# List all local branches (* marks current branch)
git branch

# List both local and remote tracking branches
git branch -a

# Create a new branch
git branch branch-name

# Switch to an existing branch
git switch branch-name
# (or legacy command: git checkout branch-name)

# Create and immediately switch to a new branch
git switch -c new-feature-branch
# (or legacy command: git checkout -b new-feature-branch)

# Delete a merged branch
git branch -d branch-name

# Force delete an unmerged branch
git branch -D branch-name
```

---

## 5. Synchronizing with Remote Repositories
```bash
# List remote repository aliases and URLs
git remote -v

# Link a remote repository to alias 'origin'
git remote add origin https://github.com/username/repository.git

# Fetch latest commits from remote without merging
git fetch origin

# Fetch and merge changes from remote into current branch
git pull origin main

# Push committed changes to remote repository and set upstream
git push -u origin main

# Standard push once upstream is established
git push
```

---

## 6. Inspecting History & Logs
```bash
# View formatted one-line commit history
git log --oneline

# View commit history with graphical branch topology
git log --oneline --graph --decorate --all

# View changes introduced in a specific commit
git show <commit-hash>

# View who modified each line in a file and when
git blame filename.py
```

---

## 7. Undoing Changes & Recovery
```bash
# Discard changes in a working directory file (revert to last commit)
git restore filename.py

# Unstage a file from the staging area without losing changes
git restore --staged filename.py

# Safely revert a commit by creating a new inverse commit
git revert <commit-hash>

# Temporarily shelve uncommitted working directory changes
git stash

# Restore shelved changes from stash
git stash pop

# List all stashed changes
git stash list
```
