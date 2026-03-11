# Learn Git & GitHub by Doing

> **How this works:** You learn by *doing*, not reading. Each task gives you a goal, the commands to run, and what to observe. Don't skip tasks — each one builds on the last.

---

##  Your Learning Journey

```
SOLO SKILLS                    COLLABORATION SKILLS
─────────────                  ────────────────────
Task 1: Install & Setup        Task 6:  Fork a Repository
Task 2: Your First Repo        Task 7:  Clone & Explore
Task 3: Commit Your Work       Task 8:  Branches for Features
Task 4: Time Travel            Task 9:  Pull Requests
Task 5: Push to GitHub         Task 10: Open Source Contribution
```

---

## 🔧 PART 1 — Solo Skills (Foundation)

---

### ✅ Task 1 — Install Git & Introduce Yourself

**Goal:** Get Git ready and tell it who you are.

**Why this matters:** Every commit you make is signed with your name and email. Collaborators will see this.

**Steps:**

1. Download and install Git from [https://git-scm.com](https://git-scm.com)
2. Open your terminal (Mac/Linux) or Git Bash (Windows)
3. Run these commands (replace with your actual name and email):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

4. Confirm it worked:

```bash
git config --list
```

**✔️ You're done when:** You see your name and email printed in the output.

**🔍 Observe:** Notice `--global` means this applies to *all* your projects, not just one.

---

### ✅ Task 2 — Create Your First Repository

**Goal:** Turn a folder into a Git repository.

**Why this matters:** A repository (repo) is where Git tracks all changes to your project.

**Steps:**

1. Create a new folder and enter it:

```bash
mkdir my-first-repo
cd my-first-repo
```

2. Initialize Git:

```bash
git init
```

3. Check what happened:

```bash
ls -la
```

**✔️ You're done when:** You see a hidden `.git` folder listed.

**🔍 Observe:** That `.git` folder is where Git stores everything. Never delete it manually.

---

### ✅ Task 3 — Make Your First Commit

**Goal:** Create a file, track it, and save a snapshot of it.

**Why this matters:** Commits are the core of Git. They are save points in your project's history.

**Steps:**

1. Create a file:

```bash
echo "# My First Project" > README.md
```

2. Check Git's current status:

```bash
git status
```

3. Stage the file (tell Git "include this in the next save"):

```bash
git add README.md
```

4. Run `git status` again and notice the difference.

5. Commit the file (create the actual save point):

```bash
git commit -m "Add README file"
```

6. View your commit history:

```bash
git log --oneline
```

**✔️ You're done when:** You see your commit with the message "Add README file".

**🔍 Observe:** Notice the short hash (like `a3f2c1b`) next to your commit. That's its unique ID.

---

### ✅ Task 4 — Make Changes & Travel Through Time

**Goal:** Make multiple commits, then explore your history.

**Why this matters:** Git lets you undo mistakes by going back to any previous commit.

**Steps:**

1. Add more content to your README:

```bash
echo "This project is for learning Git." >> README.md
echo "Learning is fun!" >> README.md
```

2. Stage and commit:

```bash
git add README.md
git commit -m "Add description to README"
```

3. View the full log:

```bash
git log
```

4. Copy the hash of your *first* commit (the long string of letters/numbers)

5. Look at what your project looked like at that commit:

```bash
git show <paste-the-hash-here>
```

6. Return to the present (you're already there, but good to know):

```bash
git checkout main
```

**✔️ You're done when:** You've viewed the diff output from `git show`.

**🔍 Observe:** Lines starting with `+` were added, lines with `-` were removed.

---

### ✅ Task 5 — Push Your Repo to GitHub

**Goal:** Upload your local repository to GitHub so others can see it.

**Why this matters:** GitHub is where collaboration happens. This is step one.

**Before starting:** Create a free account at [https://github.com](https://github.com)

**Steps:**

1. On GitHub, click **"New"** to create a new repository
2. Name it `my-first-repo`, keep it **Public**, and click **Create**
3. GitHub will show you commands — use these:

```bash
git remote add origin https://github.com/YOUR-USERNAME/my-first-repo.git
git branch -M main
git push -u origin main
```

4. Refresh your GitHub page.

**✔️ You're done when:** You can see your README.md displayed on GitHub.

**🔍 Observe:** `origin` is just a nickname for your GitHub URL. You could name it anything, but `origin` is the convention.

---

## 🤝 PART 2 — Collaboration Skills (The Real Goal)

---

### ✅ Task 6 — Fork Someone Else's Repository

**Goal:** Copy another person's repo to your own GitHub account.

**Why this matters:** Forking is how you contribute to projects you don't own. It's the foundation of open-source collaboration.

**Steps:**

1. Go to this practice repository:
   `https://github.com/firstcontributions/first-contributions`

2. Click the **"Fork"** button (top right of the page)

3. GitHub creates a copy under your account: `YOUR-USERNAME/first-contributions`

4. Notice that your fork says *"forked from firstcontributions/first-contributions"*

**✔️ You're done when:** You have a forked copy in your GitHub account.

**🔍 Observe:** Your fork is completely independent. Changes you make won't affect the original — yet.

---

### ✅ Task 7 — Clone & Explore a Repository

**Goal:** Download a GitHub repository to your computer.

**Why this matters:** You need a local copy to actually edit files and run code.

**Steps:**

1. Go to *your fork* of the repository (not the original)

2. Click the green **"Code"** button → Copy the HTTPS URL

3. Clone it:

```bash
git clone https://github.com/YOUR-USERNAME/first-contributions.git
```

4. Enter the folder:

```bash
cd first-contributions
```

5. Explore the repo structure:

```bash
ls
git log --oneline -10
git remote -v
```

**✔️ You're done when:** You can see the remote URLs showing both `origin` (your fork).

**🔍 Observe:** `git remote -v` shows where your code will push to and pull from. There's `origin` (your fork) but not yet a connection to the original.

6. Add a connection to the original repo (called `upstream`):

```bash
git remote add upstream https://github.com/firstcontributions/first-contributions.git
git remote -v
```

**🔍 Observe:** Now you have both `origin` (your fork) and `upstream` (the original). This is the standard setup for collaboration.

---

### ✅ Task 8 — Create a Branch for Your Feature

**Goal:** Create a separate branch so your changes don't affect the main code.

**Why this matters:** Branches let multiple people work simultaneously without stepping on each other. This is the golden rule of collaboration.

**Steps:**

1. Check which branch you're on:

```bash
git branch
```

2. Create a new branch named after what you're doing:

```bash
git checkout -b add-my-name
```

3. Verify you switched:

```bash
git branch
```

4. Open the file `Contributors.md` in any text editor and add your name:

```
- Your Name (https://github.com/YOUR-USERNAME)
```

5. Save the file, then commit your change:

```bash
git add Contributors.md
git commit -m "Add YOUR-NAME to contributors list"
```

6. Push your branch to GitHub:

```bash
git push origin add-my-name
```

**✔️ You're done when:** You see your new branch on GitHub under "branches".

**🔍 Observe:** You pushed to `origin add-my-name`, not `origin main`. Your `main` branch remains untouched. That's the point.

---

### ✅ Task 9 — Open a Pull Request (PR)

**Goal:** Ask the project maintainer to review and merge your changes.

**Why this matters:** Pull Requests are the primary collaboration tool on GitHub. Every professional team uses them.

**Steps:**

1. Go to your fork on GitHub: `https://github.com/YOUR-USERNAME/first-contributions`

2. You'll see a yellow banner: **"Compare & pull request"** — click it

3. Fill out the PR form:
   - **Title:** `Add YOUR-NAME to contributors`
   - **Description:** Explain what you changed and why

4. Look at the "diff" shown — the green lines are what you added

5. Click **"Create pull request"**

**✔️ You're done when:** Your PR appears in the original repo's "Pull Requests" tab.

**🔍 Observe:** The PR is now in the *original* repo, not yours. The maintainer can comment, request changes, or merge it.

---

### ✅ Task 10 — Stay in Sync with the Original Repo

**Goal:** Pull in new changes from the original repo into your fork.

**Why this matters:** On long-running projects, the original repo gets new commits while you're working. You need to sync regularly to avoid conflicts.

**Steps:**

1. Return to your `first-contributions` clone from Task 7

2. Fetch the latest changes from the original repo:

```bash
git fetch upstream
```

3. Switch to your main branch:

```bash
git checkout main
```

4. Merge upstream's changes into your local main:

```bash
git merge upstream/main
```

5. Push your now-updated main back to your fork:

```bash
git push origin main
```

**✔️ You're done when:** Your fork's `main` branch is up to date with the original.

**🔍 Observe:** This is the sync loop every contributor does regularly: fetch → merge → push. Doing this often prevents large, messy conflicts.

---

## 📋 Quick Reference Card

| Command | What it does |
|---|---|
| `git init` | Create a new repo in current folder |
| `git clone <url>` | Download a repo from GitHub |
| `git status` | See what's changed |
| `git add <file>` | Stage a file for commit |
| `git add .` | Stage ALL changed files |
| `git commit -m "message"` | Save a snapshot |
| `git log --oneline` | View commit history |
| `git branch` | List branches |
| `git checkout -b <name>` | Create & switch to new branch |
| `git checkout <name>` | Switch to existing branch |
| `git merge <branch>` | Merge a branch into current |
| `git push origin <branch>` | Upload branch to GitHub |
| `git pull` | Download & merge latest changes |
| `git fetch upstream` | Download changes from original repo |
| `git remote -v` | View remote connections |

---

## 🧠 Key Concepts Glossary

| Term | Plain English |
|---|---|
| **Repository (Repo)** | A folder that Git is tracking |
| **Commit** | A saved snapshot of your project |
| **Branch** | A parallel version of the project |
| **Merge** | Combining two branches together |
| **Fork** | Your personal copy of someone else's repo |
| **Clone** | Downloading a repo to your computer |
| **Pull Request (PR)** | A request to merge your changes into a project |
| **Upstream** | The original repo you forked from |
| **Origin** | Your fork on GitHub |
| **Merge Conflict** | Two branches changed the same line differently |


---

## 🚀 What's Next?

Once you've completed all tasks, explore these topics:

- **`git stash`** — temporarily shelve your work
- **`git rebase`** — cleaner alternative to merge

---

*Happy coding! The best way to get comfortable with Git is to use it every day — even for personal projects. Start tracking everything.* 🌱
