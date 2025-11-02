## 🔍 Essential Git Commands for Security Auditing

The following Git commands are crucial for investigating security incidents, performing code reviews for vulnerabilities, and auditing the history of a repository:

### 1. `git log`
This is your primary tool for examining the project's history.

* **Audit a specific file:**
    * `git log <filename>`
    * *Security Context:* View all commits that modified a sensitive file (e.g., a configuration file with credentials, or a core authentication module) to trace all changes.
* **Show a full patch/diff for each commit:**
    * `git log -p`
    * *Security Context:* See the exact code changes introduced by each commit. This is vital for reviewing patches for malicious code, backdoors, or fixing a vulnerability correctly.
* **Search for keywords in commit messages or code changes:**
    * `git log --grep="password"`
    * `git log -S "API_KEY"` (the "pickaxe" option)
    * *Security Context:* Quickly search the entire history for accidentally committed secrets (like passwords, tokens, API keys) or suspicious phrases.

### 2. `git blame`
Despite its name, this command is for accountability, not just "blaming."

* **Check who last modified a line of code:**
    * `git blame <filename>`
    * *Security Context:* If you find a vulnerable line of code (e.g., a SQL injection point or an insecure function call), `git blame` instantly tells you **which commit** introduced it and **who the author was**. You can then use `git show` on the commit to get more details.

### 3. `git diff`
This command compares different versions of your code, which is fundamental for security review.

* **Compare two branches/commits/tags:**
    * `git diff <commit1> <commit2>` or `git diff <branch1> <branch2>`
    * *Security Context:* Review the *entire* change set before a deployment or merge to identify potential security flaws that might have been missed in a standard code review.

### 4. `git reset` / `git revert`
These commands are essential for cleaning up and fixing issues in the history.

* **`git revert <commit-hash>`:** **(Safest for public history)** Creates a *new* commit that undoes the changes of a previous commit.
    * *Security Context:* Safely undoing a malicious or vulnerability-introducing commit *without* rewriting history, which is important for maintaining an auditable log.
* **`git reset --hard <commit-hash>`:** **(Use with extreme caution, usually only locally)** Rewrites the commit history to a specific point.
    * *Security Context:* Only use this in controlled scenarios (e.g., a local branch) or if you **must** permanently remove an exposed secret from the repository's history (though other tools are better for history rewriting).

### 5. `git show`
Used to display the metadata and content changes of a single object (commit, tag, or file).

* **Examine a specific commit:**
    * `git show <commit-hash>`
    * *Security Context:* After finding a suspicious commit hash via `git log` or `git blame`, use `git show` to get a detailed view of the commit message, author, timestamp, and the exact files/lines that were changed.

---

## 🛠️ Security Workflow Summary

Your typical security workflow using these commands might look like this:

1.  A security scan flags a vulnerability in file **`user_auth.py`**.
2.  You run `git blame user_auth.py` to identify the **commit hash** that introduced the vulnerable code.
3.  You run `git show <commit-hash>` to review the complete context of the change (commit message, author, full diff).
4.  You run `git log --author="SuspiciousUser"` or `git log --before="YYYY-MM-DD"` to check for other malicious changes made by the same author or during a specific timeframe.
5.  You use `git revert <commit-hash>` to quickly undo the change while you develop a proper fix.
