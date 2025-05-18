# Git

- To update the commit message even if we have pushed it on remote
> it is discouraged and cause problems if multiple people are working on the same branch as it involves history rewriting

```bash
  git commit --amend -m "Your corrected commit message"
```
```bash
  git push --force-with-lease origin <branch name>
```
