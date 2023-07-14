## Basic Commands

- `git init`: Initialize a new Git repository.
- `git clone [repository_url]`: Clone a repository from a remote server.
- `git add [file_name]`: Add a file to the staging area.
- `git commit -m "[commit_message]"`: Commit changes with a descriptive message.
- `git status`: View the status of files in the repository.
- `git log`: Display the commit history.
- `git pull`: Fetch and merge changes from a remote repository.
- `git push`: Push local commits to a remote repository.

## Branching and Merging

- `git branch`: List branches in the repository.
- `git branch [branch_name]`: Create a new branch.
- `git checkout [branch_name]`: Switch to a different branch.
- `git merge [branch_name]`: Merge changes from another branch.
- `git rebase [branch_name]`: Reapply commits on top of another branch.

## Remote Repositories

- `git remote add [remote_name] [remote_url]`: Add a remote repository.
- `git remote -v`: List remote repositories.
- `git fetch [remote_name]`: Fetch changes from a remote repository.
- `git push [remote_name] [branch_name]`: Push local branch to a remote repository.
- `git pull [remote_name] [branch_name]`: Pull changes from a remote repository.

## Submodules

- `git submodule add [repository_url] [path]`: Add a submodule to the repository.
- `git submodule init`: Initialize submodules after cloning a repository.
- `git submodule update`: Update submodules to the latest commit.
- `git submodule foreach [command]`: Execute a command in each submodule.
- `git submodule sync`: Synchronize submodule URLs with the .gitmodules file.

## Undoing Changes

- `git checkout -- [file_name]`: Discard changes in a specific file.
- `git reset HEAD [file_name]`: Unstage changes in a file.
- `git revert [commit_id]`: Create a new commit that undoes a previous commit.
- `git reset [commit_id]`: Discard commits and move the branch pointer.
- `git clean -f`: Remove untracked files from the working directory.

## Collaboration

- `git branch -r`: List remote branches.
- `git branch -a`: List all local and remote branches.
- `git branch -d [branch_name]`: Delete a branch.
- `git push [remote_name] --delete [branch_name]`: Delete a remote branch.
- `git fetch --prune`: Remove deleted branches from the local repository.

Sure, here's how you might structure that information as an Obsidian note in Markdown format:

```markdown
# Git Troubleshooting Guide

## Error: Fetch First

When you see the message "fetch first," it typically means that there have been changes to the remote repository that you don't have on your local machine. 

To solve this:

1. **Fetch the changes from the remote repository**
   ```bash
   git fetch origin
   ```

2. **Merge the changes into your local branch**
   ```bash
   git merge origin/master
   ```

3. **Resolve any merge conflicts**

   Once you've resolved any conflicts, add the resolved files with:
   ```bash
   git add .
   ```
   Then commit the changes with:
   ```bash
   git commit -m "Your commit message"
   ```

4. **Push your changes to the remote repository**
   ```bash
   git push origin master
   ```

## Error: Refusing to Merge Unrelated Histories


If you're seeing the "refusing to merge unrelated histories" error message, it typically means that Git is trying to merge two projects or histories that don't share a common ancestor.

To resolve this:

1. Use the `--allow-unrelated-histories` flag:
   ```bash
   git pull origin master --allow-unrelated-histories
   ```
   or
   ```bash
   git merge origin/master --allow-unrelated-histories
   ```

2. Resolve any merge conflicts:

   Once you've resolved any conflicts, add the resolved files with:
   ```bash
   git add .
   ```
   Then commit the changes with:
   ```bash
   git commit -m "Your commit message"
   ```

Be cautious when using the `--allow-unrelated-histories` flag, as it can lead to an unexpected merging of unrelated projects if used without understanding its implications.
```

Remember that in the command line code blocks, `origin` is your remote repository and `master` is your branch name. You should replace these with your actual remote name and branch name if they are different.

# Kata: Commit local changes to a new branch 
1. First, you need to ensure all your changes are staged for commit. If you haven't done so, use the command below:

    ```bash
    git add .
    ```
    `.` will stage all changes. If you only want to stage specific files, replace `.` with the file paths.

2. Now you can create a new branch. This will not change any files in your working directory:

    ```bash
    git branch my-new-branch
    ```
    Replace `my-new-branch` with the name you want for your new branch.

3. Switch to your new branch:

    ```bash
    git checkout my-new-branch
    ```
    Again, replace `my-new-branch` with the name of your new branch.

4. Now you can commit your changes:

    ```bash
    git commit -m "Your commit message"
    ```
    Replace `Your commit message` with a description of the changes you made.

5. Finally, if you want to push this new branch to your remote repository (for example, if you're using GitHub), you can use:

    ```bash
    git push origin my-new-branch
    ```
    Replace `my-new-branch` with the name of your new branch. This command will create the new branch on your remote repository and push your commit to it.

Please remember to replace `my-new-branch` and `"Your commit message"` with the name of your branch and the commit message respectively. You should make your commit messages as descriptive and specific as possible, to help others (and future you) understand the changes that were made.
# Git Add Flags

| Command                 | Description                                                | Deleted Files        | Modified Files       | New Files            |
|-------------------------|------------------------------------------------------------|----------------------|----------------------|----------------------|
| `git add [file_name]`   | Add a specific file to the staging area.                   |                      | Modified             |                      |
| `git add -A`            | Add all modified, deleted, and new files to the staging area. | Deleted              | Modified             | New                  |
| `git add -u`            | Add modified and deleted files to the staging area (excluding untracked files). | Deleted              | Modified             |                      |
| `git add .`             | Add all modified and new files to the staging area (excluding deleted files). |                      | Modified             | New                  |

# Selected Mnemonics
## to remember the `git add` commands

1. `git add [file_name]`: "Add a specific file to the staging area."
   - Mnemonic: "Add File, Be Specific" (AFBS)

2. `git add -A`: "Add all modified, deleted, and new files to the staging area."
   - Mnemonic: "Add All Changes" (AAC)

3. `git add -u`: "Add modified and deleted files to the staging area (excluding untracked files)."
   - Mnemonic: "Add Updated" (AU)

4. `git add .`: "Add all modified and new files to the staging area (excluding deleted files)."
   - Mnemonic: "Add Modified and New" (AMN)