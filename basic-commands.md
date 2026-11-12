# Basic Git Commands

A beginner-friendly guide to the most important Git commands, with practical examples.
Every example follows one small story: you join a team project called **GitHub-Guide** and make your first contribution.

---

## Table of Contents

1. [Initial Setup](#1-initial-setup)
2. [Creating or Getting a Repository](#2-creating-or-getting-a-repository)
3. [The Basic Workflow](#3-the-basic-workflow)
4. [Viewing History and Differences](#4-viewing-history-and-differences)
5. [Working with Remote Repositories](#5-working-with-remote-repositories)
6. [Undoing Changes](#6-undoing-changes)
7. [Quick Cheat Sheet](#7-quick-cheat-sheet)

---

## 1. Initial Setup

Before using Git for the first time, tell it who you are. This information is attached to every commit you make.

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Check your settings:

```bash
git config --list
```

> **Tip:** Use the same email address as your GitHub account so your commits are linked to your profile.

---

## 2. Creating or Getting a Repository

### `git init`: start a new repository

Turns the current folder into a Git repository.

```bash
mkdir GitHub-Guide
cd GitHub-Guide
git init
```

Output:

```
Initialized empty Git repository in /path/to/GitHub-Guide/.git/
```

### `git clone`: copy an existing repository

Downloads a full copy of a repository from GitHub (including its entire history).

```bash
git clone https://github.com/your-team/GitHub-Guide.git
cd GitHub-Guide
```

> In a group project, **one member creates the repository** and everyone else **clones** it.

---

## 3. The Basic Workflow

Git has three main areas:

```
Working Directory  --git add-->  Staging Area  --git commit-->  Local Repository
 (your files)                  (ready to save)                    (saved history)
```

### `git status`: see what is going on

Shows which files are changed, staged, or untracked. **Use it often!**

```bash
git status
```

Example output:

```
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        basic-commands.md
```

### `git add`: stage changes

Moves changes into the staging area, marking them to be included in the next commit.

```bash
# Stage one file
git add basic-commands.md

# Stage several files
git add README.md basic-commands.md

# Stage everything that changed
git add .
```

### `git commit`: save a snapshot

Records the staged changes in the history, along with a message.

```bash
git commit -m "Add basic Git commands guide"
```

Example output:

```
[main 3f2a9c1] Add basic Git commands guide
 1 file changed, 45 insertions(+)
 create mode 100644 basic-commands.md
```

#### Writing good commit messages

| Bad | Good |
|-----|------|
| `update` | `Add git clone example to basic-commands.md` |
| `fix` | `Fix typo in git commit section` |
| `changes` | `Add cheat sheet table at end of guide` |

Rules of thumb:
- Start with a verb (Add, Fix, Update, Remove).
- Describe **what** changed and **why**, briefly.
- Keep the first line under about 50 characters.

---

## 4. Viewing History and Differences

### `git log`: see commit history

```bash
git log
```

```
commit 3f2a9c1e8b... (HEAD -> main)
Author: Your Name <your.email@example.com>
Date:   Thu Nov 12 22:00:00 2026

    Add basic Git commands guide
```

A shorter, more readable version:

```bash
git log --oneline
git log --oneline --graph --all
```

```
3f2a9c1 Add basic Git commands guide
a81b7d4 Create README with team info
```

### `git diff`: see what changed

```bash
# Changes not yet staged
git diff

# Changes that are staged (ready to commit)
git diff --staged
```

Example output:

```diff
-Project Status: In Progress
+Project Status: Completed
```

Lines starting with `-` were removed; lines starting with `+` were added.

### `git show`: inspect a single commit

```bash
git show 3f2a9c1
```

---

## 5. Working with Remote Repositories

A **remote** is a copy of your repository hosted online (for example, on GitHub). By convention, the main remote is named `origin`.

### `git remote`: manage remotes

```bash
# List remotes
git remote -v

# Connect a local repo to GitHub
git remote add origin https://github.com/your-team/GitHub-Guide.git
```

### `git push`: upload your commits

Sends your local commits to GitHub.

```bash
# First push of a new branch
git push -u origin feature/basic-commands

# Later pushes on the same branch
git push
```

> The `-u` flag links your local branch to the remote one, so later you can type just `git push` or `git pull`.

### `git fetch`: download without merging

Gets the latest changes from GitHub but does **not** change your files.

```bash
git fetch origin
```

### `git pull`: download and merge

Fetches the latest changes **and** merges them into your current branch.

```bash
git pull origin main
```

> **Good habit:** run `git pull` before you start working, so you begin with the latest version.

---

## 6. Undoing Changes

### Unstage a file (undo `git add`)

```bash
git restore --staged basic-commands.md
```

### Discard changes in a file (careful: this cannot be undone)

```bash
git restore basic-commands.md
```

### Fix the last commit message (before pushing)

```bash
git commit --amend -m "Add basic Git commands guide with examples"
```

### Undo a commit safely (after pushing)

`git revert` creates a **new** commit that cancels an old one, keeping history intact.

```bash
git revert 3f2a9c1
```

> Avoid `git reset --hard` on shared branches. It rewrites history and can cause trouble for your teammates.

---

## 7. Quick Cheat Sheet

| Command | What it does |
|---------|--------------|
| `git config --global user.name "Name"` | Set your name |
| `git init` | Create a new repository |
| `git clone <url>` | Copy a repository from GitHub |
| `git status` | Show current state of files |
| `git add <file>` | Stage a file |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save staged changes |
| `git log --oneline` | Show compact history |
| `git diff` | Show unstaged changes |
| `git remote -v` | List remotes |
| `git push` | Upload commits to GitHub |
| `git fetch` | Download changes without merging |
| `git pull` | Download and merge changes |
| `git restore --staged <file>` | Unstage a file |
| `git revert <commit>` | Safely undo a commit |

---

