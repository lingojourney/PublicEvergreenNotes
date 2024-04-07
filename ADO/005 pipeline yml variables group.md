In Azure DevOps (ADO), a **variable group** is a collection of related variables that can be accessed and used in Azure Pipelines, particularly in YAML pipelines. These groups are useful for sharing variables across multiple pipelines or for organizing them in a way that makes sense for your projects and teams.

Here's a brief explanation of how variable groups work in YAML pipelines:

- **Creating a Variable Group**: You can't create a variable group directly in YAML, but you can use the Azure DevOps CLI to create and manage them. Once created, they can be referenced in your YAML pipeline.
  
- **Using a Variable Group**: To use a variable group in your YAML pipeline, you reference it in the `variables` section of your YAML file like so:
  ```yaml
  variables:
    - group: my-variable-group
  ```
  After referencing it, you can use the variables defined in the group throughout your pipeline.

- **Secret Variables**: Secret variables in variable groups are protected resources. You can add combinations of approvals, checks, and pipeline permissions to limit access to these secret variables.

- **Referencing Variables**: To reference a variable from a variable group, you can use macro syntax like `$(myVariable)` or runtime expressions like `$[variables.myVariable]`.

For more detailed information, you can refer to the official [Azure Pipelines documentation](^1^) on variable groups. 😊

Source: Conversation with Bing, 03/04/2024
(1) Variable groups for Azure Pipelines - Azure Pipelines. https://learn.microsoft.com/en-us/azure/devops/pipelines/library/variable-groups?view=azure-devops.
(2) Define variables - Azure Pipelines | Microsoft Learn. https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops.
(3) Using a pipeline variable to define which variable group to use in YAML .... https://stackoverflow.com/questions/70548076/using-a-pipeline-variable-to-define-which-variable-group-to-use-in-yaml-script.
(4) How to use a variable group in a Azure Pipelines yml template?. https://stackoverflow.com/questions/71823963/how-to-use-a-variable-group-in-a-azure-pipelines-yml-template.