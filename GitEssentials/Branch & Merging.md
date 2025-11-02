## 🌳 Branching and Merging Commands

Branching allows for parallel development, which is critical for team collaboration.

| Category | Command | Syntax Example | Usage |
| :--- | :--- | :--- | :--- |
| **Branching** | `git branch` | `git branch new-feature` | Creates a new branch named `new-feature`. |
| | `git branch -a` | `git branch -a` | Lists all local and remote branches. |
| | `git switch` | `git switch new-feature` | **Switches** the working directory to the specified branch (preferred over `checkout` for switching). |
| **Merging** | `git merge` | `git merge new-feature` | **Combines** the changes from `new-feature` branch into the current branch (e.g., `main`). |
| | `git branch -d` | `git branch -d new-feature` | **Deletes** the local branch (only works if merged). Use `-D` to force delete. |

-----
