To merge changes from one local branch to another in Git, follow these steps:

1. **Check out the branch you want to merge into** (the target branch):
   ```bash
   git checkout target-branch
   ```
2. **Merge the branch with the changes** (the source branch) into the target branch:
   ```bash
   git merge source-branch
   ```

Here's an example of merging changes from a branch named `feature` into the `main` branch:

```bash
git checkout main
git merge feature
```

This will merge all the commits from `feature` into `main`. The `feature` branch will remain unchanged¹.

Source: Conversation with Bing, 09/04/2024
(1) git - merge one local branch into another local branch - Stack Overflow. https://stackoverflow.com/questions/38206196/merge-one-local-branch-into-another-local-branch.
(2) How do I merge my local uncommitted changes into another Git branch .... https://stackoverflow.com/questions/556923/how-do-i-merge-my-local-uncommitted-changes-into-another-git-branch.
(3) How can I selectively merge or pick changes from another branch in Git .... https://stackoverflow.com/questions/449541/how-can-i-selectively-merge-or-pick-changes-from-another-branch-in-git.
