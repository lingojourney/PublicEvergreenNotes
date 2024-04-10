To remove local branches in Git, you can use the following command:

```bash
git branch -d <branch-name>
```

Replace `<branch-name>` with the name of the branch you want to delete. If the branch has unmerged changes and you are certain you want to delete it, you can use the `-D` option to force the deletion:

```bash
git branch -D <branch-name>
```

This will delete the branch locally. Be cautious with the `-D` option as it will permanently delete the branch and its changes¹².

Source: Conversation with Bing, 09/04/2024
(1) How do I delete a local branch in Git?. https://www.git-tower.com/learn/git/faq/delete-local-branch/.
(2) How do I delete a Git branch locally and remotely?. https://stackoverflow.com/questions/2003505/how-do-i-delete-a-git-branch-locally-and-remotely.
(3) Git Delete Branch – How to Remove a Local or Remote Branch. https://www.freecodecamp.org/news/git-delete-branch-how-to-remove-a-local-or-remote-branch/.
(4) How To Clean Up Git Branches – devconnected. https://devconnected.com/how-to-clean-up-git-branches/.
(5) How to Delete Local and Remote Git Branches | Refine. https://refine.dev/blog/git-delete-remote-branch-and-local-branch/.