# Step 1: Install Git

## Objective

Install Git on your operating system and verify that the installation was successful.

## What is Git?

Git is a **Distributed Version Control System (DVCS)** that helps developers track changes in source code, collaborate with teams, and maintain version history.

---

## Download Git

Download Git from the official website:

https://git-scm.com/downloads

Choose the appropriate installer based on your operating system:

- **Windows** – Download **Git for Windows/x64 Setup**
- **macOS** – Download the macOS installer or install using Homebrew
- **Linux** – Install using your distribution's package manager

---

## Install Git

### Windows

1. Download **Git for Windows/x64 Setup**.
2. Run the installer.
3. Keep the default installation options.
4. Click **Install**.
5. Click **Finish**.

### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install git -y
```

### macOS (Homebrew)

```bash
brew install git
```

---

## Verify the Installation

Open **Git Bash**, **Command Prompt**, or **PowerShell** and run:

```bash
git --version
```

Example output:

```text
git version 2.55.0.windows.3
```

If the version is displayed, Git has been installed successfully.

---

## Configure Git

After installing Git, configure your username and email. These details are recorded with every commit.

Set your username:

```bash
git config --global user.name "e5405777"
```

Set your email address:

```bash
git config --global user.email "ky71bm@gmail.com"
```

Configure the default push behavior:

```bash
git config --global push.default simple
```

View all Git configuration settings:

```bash
git config --list
```

Expected output:

```text
user.name=e5405777
user.email=ky71bm@gmail.com
push.default=simple
```

---

## Next Step

Navigate to the directory where you want to store your projects:

```bash
cd Projects
```

Clone an existing GitHub repository:

```bash
git clone https://github.com/username/git-practice.git
```

Replace **username** with your GitHub username.

################################

# Git File States

Git tracks files through different states during the development lifecycle.

## 1. Untracked

**Definition:**
A file that exists in the working directory but has not been added to Git.

**Example:**

```bash
touch sample.txt
git status
```

Output:

```
Untracked files:
    sample.txt
```

**Move to the next state:**

```bash
git add sample.txt
```

---

## 2. Tracked

A tracked file is a file that Git knows about. Once a file is added using `git add`, Git starts tracking it.

Tracked files can be in one of the following states:

- Unmodified
- Modified
- Staged

---

## 3. Unmodified

**Definition:**
A tracked file that has not changed since the last commit.

Example:

```
README.md
```

After committing:

```bash
git commit -m "Initial Commit"
```

The file becomes **Unmodified**.

---

## 4. Modified

**Definition:**
A tracked file that has been changed but the changes have not yet been staged.

Example:

Edit `README.md`.

Run:

```bash
git status
```

Output:

```
Changes not staged for commit:
    modified: README.md
```

Move to the staging area:

```bash
git add README.md
```

---

## 5. Staged

**Definition:**
A file that has been added to the staging area and is ready to be committed.

Example:

```bash
git add README.md
```

Run:

```bash
git status
```

Output:

```
Changes to be committed:
    modified: README.md
```

Commit the changes:

```bash
git commit -m "Updated README"
```

After the commit, the file returns to the **Unmodified** state.

---

# Git File State Workflow

```
           Create File
                │
                ▼
          Untracked File
                │
          git add <file>
                │
                ▼
            Staged File
                │
         git commit -m ""
                │
                ▼
          Unmodified File
                │
      Edit the File
                │
                ▼
          Modified File
                │
          git add <file>
                │
                ▼
            Staged File
                │
         git commit -m ""
                │
                ▼
          Unmodified File
```

## Summary

| State | Description |
|--------|-------------|
| **Untracked** | New file that Git is not tracking. |
| **Tracked** | A file that Git is managing. |
| **Unmodified** | Tracked file with no changes since the last commit. |
| **Modified** | Tracked file that has been changed but not staged. |
| **Staged** | File added to the staging area and ready to be committed. |

> **Note:** There is no **"Unmanaged"** state in Git. The correct term is **Untracked** for files Git is not tracking.