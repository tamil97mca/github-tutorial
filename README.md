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

The `-M` flag in the `git branch -M main` command stands for **"move/rename branch"**, and it **forces** the rename even if the new branch name already exists.
---
### 🔍 Full Explanation:

```bash
git branch -M main
```

* `git branch`: Git command for managing branches.
* `-M`: Stands for "Move" or "rename forcefully".
* `main`: The new name you want to give to the current branch (commonly renaming from `master` to `main`).

---

### 🛠️ Use Case Example

You initialized a repo, and Git created a default `master` branch. To align with modern standards, you rename it:

```bash
git branch -M main
```

This:

* Renames `master` → `main`
* Replaces any existing `main` branch if it already exists (forceful)

If you **don’t want to force** the rename (e.g., only rename if the target doesn’t exist), use `-m` (lowercase):

```bash
git branch -m main
```

---

### ✅ Summary Table

| Flag | Meaning     | Behavior                             |
| ---- | ----------- | ------------------------------------ |
| `-m` | move/rename | Safe rename (fails if `main` exists) |
| `-M` | force move  | Renames even if `main` exists        |

---

### 🔍 `-m` in `git commit -m "Initial commit"` Explained

The `-m` flag in Git stands for **"message"**.

---

### ✅ Full Breakdown:

```bash
git commit -m "Initial commit"
```

* `git commit`: Creates a new commit from the staged changes.
* `-m`: Tells Git that you're **providing the commit message inline**.
* `"Initial commit"`: The **message** describing what this commit does.

---

### 🔁 Without `-m` (Alternative)

If you **omit** `-m`, Git opens the **default text editor** (like Vim or VSCode) to let you write a multi-line commit message manually:

```bash
git commit
```

---

### 📝 Best Practices for `-m`:

* Always use meaningful messages:

  * ✅ `git commit -m "Fix login bug on Safari"`
  * ❌ `git commit -m "stuff"`

---

### ✅ Summary Table

| Flag | Meaning        | Usage Example                       |
| ---- | -------------- | ----------------------------------- |
| `-m` | Inline message | `git commit -m "Add login feature"` |

Would you like me to append this explanation to your PDF?

---

### 🔍 `-u` in `git push -u origin main` Explained

The `-u` flag stands for **`--set-upstream`** — it **links** your local branch with the remote branch.

---

### ✅ Full Breakdown:

```bash
git push -u origin main
```

* `git push`: Uploads your commits to a remote repository.
* `origin`: The remote name (usually GitHub).
* `main`: The branch you're pushing.
* `-u`: Sets the **upstream tracking relationship** between your local `main` and the remote `origin/main`.

---

### 🔁 Why Use `-u`?

After you use `-u` once, future pushes and pulls become simpler:

```bash
# After the first push with -u
git push    # Automatically knows to push to origin/main
git pull    # Automatically pulls from origin/main
```

Without `-u`, you'd always have to do:

```bash
git push origin main
git pull origin main
```

---

### ✅ Summary Table

| Flag | Full Form        | Meaning                             |
| ---- | ---------------- | ----------------------------------- |
| `-u` | `--set-upstream` | Links local branch to remote branch |

---
