## 🌐 Remote Repository Commands

These commands are used to synchronize your local repository with a remote hosting service like GitHub, GitLab, or Bitbucket.

| Category | Command | Syntax Example | Usage |
| :--- | :--- | :--- | :--- |
| **Connecting** | `git remote add` | `git remote add origin <url>` | **Links** a local repository to a remote server (usually named `origin`). |
| **Updating Local** | `git fetch` | `git fetch origin` | Downloads the latest changes (commits, branches) from the remote but **DOES NOT merge** them into your local branch. |
| | `git pull` | `git pull origin main` | **Fetches** the changes from the remote **AND immediately merges** them into your current local branch. |
| **Updating Remote** | `git push` | `git push origin main` | **Uploads** your local commits to the remote repository's branch. |

-----

### 💡 Quick Tip: Git Flow

The basic daily workflow for a developer is:

1.  **Start:** `git pull` (Get latest changes from the team).
2.  **Work:** Modify files in your working directory.
3.  **Stage:** `git add .` (Mark files to be included).
4.  **Commit:** `git commit -m "Fixed bug X"` (Save the snapshot).
5.  **Share:** `git push` (Upload the commit to the remote repository).
