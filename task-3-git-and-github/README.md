# Git & GitHub: Complete Version Control Guide for FinTech Analysts

> **Module 3 Reference & Workflow Guide**  
> *Targeted for Bluestock Fintech Onboarding & Financial Analytics*

---

## 1. What is Version Control & Why Does It Matter?
**Version Control Systems (VCS)** record changes to files over time so that you can recall specific versions, audit who modified what, rollback broken code, and collaborate seamlessly across engineering and data teams.

For Data Analysts at Bluestock, Git version control guarantees:
* **Analytical Reproducibility:** Pinpoint the exact SQL query, Python script, and data transformation pipeline that generated an executive report.
* **Collaboration & Code Reviews:** Data models and KPI definitions are verified by peer reviewers via Pull Requests before hitting production data warehouses.
* **Zero Work Loss:** Local and remote distributed history safeguards your scripts, notebooks, and models against hardware failures.

---

## 2. Git Architecture: The Three Local Zones & Remote

Git manages code across four distinct lifecycle states:

```
+───────────────────────────────────────────────────────────────────────────────────+
|                               GIT WORKFLOW LIFECYCLE                              |
+───────────────────────────────────────────────────────────────────────────────────+

  [ Working Directory ] ───( git add )───> [ Staging Area (Index) ]
                                                   │
                                            ( git commit )
                                                   │
                                                   ▼
  [ Remote GitHub Repo ] <──( git push )─── [ Local Repository (.git) ]
                         ───( git pull )───>
```

1. **Working Directory:** The local folder where you actively create, modify, and delete files.
2. **Staging Area (Index):** The drafting zone where changes are selected and queued before finalizing a commit (`git add`).
3. **Local Repository (`.git`):** The local database storing compressed file snapshots, metadata, and the complete historical timeline (`git commit`).
4. **Remote Repository (GitHub):** The centralized cloud host enabling team synchronization, code review, and automated CI/CD deployments (`git push` / `git pull`).

---

## 3. Core Git Concepts Explained

### A. Repository (Repo)
A **Repository** is the digital container that houses your project files, directory tree, and complete version history tracked by Git.

### B. Clone
Creates an exact local copy of an existing remote repository on your machine:
```bash
git clone https://github.com/<username>/bluestock-fintech-analytics.git
```

### C. Commit
A **Commit** is an immutable, cryptographically hashed snapshot (SHA-1/SHA-256) of staged changes at a specific point in time. It includes an author name, timestamp, and descriptive message:
```bash
git commit -m "feat(task-2): add market data transformation pipeline to CSV"
```

### D. Push
Uploads local commits from your machine to the remote repository on GitHub:
```bash
git push origin main
```

### E. Pull & Fetch
* `git fetch`: Downloads new commits, branches, and tags from GitHub without modifying your local working files.
* `git pull`: Executes `git fetch` and immediately merges the changes into your current active local branch:
```bash
git pull origin main
```

### F. Branches
A **Branch** is a lightweight, moveable pointer to a specific commit. Branches isolate new feature development, bug fixes, or analytical experiments without corrupting the stable `main` production codebase.
```bash
# Create and switch to a new feature branch
git checkout -b feature/options-screener-analysis
# Modern Git alternative:
git switch -c feature/options-screener-analysis
```

### G. Pull Requests (PR) & Code Reviews
A **Pull Request (PR)** is a GitHub collaborative workflow where a developer requests that changes made on a feature branch be reviewed, tested, and merged into the base branch (`main`).
* Reviewers can leave inline comments, request revisions, and verify that automated CI/CD tests pass before approving the merge.

---

## 4. Git Best Practices: Conventional Commits
Professional teams enforce semantic commit messages. Use the standard **Conventional Commits** specification:

* `feat:` A new feature or analytical capability (e.g., `feat(api): add CoinGecko price extraction script`)
* `fix:` A bug fix (e.g., `fix(parser): handle null values in market cap calculation`)
* `docs:` Documentation updates (e.g., `docs(readme): add setup and execution instructions`)
* `refactor:` Code restructuring without changing functional behavior
* `test:` Adding or updating unit tests

---

## 5. Step-by-Step Guide: Publishing This Assignment to GitHub

Follow these exact steps in your terminal to publish your local repository to your personal GitHub account:

### Step 1: Create a New Empty Repository on GitHub
1. Log in to [GitHub](https://github.com).
2. Click the **`+`** icon in the top-right corner and select **New repository**.
3. Repository name: `bluestock-fintech-data-analyst`
4. Description: `Bluestock FinTech Data Analyst Onboarding & Domain Prerequisite Assignments`
5. Set visibility to **Public** (or Private if preferred).
6. **Do NOT** initialize with a README, `.gitignore`, or license (we already created them locally).
7. Click **Create repository**.

### Step 2: Set the Default Branch to `main`
In PowerShell or your terminal inside this workspace directory:
```bash
git branch -M main
```

### Step 3: Link Your Local Repo to the Remote GitHub URL
Copy your GitHub repo URL and run:
```bash
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/bluestock-fintech-data-analyst.git
```
*(Replace `<YOUR_GITHUB_USERNAME>` with your actual GitHub username).*

### Step 4: Verify the Remote Configuration
```bash
git remote -v
```
*(Should output `origin  https://github.com/... (fetch)` and `(push)`).*

### Step 5: Push Your Local Commits to GitHub
```bash
git push -u origin main
```
*The `-u` (or `--set-upstream`) flag links your local `main` branch directly to `origin/main` on GitHub, enabling simple future `git push` and `git pull` commands.*

---

## 6. How to Submit Updates via Branches & Pull Requests

1. **Create a new branch for changes:**
   ```bash
   git switch -c update/bse-ratio-metrics
   ```
2. **Make your edits and commit:**
   ```bash
   git add .
   git commit -m "docs(task-1): update BSE Ltd FY24 net profit margin analysis"
   ```
3. **Push the branch to GitHub:**
   ```bash
   git push -u origin update/bse-ratio-metrics
   ```
4. **Open a Pull Request on GitHub:**
   * Navigate to your repo on GitHub.
   * Click **Compare & pull request**.
   * Fill out the title and description, then click **Create pull request**.
   * Merge the PR into `main` after review.
