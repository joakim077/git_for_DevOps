
# GIT: Version Control System

### Features
- Backup and restoration
- Collaboration
- Branching and merging
- Tracking changes

---

## Install and check Version

```bash
sudo apt-get install git     # Install git
git --version                # Check version
```

---

## Config

```bash
git config --global user.name "<user_name>"
git config --global user.email "<email>"
git config --list
```

---

## Commands

```bash
git init                          # Initialize git repo (Create .git directory)
git diff                          # Show difference
git add .                         # Stage changes
git status                        # See status
git commit -m "commit message"    # Commit changes
```

---

## See content of older Versions

1. `git show <commit-id>:<filename>`: See file of that version
2. `git checkout <commit-id> -- <filename>`: Make file content of mentioned version
3. `git checkout <latest-commit> -- <filename>`: Revert back to latest version

---

## Restore to Last Version

1. `git restore .` : Restore to last commit version (files content will be as of last commit)
2. `git restore --staged <filename>`: Unstage file (file content preserved)
3. `git restore --worktree <filename>`: Discard unstaged changes, keep staged content
4. **Reset:**
    - `git reset --soft HEAD^`: Go to previous version but keep changes in files
    - `git reset --hard HEAD^`: Go to previous version and discard changes

---

## GIT Log Options

```bash
git log                                      # See logs, commit ID, commit messages
git log -p -2                                # Last two commits with diff
git log --stat                               # Summary of changes
git log --pretty=oneline
git log --pretty=format:"%h-%an,%ar:%s"
git log -S "H1"                              # When was H1 added
git log --grep="fix bug"
git log --since="2024-01-01"
git log --until="2024-01-01"
git log --author="Paul"
git log --no-merge
```

---

## Remote Repo: Version of your project on hosted repo (e.g., GitHub)

1. `git remote add origin <URL>`: Add remote repo (see `git remote -v`)
2. `git branch -M main`: Rename master to main
3. `git push -u origin main`: Set upstream & push changes to remote repo
4. `git pull`: Pull changes from remote repo
5. `git clone`: Clone remote repo

---

## GitHub Authentication

1. Personal Access Token (PAT)
2. `git remote set-url origin https://<TOKEN>@github.com`
3. `https://<TOKEN>@github.com/<USERNAME>/<REPO>.git'
4. `git remote set-url origin <SSH-URL>`

---

## GIT Branch and Merge

```bash
git branch                      # See branches            
git branch design               # Create branch
git checkout design             # Switch to branch
git merge design                # Merge branch 'design' to current branch
```

---

## GIT Merge Conflict

- When two branches edit the same file and try to merge, this causes a conflict.
- Resolve the conflict manually, edit the conflict file, and commit the changes.

---

## Fork and Pull Request

- Fork the repository, make changes, and submit a pull request to contribute.

---

## .gitignore

- Specify files or directories that should be ignored by Git.

---

## Git Clean

```bash
git clean -n                   # Preview untracked files that will be deleted
git clean -f                   # Delete untracked files permanently
```

---

## Tags: Create release points from tags

```bash
git tag
git tag -a <tag_name> -m "message"             # Tag latest commit
git tag -a <tag_name> <commit_id> -m "msg"     # Tag an old commit
git push origin --tags                         # Push all tags to remote
```
