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

### ✅ 1. `git stash` – *Temporarily Save Uncommitted Work*

---

#### 🔍 What it Does:

`git stash` temporarily shelves (or stashes) changes you've made to your working directory so you can work on something else, and then come back and re-apply them later.

#### 📘 Syntax:

```bash
git stash         # Save tracked files
git stash -u      # Save tracked + untracked files
git stash pop     # Apply last stash and remove it
git stash apply   # Apply last stash but keep it
git stash list    # View saved stashes
git stash drop    # Delete a stash
```

#### 🌐 Real-World Use Case:

You're working on a feature but are asked to urgently fix a bug in another branch:

```bash
git stash                 # Save your current progress
git checkout bugfix-branch
# fix the bug
git commit -am "Bug fix"
git checkout feature-branch
git stash pop             # Resume where you left off
```

---

### ✅ 2. `git rebase` – *Rewriting History, Making Linear Commit Trees*

#### 🔍 What it Does:

`git rebase` moves or replays commits from one branch onto another. It’s often used to create a **cleaner project history**.

#### 📘 Syntax:

```bash
git checkout feature-branch
git rebase main             # Reapply feature commits on top of main
git rebase -i HEAD~3        # Interactive rebase last 3 commits
```

#### 🌐 Real-World Use Case:

Suppose your `feature-branch` is behind `main` but you want to update it before making a pull request:

```bash
git checkout feature-branch
git rebase main
```

This will replay your changes on top of the latest main, giving a linear history (cleaner than merge commits).

---

### ✅ 3. `git cherry-pick` – *Apply Specific Commits*

#### 🔍 What it Does:

`git cherry-pick` allows you to **pick a single commit from another branch** and apply it to your current branch.

#### 📘 Syntax:

```bash
git cherry-pick <commit-hash>
```

#### 🌐 Real-World Use Case:

You fixed a typo in `main`, but want that same fix in `release` branch:

```bash
git checkout release
git cherry-pick 7a8b9c3       # Commit hash from main
```

Now that specific commit exists in `release` too, without merging full history.

---

### ✅ 4. `git tag` – *Marking Specific Points in History (usually releases)*

#### 🔍 What it Does:

Tags are used to **mark release points**, like `v1.0`, in your repository.

#### 📘 Syntax:

```bash
git tag                      # List tags
git tag v1.0                 # Create lightweight tag
git tag -a v1.1 -m "Release v1.1"   # Annotated tag
git push origin v1.1         # Push specific tag
git push origin --tags       # Push all tags
```

#### 🌐 Real-World Use Case:

You’ve finished a major release:

```bash
git tag -a v1.0 -m "First stable release"
git push origin v1.0
```

Useful for version control and integrating with CI/CD tools (like GitHub Releases or GitHub Actions).

---

### ✅ 5. `git blame file.txt` – *Track Who Changed Each Line*

#### 🔍 What it Does:

`git blame` shows **who last modified each line of a file**, along with the commit hash and timestamp.

#### 📘 Syntax:

```bash
git blame file.txt
git blame -L 10,20 file.txt      # Show blame only for lines 10-20
```

#### 🌐 Real-World Use Case:

You're debugging a bug in `file.txt` and want to see who wrote line 42:

```bash
git blame file.txt
```

You'll see the author, date, and commit ID, helping you track down the reason for that line's change.

---

### 🧠 Summary Table:

| Command           | Use Case                                      | Helpful Flags        |
| ----------------- | --------------------------------------------- | -------------------- |
| `git stash`       | Save uncommitted changes temporarily          | `-u`, `pop`, `apply` |
| `git rebase`      | Clean up or linearize history                 | `-i`, `--onto`       |
| `git cherry-pick` | Apply a specific commit to another branch     |                      |
| `git tag`         | Mark versions/releases                        | `-a`, `-m`, `--tags` |
| `git blame`       | Find who made specific line changes in a file | `-L`                 |

---

Perfect! Let’s walk through a **real-time GitHub scenario** combining:

✅ `git stash`
✅ `git rebase`
✅ `git cherry-pick`
✅ `git tag`
✅ `git blame`

We'll simulate a situation in a **team-based GitHub project**.

---

## 🧪 Project Scenario

Imagine you're working on a project with the following branches:

* `main`: Production-ready code
* `feature/login-ui`: You're developing a new login UI
* `bugfix/header`: Another dev fixed a header bug
* `release`: Branch used for releasing stable versions

You are in the `feature/login-ui` branch when:

---

## 🔧 1. `git stash` – Save Your Ongoing Work

### 💬 Problem:

You're halfway done with your new login UI, but a critical bug in the `main` header needs fixing urgently.

### ✅ What You Do:

```bash
# You're on: feature/login-ui
git stash                     # Save uncommitted changes

git checkout main
git checkout -b hotfix/header-font
# Fix the bug in the header
git commit -am "Fix: Header font size"
git checkout feature/login-ui
git stash pop                 # Resume login UI work
```

🔄 Your **work is safely restored** and the urgent fix was handled.

---

