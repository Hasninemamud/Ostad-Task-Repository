
# Git Branching, Merge, and Rebase Task

##  GitHub Repository
https://github.com/Hasninemamud/Ostad-Task-Repository

---

# Project Overview

This repository demonstrates Git workflow operations including:

- Branch creation (feature & bugfix)
- Commit management
- Merge strategy
- Rebase strategy
- Interactive rebase (squash & reword)
- Conflict resolution
- Pull request workflow (if applicable)

---

# Branches Created

- feature-payment  
- feature-profile  
- bugfix-login-error  
- feature-rebase-demo  

---

# ⚙️ Commands Used

## 1. Initialize & Check Repo
```bash
git init
git status
git log --oneline
````

---

## 2. Create Branches

```bash
git checkout main
git checkout -b feature-payment
git checkout -b feature-profile
git checkout -b bugfix-login-error
```

---

## 3. Make Commits

```bash
echo "payment feature" >> app.txt
git add .
git commit -m "add payment feature"

echo "profile feature" >> app.txt
git add .
git commit -m "add profile feature"

echo "fix login error" >> app.txt
git add .
git commit -m "fix login error"
```

---

## 4. Merge Strategy

```bash
git checkout main
git merge feature-payment
```

---

## 5. Rebase Strategy

```bash
git checkout feature-profile
git rebase main

git checkout main
git merge feature-profile
```

---

## 6. Conflict Resolution

```bash
git status
# resolve conflicts manually inside file

git add app.txt
git commit
```

---

## 7. Interactive Rebase (Squash & Reword)

```bash
git checkout feature-rebase-demo
git rebase -i HEAD~5
```

Example:

```text
reword <commit-id> commit 1
squash <commit-id> commit 2
squash <commit-id> commit 3
pick <commit-id> commit 4
pick <commit-id> commit 5
```

---

* Branch list (`git branch`)
* Commit history (`git log --oneline --graph`)
* Merge result
* Rebase result
* Conflict resolution screen
* Pull request (if created)

---

# 🔀 Merge vs Rebase

## Merge

* Combines branches using a merge commit
* Preserves full history
* Creates non-linear commit graph

Example:

### Pros

* Safe for shared branches
* Keeps full history

### Cons

* History becomes complex

---

## Rebase

* Moves commits onto another base branch
* Produces linear history
* Rewrites commit history

### Pros

* Clean history
* Easier to read logs

### Cons

* Not safe for shared branches

---

#  Squash vs Reword

## Squash

* Combines multiple commits into one
* Used to clean messy commit history


## Reword

* Changes commit message only
* Does not change code/content

Used during:

```bash
git rebase -i
```



