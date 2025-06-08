
# Git Cheatsheet for DevOps & QA

This file provides commonly used Git commands tailored for DevOps, QA, and collaborative development workflows.

---

## 🔧 Setup and Initialization

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git init
```

---

## 📂 Working with Repositories

```bash
git clone https://github.com/username/repo.git
git status
git add filename
git commit -m "Your message"
git push origin main
git pull origin main
```

---

## 🌿 Branching and Merging

```bash
git branch                      # List branches
git branch feature-xyz         # Create new branch
git checkout feature-xyz       # Switch to branch
git checkout -b bugfix-123     # Create and switch
git merge feature-xyz          # Merge into current branch
git branch -d feature-xyz      # Delete branch
```

---

## 🔁 Undoing Changes

```bash
git reset --hard HEAD          # Undo local changes
git checkout -- filename       # Discard changes in a file
git revert <commit_hash>       # Create commit that undoes a previous one
```

---

## 🔍 Viewing History

```bash
git log
git log --oneline --graph
git diff
git diff HEAD~1 HEAD
```

---

## 🧪 QA-Specific Commands

```bash
git blame file.py              # See who wrote each line
git show <commit_hash>         # Show changes from specific commit
```

---

## 🗂 Stashing Work

```bash
git stash                      # Save changes temporarily
git stash list
git stash pop                  # Restore stashed changes
```

---

## 🔐 Git Credentials (HTTPS)

```bash
git config --global credential.helper cache
git config --global credential.helper 'cache --timeout=3600'
```

---

## 📌 Summary Table

| Task                  | Command                          |
|-----------------------|----------------------------------|
| Clone repo            | `git clone <url>`                |
| New branch            | `git checkout -b branch-name`    |
| Stage changes         | `git add <file>`                 |
| Commit changes        | `git commit -m "msg"`            |
| Push to remote        | `git push origin branch-name`    |
| See history           | `git log`, `git log --oneline`  |
| Discard changes       | `git reset --hard`, `checkout`   |

---

