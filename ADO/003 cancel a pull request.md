To cancel a pull request in Azure DevOps, you can abandon it. Here’s how you can do it:

1. Navigate to the **Pull Requests** section in your Azure DevOps project.
2. Find and select the pull request you wish to cancel.
3. On the pull request details page, look for the **More options** menu (usually represented by three dots or an ellipsis).
4. From the dropdown menu, select **Abandon pull request**.

Once you abandon the pull request, it will be marked as such, and the changes proposed in it will not be merged into the target branch. [If you decide to proceed with the changes later, you can reactivate the abandoned pull request](https://learn.microsoft.com/en-us/azure/devops/repos/git/complete-pull-requests?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/repos/git/complete-pull-requests?view=azure-devops).

If you’re using the Azure CLI, you can also abandon a pull request with the following command:

```bash
az repos pr update --id <PR Id> --status abandoned
```

[Replace `<PR Id>` with the actual ID of the pull request you want to cancel](https://learn.microsoft.com/en-us/azure/devops/repos/git/complete-pull-requests?view=azure-devops)[2](https://www.iheavy.com/how-to-abandon-a-pull-request-in-azure-devops/). [Remember, once a pull request is abandoned, it cannot be deleted from Azure DevOps; it will remain in the system for historical tracking](https://stackoverflow.com/questions/60291096/how-to-permanently-delete-an-abandoned-pull-request-in-azure-devops)[3](https://stackoverflow.com/questions/60291096/how-to-permanently-delete-an-abandoned-pull-request-in-azure-devops).