To ignore target folders in Git, you can create a `.gitignore` file in the root directory of your project and add the following line to it:

```
target/
```

This will ensure that the `target` directory is not tracked by Git and won’t be included in your commits. If you have multiple target directories in different subdirectories and want to ignore them all, you can use the following pattern:

```
**/target/
```

[This pattern will match any `target` directory, no matter where it is located in your project structure](https://stackoverflow.com/questions/44163775/how-to-avoid-to-add-the-target-folder-into-a-git-commit)[1](https://stackoverflow.com/questions/44163775/how-to-avoid-to-add-the-target-folder-into-a-git-commit)[2](https://stackoverflow.com/questions/991801/git-ignores-and-maven-targets). Remember, if you’ve already tracked files or directories that you now want to ignore, you’ll need to remove them from the index with the following command before they will be ignored:

```bash
git rm --cached -r target/
```

Then commit the changes:

```bash
git commit -m "Remove target directory from Git tracking"
```

[After these steps, the `target` folders will be ignored by Git](https://stackoverflow.com/questions/44163775/how-to-avoid-to-add-the-target-folder-into-a-git-commit)[1](https://stackoverflow.com/questions/44163775/how-to-avoid-to-add-the-target-folder-into-a-git-commit).