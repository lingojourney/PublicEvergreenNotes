Yes, it's possible to replace the contents of your current directory with the contents of another branch without merging. You can use the `git checkout` command with the `--force` option to do this. Here's how:

1. Make sure you have no uncommitted changes, as this process will overwrite them. Commit or stash any changes you have.

2. Then, use the following command to replace the contents of your current directory with those from `temp-branch`:
   ```shell
   git checkout temp-branch --force
   ```

This command will forcefully switch your current working directory to match the exact state of `temp-branch`, discarding any local changes or commits that haven't been applied to `temp-branch`.

Please proceed with caution, as this action cannot be undone.

If you need further assistance, feel free to ask!