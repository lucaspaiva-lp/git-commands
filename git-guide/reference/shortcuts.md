## ⚡ Quick Shortcuts & Tips

Here are some practical Git shortcuts and tips to make your workflow faster and more efficient:

### Quick Status Check
```
git st    # shortcut for 'git status'
```
### One-line Log
```
git lg    # custom alias for 'git log --oneline --graph --decorate --all'
```

**💡Tip:** Shows a concise, visual representation of the commit history.

### Add and Commit in One Step
```
git ac "Commit message"   # custom alias for 'git add . && git commit -m'
```
### Undo Last Commit (Keep Changes)
```
git reset --soft HEAD~1
```
### Discard Local Changes in a File
```
git checkout -- filename
```
### Pull with Rebase
```
git pull --rebase
```

**💡Tip:** Keeps the history linear and avoids unnecessary merge commits.

### View All Branches
```
git branch -a
```
**💡Tip:** Includes both local and remote branches.

### Delete Local Branch
```
git branch -d feature/login
```
### Delete Remote Branch
```
git push origin --delete feature/login
```
### Show Last Commit Details

```
git show
```

### 💡 Tips for efficiency:

- Use aliases to shorten frequently used commands.

- Explore tab completion to quickly fill branch names or paths.

- Combine commands with && for repetitive tasks, e.g., git add . && git commit -m "message".