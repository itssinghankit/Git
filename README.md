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

