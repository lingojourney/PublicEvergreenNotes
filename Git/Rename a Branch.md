To rename a branch in Git, you'll use the `-m` option with the `git branch` command. Here is how to do it:

1. First, check that you're on the branch you want to rename:

```shell
git branch
```

This prints a list of all branches in your repository. The current branch is indicated with an asterisk (`*`).

2. If you're not already on the branch you want to rename, switch to it:

```shell
git checkout <old_branch_name>
```

3. Then, rename the branch:

```shell
git branch -m <new_branch_name>
```

This renames the current branch to `<new_branch_name>`.

If you're not currently on the branch you want to rename, you can do so by providing both the old and new names to the `git branch -m` command:

```shell
git branch -m <old_branch_name> <new_branch_name>
```

This renames `<old_branch_name>` to `<new_branch_name>`, regardless of your current branch.

Remember that if you've already pushed your branch to a remote repository, you'll also need to delete the old branch on the remote and push the new branch. Here's how:

1. Delete the old branch:

```shell
git push origin --delete <old_branch_name>
```

2. Push the new branch:

```shell
git push origin <new_branch_name>
```

3. Finally, set the remote branch for your local branch:

```shell
git branch --set-upstream-to=origin/<new_branch_name> <new_branch_name>
```

Now, both your local and remote repositories reflect the renamed branch.