## 🎯 2. `git cherry-pick` – Reuse Specific Fix

### 💬 Problem:

Now your team also wants that header font fix in the `release` branch, without merging the whole branch.

### ✅ What You Do:

```bash
git checkout release
git cherry-pick <commit-hash>
```

> Replace `<commit-hash>` with the commit ID of `"Fix: Header font size"` from `hotfix/header-font`.

✅ Only **that single fix** is applied to `release`, no unrelated changes.

---

## 🧹 3. `git rebase` – Clean Up History

### 💬 Problem:

You finished the login UI work in `feature/login-ui`, but it's behind `main`. You want a clean, linear history for pull request.

### ✅ What You Do:

```bash
git checkout feature/login-ui
git rebase main
```

This replays your feature commits on top of the latest `main`, creating a **clean PR history**.

If conflicts occur, fix them and:

```bash
git add .
git rebase --continue
```

---

## 📌 4. `git tag` – Mark a Release

### 💬 Problem:

You've merged all fixes and features into `main` and now it's ready for release.

### ✅ What You Do:

```bash
git checkout main
git pull
git tag -a v1.0 -m "🎉 Release version 1.0"
git push origin v1.0
```

✅ This helps GitHub and CI/CD systems **track releases**, link changelogs, and rollback easily.

---

## 🕵️ 5. `git blame` – Find Who Broke Something

### 💬 Problem:

Login isn't working. You suspect something went wrong in `auth.service.ts`.

### ✅ What You Do:

```bash
git blame src/services/auth.service.ts
```

Sample output:

```
a1b2c3d4  (Alice 2024-06-02 12:34:56)   return this.login(email, password);
e5f6g7h8  (You   2024-06-05 14:00:02)   console.log("Login called");
```

✅ You now know **who wrote each line**, and when. You find Alice changed a key function — time to ask her why!

---

## 🔁 Summary Workflow Map

```bash
# While on feature branch, get urgent task
git stash

# Switch, fix bug, commit
git checkout -b hotfix/header-font
# Fix
git commit -am "Header fix"

# Cherry-pick fix to release
git checkout release
git cherry-pick <fix-commit>

# Go back, resume work
git checkout feature/login-ui
git stash pop

# After finishing, rebase for clean history
git rebase main

# Tag final release
git checkout main
git tag -a v1.0 -m "Release v1.0"
git push origin v1.0

# If an issue occurs
git blame file.txt
```

---

Great! Let’s simulate the **entire GitHub workflow** on your **local system**, step-by-step. You’ll:

✅ Set up a Git repo
✅ Create branches
✅ Use `stash`, `cherry-pick`, `rebase`, `tag`, and `blame`

---

## 🛠️ STEP 1: Initialize the Repository

```bash
mkdir git-advanced-demo && cd git-advanced-demo
git init
echo "# Git Advanced Demo" > README.md
git add README.md
git commit -m "Initial commit"
git checkout -b main
```

---

## 🧪 STEP 2: Create a Feature Branch (Login UI)

```bash
git checkout -b feature/login-ui
mkdir src && echo "// Login page" > src/login.js
git add .
git commit -m "Start login page"
```

Now, **simulate uncommitted work**:

```bash
echo "// Unfinished login code" >> src/login.js
```

---

## ⚠️ STEP 3: Simulate Emergency Fix → Use `stash`

You’re told to fix a header issue ASAP.

```bash
git stash                  # Save your unfinished work
git checkout -b bugfix/header
echo "// Header bug fixed" > src/header.js
git add .
git commit -m "Fix: Header rendering issue"
```

---

## 🚀 STEP 4: Use `cherry-pick` to Add Fix to Release

```bash
git checkout -b release main
git cherry-pick <BUGFIX_COMMIT_HASH>
```

> 💡 To get the hash:
> `git log --oneline --graph --all`
> Copy the commit for "Fix: Header rendering issue"

---

## 🔁 STEP 5: Resume Work with `stash pop`

```bash
git checkout feature/login-ui
git stash pop
```

✅ Your unfinished work is back!

---

## 📚 STEP 6: Finish Feature & Rebase on Main

```bash
git add .
git commit -m "Finish login UI"
git checkout main
echo "// Main branch updated" > src/utils.js
git add . && git commit -m "Main branch utils update"

git checkout feature/login-ui
git rebase main
```

If conflict happens:

```bash
# Fix file manually
git add .
git rebase --continue
```

---

## 🏷️ STEP 7: Tag the Release

```bash
git checkout main
git merge feature/login-ui
git tag -a v1.0 -m "🎉 Release version 1.0 with Login and Header fix"
git log --oneline --decorate --graph
```

✅ You’ve tagged a release point.

---

## 🔍 STEP 8: Use `git blame`

Let's say something broke in `login.js`. Run:

```bash
git blame src/login.js
```

You’ll see who wrote each line with date, time, and commit hash.

---

## 🎉 All Done! Your Workflow Looked Like:

```
main ──────┬──────────────┬─── Merged to main
           │              │
     feature/login-ui   bugfix/header ──── cherry-pick ──► release
```

---