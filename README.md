Here’s a **complete Git & GitHub tutorial** with an in-depth explanation of each command keyword, ideal for beginners and intermediate users.

---

## 🧠 What Is Git & GitHub?

* **Git**: A **distributed version control system** that tracks changes in code.
* **GitHub**: A **cloud-based hosting service** for Git repositories, allowing collaboration.

---

## 📦 Git Installation

```bash
git --version
```

> ✅ Checks if Git is installed.

To install Git: [https://git-scm.com/downloads](https://git-scm.com/downloads)

---

## 🔧 Basic Git Configuration

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

> ✅ Sets your Git identity globally.

```bash
git config --list
```

> ✅ Shows all Git configurations.

---

## 📁 Creating a New Repository

```bash
git init
```

> ✅ Initializes a new Git repository in the current directory.

---

## 🧲 Cloning a Remote Repository

```bash
git clone https://github.com/username/repo-name.git
```

> ✅ Copies an entire remote repository to your local machine.

---

## 📋 Checking Repository Status

```bash
git status
```

> ✅ Shows changes staged for commit, files not being tracked, and files that have changed.

---

## 🧮 Staging Changes

```bash
git add file.txt
```

> ✅ Adds specific file(s) to the staging area.

```bash
git add .
```

> ✅ Adds all changed files in the directory to staging.

---

## 💾 Committing Changes

```bash
git commit -m "Meaningful message"
```

> ✅ Saves the staged changes with a commit message.

```bash
git commit -am "Message"
```

> ✅ Adds and commits changes in tracked files (skips `git add` for tracked files).

---

## 📜 Viewing Commit History

```bash
git log
```

> ✅ Shows commit history with hash, author, date, and message.

```bash
git log --oneline
```

> ✅ Condensed view of commits.

---

## 🔄 Branching

```bash
git branch
```

> ✅ Lists all local branches.

```bash
git branch new-feature
```

> ✅ Creates a new branch.

```bash
git checkout new-feature
```

> ✅ Switches to the new branch.

```bash
git checkout -b new-feature
```

> ✅ Creates and switches to a new branch (shortcut).

---

## 🔀 Merging Branches

```bash
git merge branch-name
```

> ✅ Merges another branch into the current one.

---

## 🔁 Pulling Changes

```bash
git pull origin main
```

> ✅ Fetches and merges changes from the remote repository.

---

## 📤 Pushing Changes

```bash
git push origin main
```

> ✅ Sends your local commits to the remote repository.

---

## 🧼 Undoing & Resetting

```bash
git reset file.txt
```

> ✅ Unstages a file.

```bash
git checkout -- file.txt
```

> ✅ Discards changes in working directory.

```bash
git reset --hard HEAD
```

> ✅ Resets working directory and staging area to last commit.

---

## 🔍 Comparing Changes

```bash
git diff
```

> ✅ Shows changes not staged.

```bash
git diff --staged
```

> ✅ Shows staged changes.

---

## 🔗 Connecting to GitHub

```bash
git remote add origin https://github.com/username/repo.git
```

> ✅ Links your local repo to a remote one.

```bash
git remote -v
```

> ✅ Verifies the remote repository URL.

---

## 🚀 GitHub Upload Flow (Quick Recap)

1. `git init`
2. `git add .`
3. `git commit -m "Initial commit"`
4. `git branch -M main`
5. `git remote add origin https://github.com/yourname/repo.git`
6. `git push -u origin main`

---

## 🛠️ Advanced Commands (Brief)

```bash
git stash           # Temporarily stores changes
git rebase          # Reapplies commits on top of another base
git cherry-pick     # Applies a specific commit
git tag             # Marks a specific commit (for releases)
git blame file.txt  # Shows who changed what and when
```

---

