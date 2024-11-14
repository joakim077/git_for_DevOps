
### Revert vs Reset

#### git revert: Modifies the commit history by moving the branch pointer to an earlier commit.

```bash
git revert <commit-hash>
```

#### git reset: : Does not change the commit history. It creates a new commit that undoes the changes.  

```bash
git reset --hard <commit-hash>
```
**Tip**: Be cautious while running reset.

---

### Merge & Rebase

#### git merge: Combines two branches by creating a merge commit.

```bash
git merge <branch_name>
```

#### git rebase: Rewrites commit history by placing your commits on top of another branch (linear history). Does not create a merge commit.
```bash
git rebase <master>
```
  
**Resolve conflict in rebase**: Resolve conflict, then run:
```bash
git add <fileName>
git rebase --continue
```

**Note**: Never run on the main branch.

---

### Squash

Git squash refers to the process of combining multiple commits into a single commit.

- **Squashing during a merge**:
```bash
git merge --squash <branch>
```

- **Squashing during a rebase**:
```bash
git rebase -i HEAD~4
```
and use `pick` or `squash`.

---

### Stash

Helps save changes that you are not yet ready to commit.

#### stash: Stash changes.
```bash
git stash
```
#### pop: Remove the most recent stashed changes and reapply them to your working copy.
```bash
git stash pop
```

```bash
git stash list
```

```bash
git stash apply stash@{2}
```

```bash
git stash drop stash@{2}
```

```bash
git stash clear
```

#### stash apply: Apply whatever is stashed without removing it from the stash.

```bash
git stash apply
```

#### Stash untracked files as well.
```bash
git stash -u
```

---

### CherryPick

Similar to merge or rebase, but instead of merging the entire branch, selected commits are merged.

```bash
git cherry-pick <hash1> <hash2>
```
