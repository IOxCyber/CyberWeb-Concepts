## ⚙️ Essential Git Commands (Local Repository Workflow)

- The local workflow involves three main stages: the **Working Directory** (your files), the **Staging Area** (files marked for the next commit), and the **Local Repository** (your saved history).

| Category | Command | Syntax Example | Usage |
| :--- | :--- | :--- | :--- |
| **Setup & Init** | `git init` | `git init` | Initializes a **new, empty Git repository** in the current directory. |
| | `git clone` | `git clone <repository_url>` | Creates a **local copy** of an existing remote repository (like from GitHub). |
| **Staging** | `git status` | `git status` | Shows the current state of the repository: which files are modified, staged, or untracked. |
| | `git add` | `git add filename.txt` <br> `git add .` | Adds a specific file or **all modified/new files** (`.`) to the **Staging Area**. |
| **Committing** | `git commit` | `git commit -m "Initial project setup"` | Records the staged changes as a new **commit** (snapshot) in the local repository history. |
| | `git log` | `git log` | Displays the **commit history**. |
| **Undoing** | `git restore` | `git restore filename.txt` | Discards changes in the working directory (unstaged changes) for a specific file. |
| | `git reset` | `git reset HEAD~1` | **Unstages** the last commit while keeping the changes in your files. (Removes the last commit from history). |

-----

