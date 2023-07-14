## How to commit local changes to a new Git branch

1. Make sure you're on the branch that you want to base your new branch off of. You can check which branch you're currently on by running:

   `````
   git branch
   ```

   The current branch will be highlighted with an asterisk.

2. Create a new branch by running:

   ````
   git branch <new-branch-name>
   ````

   Replace `<new-branch-name>` with the name you want to give your new branch.

3. Switch to your new branch by running:

   ````
   git checkout <new-branch-name>
   ````

4. Stage the changes you want to commit by running:

   ````
   git add <file1> <file2> ...
   ````

   Replace `<file1>`, `<file2>`, etc. with the names of the files you want to stage. Alternatively, you can stage all changes by running `git add .` (note the period at the end).

5. Commit your changes by running:

   ````
   git commit -m "<commit-message>"
   ````

   Replace `<commit-message>` with a brief description of the changes you made.

6. Push your new branch to the remote repository by running:

   ````
   git push -u origin <new-branch-name>
   ````

   This will create your new branch on the remote repository and set it to track your local branch.

And that's it! Your changes are now safely stored in a new Git branch.