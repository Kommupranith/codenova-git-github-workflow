# CodeNova DevOps Internship — Git and GitHub Workflow

## Project Overview

This repository demonstrates a practical Git and GitHub collaboration workflow developed for the CodeNova DevOps Internship, Batch 01.

The project focuses on version control, feature branching, meaningful commits, Pull Requests, code review practices, merge-conflict resolution, and repository maintenance.

**Repository:** [codenova-git-github-workflow](https://github.com/Kommupranith/codenova-git-github-workflow)

## Objectives

- Understand Git fundamentals and remote repositories.
- Organize work using feature branches.
- Use GitHub Pull Requests to propose and review changes.
- Follow Conventional Commits for clear project history.
- Simulate, resolve, and document a realistic merge conflict.
- Maintain a clean, secure, and well-documented repository.

## Technology Stack

- **Git:** Distributed version control.
- **GitHub:** Remote repository hosting and collaboration.
- **Git Bash:** Command-line Git environment on Windows.
- **Markdown:** Project documentation.

No paid software or hosting is required for this project.

## Repository Structure

```text
codenova-git-github-workflow/
├── .gitignore
├── LICENSE
├── README.md
├── conflict-practice.txt
└── docs/
    └── collaboration-handbook.md
```

- `README.md` — Project overview and Git collaboration handbook.
- `.gitignore` — Lists temporary files, logs, Python cache files, environment files, and editor settings that Git should ignore.
- `LICENSE` — Project license information.
- `conflict-practice.txt` — File used to practise a merge conflict.
- `docs/collaboration-handbook.md` — Additional documentation of the collaboration workflow and conflict-resolution exercise.

## Prerequisites

Install or create the following:

1. A GitHub account.
2. Git installed on your computer.
3. Git Bash or another terminal.
4. A text editor such as Notepad or Visual Studio Code.

Verify your Git installation:

```bash
git --version
```

Set your commit identity if you have not already configured it:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Use your own name and an email address associated with your GitHub account. These commands configure the author information recorded in your commits.

## Getting Started

Clone the repository and enter its directory:

```bash
git clone https://github.com/Kommupranith/codenova-git-github-workflow.git
cd codenova-git-github-workflow
```

Check the current branch and working tree:

```bash
git status
git branch
```

Download the latest changes from the remote `main` branch:

```bash
git switch main
git pull origin main
```

## Git Branching Strategy

The `main` branch contains the primary project history. Create a separate feature branch for each focused change instead of doing all development directly on `main`.

Branch naming convention:

```text
feature/<short-description>
```

Example:

```bash
git switch main
git pull origin main
git switch -c feature/update-documentation
```

Make the required changes in the new branch. Check the files before staging them:

```bash
git status
git diff
```

Stage and commit a specific file:

```bash
git add README.md
git commit -m "docs: improve project documentation"
```

Push the feature branch to GitHub:

```bash
git push -u origin feature/update-documentation
```

Replace the example branch name and file path with the actual ones for your change.

## Conventional Commits

Commit messages should communicate the purpose of a change clearly.

Use this format:

```text
<type>: <short description>
```

Common commit types:

| Type | Purpose | Example |
|---|---|---|
| `feat:` | Add a feature | `feat: add repository guide` |
| `fix:` | Correct a problem | `fix: correct setup instructions` |
| `docs:` | Update documentation | `docs: document merge conflict resolution` |
| `refactor:` | Restructure without changing intended behavior | `refactor: simplify folder layout` |
| `test:` | Add or update tests | `test: add workflow checks` |
| `chore:` | Maintenance tasks | `chore: update ignore rules` |

Keep commits focused. Avoid vague messages such as `changes`, `update`, or `final commit`.

## Pull Request Workflow

A Pull Request (PR) proposes changes from a feature branch into the base branch. It provides a place to discuss the changes before merging.

1. Create a feature branch.
2. Make a focused change.
3. Inspect the changes using `git diff`.
4. Stage and commit the changes.
5. Push the branch to GitHub.
6. Open a Pull Request with `main` as the base branch.
7. Explain what changed and why in the PR description.
8. Review the **Files changed** tab for errors or unintended changes.
9. Ask a peer to review the PR when possible.
10. Address review comments and push any required updates.
11. Merge the PR when it is ready.
12. Delete the merged feature branch when it is no longer needed.

### Peer Review Checklist

A reviewer should check:

- Does the change match the stated purpose?
- Are file names and folder locations appropriate?
- Are the instructions clear and accurate?
- Are commit messages meaningful?
- Are secrets or unnecessary files included?
- Are merge conflicts resolved?
- Is the change ready to merge?

For a solo practice project, a self-review or simulated review can help practise the process, but it should not be described as an actual independent peer approval.

## Merge Conflict Resolution

A merge conflict can occur when two branches make incompatible changes to the same part of a file.

### Example Scenario

The file `conflict-practice.txt` was used to practise a conflict by changing the same line on `main` and `feature/merge-conflict-practice`.

### Typical Conflict Workflow

First, commit your changes on the feature branch. Then merge the updated `main` branch into it:

```bash
git switch feature/merge-conflict-practice
git fetch origin
git merge origin/main
```

If Git reports a conflict, inspect the affected file. A conflict may look like this:

```text
<<<<<<< HEAD
Project status: feature branch update
=======
Project status: main branch update
>>>>>>> origin/main
```

These markers identify the competing versions. They are examples only; the actual labels may differ depending on the merge.

Resolve the conflict by editing the file and choosing the intended final content. For example:

```text
Project status: main and feature updates reviewed
```

Remove all conflict markers, save the file, and stage the resolution:

```bash
git add conflict-practice.txt
```

Commit the resolution:

```bash
git commit -m "docs: resolve project status merge conflict"
```

Push the feature branch:

```bash
git push
```

Then open or update the Pull Request, review the changes, and merge it when appropriate.

**Important:** Do not blindly copy the example conflict markers into a file. Git generates them when a real conflict occurs. Resolve the actual content and preserve the intended changes.

### Verify the Resolution

Inspect the file and search for leftover conflict markers:

```bash
git diff
git grep -n -E '^(<<<<<<< |=======|>>>>>>> )' -- .
```

The search command may return no matches when no tracked file contains those marker patterns. If it finds any, inspect them before proceeding.

Check the final repository status:

```bash
git status
```

A clean working tree should report:

```text
nothing to commit, working tree clean
```

A clean working tree does not by itself prove that every branch is merged or every conflict marker has been removed, so check those separately.

## Useful Git Commands

| Command | Purpose |
|---|---|
| `git status` | Show branch and working-tree status |
| `git log --oneline` | View concise commit history |
| `git branch` | List local branches |
| `git branch -a` | List local and remote-tracking branches |
| `git switch main` | Switch to `main` |
| `git switch -c feature/example` | Create and switch to a branch |
| `git fetch origin` | Fetch remote updates |
| `git pull origin main` | Pull updates from remote `main` |
| `git diff` | Inspect unstaged changes |
| `git add <file>` | Stage a file |
| `git commit -m "docs: describe change"` | Create a commit |
| `git push -u origin feature/example` | Push a branch and set its upstream |
| `git merge main` | Merge `main` into the current branch |
| `git branch -d feature/example` | Delete a merged local branch |

Run `git branch -d` only after switching away from the branch and confirming that the branch has been merged. Remote branch deletion is a separate operation.

## Repository Maintenance

Before finishing a task:

1. Inspect the working tree using `git status`.
2. Review pending changes with `git diff`.
3. Check commit history with `git log --oneline`.
4. Confirm the PR has been merged.
5. Update local `main` using `git pull origin main`.
6. Delete obsolete merged feature branches.
7. Verify that the working tree is clean.

## Security Best Practices

- Never commit passwords, access tokens, API keys, private keys, or real environment secrets.
- Keep sensitive values in environment variables or an approved secrets manager.
- Use `.gitignore` to avoid accidentally tracking local secret and temporary files.
- Remember that `.gitignore` does not remove files that Git already tracks.
- Review changes before committing and before merging a Pull Request.
- Follow the terms of the repository's `LICENSE` and any third-party licenses.

If a secret is accidentally committed, removing it from the latest file is not always sufficient. Revoke or rotate the exposed credential immediately and follow the appropriate repository-history cleanup procedure.

## Troubleshooting

### My working tree has uncommitted changes

Run:

```bash
git status
git diff
```

Decide whether to commit, discard, or temporarily save the changes. Do not discard work you want to keep.

### Git says the branch is not fully merged

Switch to another branch and verify whether the feature branch has been merged. Do not force-delete a branch until you have confirmed that its work is safely preserved.

### My push is rejected

Fetch the latest remote changes and inspect the branch history. Integrate the required updates carefully, resolve any conflicts, and retry the push after verifying the result.

### I see merge-conflict markers

Open each affected file, select or combine the intended changes, remove the markers, save the file, stage the resolution, and commit it.

## Learning Outcomes

This project provided practical experience with:

- Git initialization and repository maintenance.
- Feature branching and commit history.
- Conventional commit messages.
- Pull Requests and review practices.
- Merge-conflict simulation and resolution.
- Markdown documentation.
- Clean branch and working-tree management.
- Basic version-control security practices.

## Project Documentation

- [Collaboration Handbook](docs/collaboration-handbook.md)
- [Conflict Practice File](conflict-practice.txt)

## Internship Submission

This repository was prepared for CodeNova DevOps Internship — Batch 01, Task 1: Git and GitHub Workflow.

**Repository URL:** https://github.com/Kommupranith/codenova-git-github-workflow

Before submission, verify that the repository is public, the README matches the final project, the Pull Requests are closed and merged as intended, and no secrets or unresolved conflict markers remain.

This repository documents a learning exercise. It does not claim that automated testing, Docker, or CI/CD pipelines were implemented as part of Task 1.

---

Maintained as an educational project for the CodeNova DevOps Internship, Batch 01.
