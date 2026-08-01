# git-practice
Learning Git and GitHub basics through hands-on practice.
# Git & GitHub Training Guide

## Table of Contents

1. Introduction to Git
2. What is Version Control?
3. Types of Version Control Systems
4. Why Git?
5. What is GitHub?
6. Install Git
7. Verify Installation
8. Configure Git
9. Create a GitHub Repository
10. Clone a Repository
11. Git Workflow
12. Common Git Commands
13. Git Branching
14. Git Merge
15. Git Ignore
16. Undo Changes
17. Best Practices
18. Troubleshooting

---

# Introduction to Git

Git is a **Distributed Version Control System (DVCS)** used to track changes in source code during software development.

It helps developers:
- Track file changes
- Collaborate with multiple developers
- Maintain code history
- Restore previous versions
- Create feature branches
- Merge changes safely

---

# What is Version Control?

Version Control is a system that records changes made to files over time.

Without Version Control:
- Files get overwritten
- Difficult to recover previous versions
- Collaboration becomes difficult

With Version Control:
- Every change is tracked
- Multiple developers can work together
- Easy rollback to previous versions

Example:

```
Version 1
↓

Version 2
↓

Version 3
↓

Version 4
```

---

# Types of Version Control

### 1. Local Version Control

History stored on a single computer.

Example:
- RCS

### 2. Centralized Version Control (CVCS)

Single central server.

Examples:
- SVN
- CVS

Disadvantage:
If server fails, work stops.

### 3. Distributed Version Control (DVCS)

Every developer has a complete copy of the repository.

Examples:
- Git
- Mercurial

Advantages:
- Fast
- Offline support
- Backup available
- Easy collaboration

---

# Why Git?

Advantages:

- Open Source
- Free
- Fast
- Secure
- Distributed
- Branching support
- Easy merging
- Large community

---

# What is GitHub?

GitHub is a cloud-based platform used to host Git repositories.

Git = Version Control Tool

GitHub = Remote Repository Hosting Service

Examples:

Git Repository (Local Computer)

↓

GitHub Repository (Cloud)

---

# Install Git

## Step 1

Download Git

https://git-scm.com/downloads

## Windows

Download:

**Git for Windows x64 Setup**

## Linux

```bash
sudo apt update
sudo apt install git
```

## macOS

```bash
brew install git
```

---

# Verify Installation

```bash
git --version
```

Example:

```text
git version 2.55.0.windows.3
```

---

# Configure Git

Set Username

```bash
git config --global user.name "e5405777"
```

Set Email

```bash
git config --global user.email "ky71bm@gmail.com"
```

Verify

```bash
git config --list
```

---

# Create a GitHub Repository

1. Login to GitHub
2. Click New Repository
3. Repository Name
4. Description
5. Public/Private
6. Add README
7. Create Repository

---

# Clone Repository

```bash
git clone https://github.com/username/git-practice.git
```

Move into repository

```bash
cd git-practice
```

---

# Git Workflow

Working Directory

↓

Staging Area

↓

Local Repository

↓

Remote Repository (GitHub)

---

# Check Status

```bash
git status
```

---

# Add Files

Single file

```bash
git add file.txt
```

All files

```bash
git add .
```

---

# Commit

```bash
git commit -m "Added README"
```

---

# Push

```bash
git push origin main
```

---

# Pull

```bash
git pull origin main
```

---

# View History

```bash
git log
```

Short format

```bash
git log --oneline
```

---

# Branching

Create Branch

```bash
git branch feature1
```

List Branches

```bash
git branch
```

Switch Branch

```bash
git checkout feature1
```

Create and Switch

```bash
git checkout -b feature1
```

---

# Merge

Switch to main

```bash
git checkout main
```

Merge

```bash
git merge feature1
```

---

# Delete Branch

```bash
git branch -d feature1
```

---

# Git Ignore

Create

```
.gitignore
```

Example

```
*.log
bin/
obj/
node_modules/
```

---

# Undo Changes

Discard file changes

```bash
git restore file.txt
```

Unstage file

```bash
git restore --staged file.txt
```

Undo last commit

```bash
git reset HEAD~1
```

---

# Useful Commands

```bash
git init
git clone
git status
git add
git commit
git push
git pull
git fetch
git log
git diff
git branch
git checkout
git merge
git stash
git remote -v
```

---

# Best Practices

- Commit frequently
- Use meaningful commit messages
- Pull before pushing
- Create branches for new features
- Never commit passwords or secrets
- Use `.gitignore`
- Review changes before committing

---

# Troubleshooting

### Git not recognized

Verify installation:

```bash
git --version
```

Restart the terminal after installation.

---

### Authentication Failed

Use a Personal Access Token (PAT) instead of your GitHub password.

---

### Merge Conflicts

1. Open the conflicting file.
2. Resolve the conflict.
3. Save the file.
4. Add the file.
5. Commit the merge.

---

# References

- https://git-scm.com/docs
- https://github.com
