There are a few ways to edit, erase or squash the commit history in Git:

- To edit the most recent commit message: 

`git commit --amend -m "New commit message"`

- To squash multiple commits into one:

`git rebase -i HEAD~N` (where N is number of commits to squash)

- To completely erase commits:

`git reset --hard COMMIT_HASH` (reset to specified commit, erasing later commits) 

- Or to erase everything after a commit: 

`git reset --hard HEAD~N` (reset last N commits, keeping changes)

- To interactively rebase and edit/erase specific commits:

`git rebase -i HEAD~N` 

In the rebase tool, change 'pick' to 'edit' for commits to modify, 'drop' to remove a commit, 'squash' to meld commits.

- To remove a file from the entire Git history:

`git filter-branch --index-filter 'git rm --cached --ignore-unmatch FILE-PATH' HEAD`

- To rewrite author/committer details: 

`git filter-branch --env-filter 'SCRIPT-TO-MODIFY-AUTHOR-ENV-VARS'`

In general, be very careful editing published commit history and avoid force pushing. An alternative is to revert problematic commits.