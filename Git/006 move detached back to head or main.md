If you have made commits in the detached HEAD state and want to merge those changes back into `main`, follow these steps:

1. Create a new branch from the detached HEAD state to save your changes:
    
    ```shell
    git branch temp-branch
    ```
    
2. Switch to the `main` branch (or `master`, if that’s your main branch):
    
    ```shell
    git checkout main
    ```
    
3. Merge the new temporary branch into `main`:
    
    ```shell
    git merge temp-branch
    ```
    
4. If you no longer need the temporary branch after merging, you can delete it:
    
    ```shell
    git branch -d temp-branch
    ```
    

This will safely transfer your commits from the detached HEAD state into your `main` branch.

If you need further assistance with Git, feel free to ask!