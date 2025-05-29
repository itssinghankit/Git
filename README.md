# Git

### To update the commit message even if we have pushed it on remote
> it is discouraged and cause problems if multiple people are working on the same branch as it involves history rewriting

```bash
  git commit --amend -m "Your corrected commit message"
```
```bash
  git push --force origin <branch name>
                  or
  git push --force-with-lease origin <branch name>
```
> This command checks if your local branch is based on the same remote branch as when you last fetched. If the remote branch has been updated by someone else, the force push will be rejected.

### To delete the last commit even if we have pushed it on remote
> again involves history rewriting, so do it with caution

```bash
  git reset --hard HEAD~1
```
> if you only want to delete commit but dont want to delete any existing written code use `--soft` instead of `--hard`
```bash
  git push --force origin <branch_name>
```

### Stashing
if you dont want to commit the changes and still want to visit other branch make sure to save(stash) your changes first and can retrieve(pop) any time after visisting the same feature branch
```bash
  git stash
  git checkout old_branch
  git checkout feature_branch
  git stash pop 
```

### Pull vs Fetch
If you create a new branch `develop` from let say `master` and then all the existing commits exits in master will also get present in `develop` apart from whether it actually exist in `remote/develop` or not. 
Instead what you should do is fetch the `develop branch` and then checkout directly from any branch using
```bash
  git branch -b branch_name_develop remote_branch_name
```

> Always check if your local as well as remote heads are pointing to same commit or not, also check git graph to see if your branch is actually getiing deleted or not after you delete it

### Renaming branch
#### Locally
```bash
    git branch -m new-branch-name
```

```bash
  git branch -m old-branch-name new-branch-name
```

#### Remote
- Rename it locally:
```bash
  git branch -m old-branch-name new-branch-name
```

- Delete the old branch from the remote:
```bash
  git push origin --delete old-branch-name
```

- Push the renamed branch to remote:
```bash
  git push origin new-branch-name
```

- If you want to track the new remote branch:
```bash
  git push --set-upstream origin new-branch-name
```

### Discard changes
- unstaged (without add)
```bash
  git restore .
```

- staged
```bash
  git restore --staged .
          or
  git restore --staged <file>
```

- all changes
```bash
  git reset --hard HEAD
```
