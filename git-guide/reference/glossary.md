# 📚 Git Glossary
## 📂 Blob

A binary large object that stores the contents of a file. Each version of a file is represented as a separate blob in Git.
**Example:**
```bash
# Git handles blobs internally; you usually don't manipulate them directly
git hash-object README.md 
```

## 🌳 Branch

A parallel line of development in a repository. The most recent commit on a branch is referred to as the tip of that branch.

**Example:**
```bash
git branch feature/login    # create a new branch
git checkout feature/login  # switch to the branch
```
## 🧠 HEAD

A reference to the current commit in the current branch. HEAD points to the tip of the current branch and moves forward as new commits are added.
**Example:**
```bash
git log -1
git rev-parse HEAD
```
## 📄 Commit

A snapshot of changes in the repository. Each commit includes a unique ID, author information, timestamp, and a message describing the changes.
**Example:**
```bash
git add .
git commit -m "Add login functionality"
```
## 🧾 Diff

A comparison between two versions of a file or a set of files, showing the differences introduced by changes.
**Example:**
```bash
git diff                # unstaged changes
git diff --staged       # staged changes
git diff HEAD~1 HEAD    # difference between last two commits
```
## 🔀 Merge

The process of integrating changes from one branch into another. A merge combines the histories of two branches into a single unified history.
**Example:**
```bash
git checkout main
git merge feature/login
```
## 🧪 Rebase

The process of moving or combining a sequence of commits to a new base commit. Rebasing rewrites the commit history to create a linear progression of changes.
**Example:**
```bash
git checkout feature/login
git rebase main
```
## 🧹 Stash

A mechanism to temporarily save changes that are not yet ready to be committed. Stashing allows you to switch branches without losing your uncommitted changes.
**Example:**
```bash
git stash         # save current changes
git stash pop     # reapply stashed changes
```
## 🧩 Tag

A reference to a specific point in the repository's history, typically used to mark release points (v1.0, v2.0, etc.).
**Example:**
```bash
git tag -a v1.0 -m "Version 1.0"
git push origin v1.0
```
## 🔗 Remote

A version of the repository that is hosted on the internet or network. Remotes allow for collaboration and backup of your work.
**Example:**
```bash
git remote add origin https://github.com/user/repo.git
git remote -v
```
## 🏷️ Origin

The default name of the remote repository when cloning a repository.

**Example:**
```bash
git clone https://github.com/user/repo.git
git remote -v   # origin will point to the cloned repository URL
```
## 🧰 Index (Staging Area)

Also known as the staging area, it's where changes are prepared before committing them to the repository.
**Example:**
```bash
git add README.md   # stage changes for commit
git status          # verify staged files
```
## 🧭 Detached HEAD

A state where HEAD points directly to a commit rather than a branch. This allows for inspecting past commits without affecting the current branch.
**Example:**
```bash
git checkout HEAD~2
git log --oneline
```
## 🧾 Cherry-pick

Applies the changes introduced by an existing commit from another branch onto the current branch.
**Example:**
```bash
git checkout main
git cherry-pick abc1234
```
## 🔄 Fetch

The operation of downloading objects and refs from another repository. Fetching updates your local view of the remote repository without modifying your working directory.
**Example:**
```bash
git fetch origin
git log origin/main
```
## 🚀 Push

The process of uploading your local repository content to a remote repository. Pushing sends your commits to the remote server.
**Example:**
```bash
git push origin main
```
## 📥 Pull

The act of fetching from a remote repository and integrating the changes into your current branch. Pulling is a combination of fetching and merging.
**Example:**
```bash
git pull origin main
```
## 🧾 Reflog

A log of where your HEAD and references have been. It records updates to the tips of branches and allows you to recover lost commits.
**Example:**
```bash
git reflog
git checkout HEAD@{3}
```
## 🧰 Worktree

A working directory associated with a repository. It contains the checked-out files and directories that you are working on.
**Example:**
```bash
git worktree add ../feature-branch feature/login
```
## 🧪 Bisect

A binary search algorithm used to find the commit that introduced a bug by testing a range of commits.
**Example:**
```bash
git bisect start
git bisect bad
git bisect good v1.0
```
## 🧩 Submodule

A repository embedded within another repository. Submodules allow you to keep a Git repository as a subdirectory of another Git repository.
**Example:**
```bash
git submodule add https://github.com/lib/repo.git libs/repo
git submodule update --init
```
## 📄 Hook

Scripts that Git executes before or after events such as commits, merges, and push operations. Hooks allow for automation of tasks.
**Example:**
```bash
# .git/hooks/pre-commit
#!/bin/sh
npm test
```
## 🧩 Alias

Custom shortcuts for Git commands, allowing you to define your own commands to simplify repetitive tasks.
**Example:**
```bash
git config --global alias.st status
git st   # runs git status
```