If you accidentally add a file to git that you did not mean to track, such as a large file or file with sensitive information, you can remove it from git while keeping it locally.

## Steps

1. Delete the file from the working tree and stage the removal 

    ```
    git rm --cached path/to/file
    ```

    This removes the file from git but keeps it on your filesystem.

2. Commit the removal

    ```
    git commit -m "Remove file that was accidentally added"
    ```

3. Amend previous commits to remove the file from their history

    ```
    git filter-branch --force --index-filter \
    "git rm --cached --ignore-unmatch path/to/file" \
    --prune-empty --tag-name-filter cat -- --all
    ```

    This will rewrite history to remove the file from all previous commits.

4. Force push to origin to overwrite remote history

    ```
    git push origin --force --all
    ```

    Be very careful with this, as it will overwrite remote history! Make sure no one else is working off the remote containing the file.

The file is now removed from git's history, but still exists untouched in your working tree.