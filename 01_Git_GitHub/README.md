# 🐙 Git & GitHub Notes & Cheatsheets

Comprehensive handwritten notes, illustrated diagrams, and quick-reference cheat sheets covering version control with **Git** and cloud collaboration with **GitHub** (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **Git & GitHub Handwritten Notes (English)** | English | PDF (6 Pages) | [`Git_Github_Handwritten_Notes_English.pdf`](./Git_Github_Handwritten_Notes_English.pdf) |
| **Git & GitHub Handwritten Notes (Hinglish)** | Hinglish | PDF (5 Pages) | [`Git_Github_Handwritten_Notes_Hinglish.pdf`](./Git_Github_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`Git_Github_Notes_English.html`](./Git_Github_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`Git_Github_Notes_Hinglish.html`](./Git_Github_Notes_Hinglish.html) |

---

## 📚 Topics & Key Concepts

### 1. What is Git vs GitHub?
- **Git:** A free, open-source **Distributed Version Control System (VCS)** that tracks changes in source code locally across development history.
- **GitHub:** A cloud-based hosting service and collaboration platform for Git repositories, enabling team collaboration, pull requests, issue tracking, and CI/CD.

```
       [ Local Machine ]                         [ Cloud Platform ]
+------------------------------+             +------------------------+
| Working Dir -> Staging -> Git|  git push   |        GitHub          |
| (Local Code)   (git add) (commit) ---------> (Remote Repository)    |
|                              |  <--------- |                        |
+------------------------------+   git pull  +------------------------+
```

---

### 2. The 3 Stages of Git
1. **Working Directory:** Where you actively write and modify your code files.
2. **Staging Area (Index):** Preparing selected changes to be snapshotted (`git add`).
3. **Local Repository:** Permanent history containing saved commit snapshots (`git commit`).

---

### 3. Essential Commands Cheat Sheet

| Command | Purpose | Example |
| :--- | :--- | :--- |
| `git init` | Initialize a new local Git repository | `git init -b main` |
| `git clone <url>` | Download an existing repository from GitHub | `git clone https://github.com/user/repo.git` |
| `git status` | Check current branch and staged / untracked files | `git status` |
| `git add <file>` | Stage file(s) for the next commit | `git add .` (stages all changes) |
| `git commit -m "<msg>"` | Create a permanent commit snapshot with a message | `git commit -m "feat: add login feature"` |
| `git log` | View chronological commit history | `git log --oneline --graph` |
| `git remote add origin <url>` | Link local repository to remote GitHub repo | `git remote add origin https://github.com/...` |
| `git push -u origin <branch>` | Upload local commits to remote GitHub branch | `git push -u origin main` |
| `git pull origin <branch>` | Fetch and merge remote updates into local branch | `git pull origin main` |

---

### 4. Branching & Merging Workflow

```
main:     ●-------●-------●-----------● (Merged)
                   \                 /
feature:            ●-------●-------●
```

- **Create & Switch Branch:**
  ```bash
  git checkout -b feature-login   # Old syntax
  git switch -c feature-login     # Modern syntax
  ```
- **Merge into Main:**
  ```bash
  git checkout main
  git merge feature-login
  ```
- **Delete Branch after merge:**
  ```bash
  git branch -d feature-login
  ```

---

### 5. Pull Requests (PR) & Open Source Contributions
1. **Fork:** Create your personal copy of someone else's repository on GitHub.
2. **Clone:** Clone your fork to your local machine.
3. **Branch:** Create a new feature branch for your changes.
4. **Commit & Push:** Commit your improvements and push to your fork.
5. **Pull Request (PR):** Open a PR from your branch to the original repository's `main` branch for review and merging.

> [!TIP]
> Always verify `git status` before committing, and keep your `.gitignore` updated to prevent committing system files or sensitive API keys.
