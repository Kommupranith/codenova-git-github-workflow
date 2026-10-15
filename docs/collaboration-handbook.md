\# Git and GitHub Collaboration Handbook



\## Project Overview

This project demonstrates Git version control

and GitHub collaboration workflows for the

CodeNova Task 1.



\## Tools Used

\- Git

\- GitHub

\- Markdown



\## Collaboration Workflow

1\. Create a feature branch.

2\. Make changes to project files.

3\. Commit changes using meaningful messages.

4\. Push the branch to GitHub.

5\. Open a pull request.

6\. Review and merge the pull request.

7\. Practice resolving merge conflicts.



\## Best Practices

\- Write clear commit messages.

\- Use feature branches for changes.

\- Review code before merging.

\- Keep documentation updated.



\## Merge Conflict Practice



\### Scenario

A merge conflict was intentionally created by changing

the same line in `conflict-practice.txt` on the `main`

branch and `feature/merge-conflict-practice` branch.



\### Resolution

1\. Merged `main` into the feature branch.

2\. Inspected the conflict markers.

3\. Resolved the conflict by preserving both updates.

4\. Staged the resolved file using `git add`.

5\. Committed the resolution using a conventional commit message.

6\. Pushed the feature branch to GitHub.

7\. Opened and merged a Pull Request.

8\. Updated local `main` and deleted the local feature branch.



\### Verification

Ran `git status` and confirmed that the working tree was clean and the local `main` branch was up to date

with `origin/main`.

