## ❶
To parameterize an Azure DevOps (ADO) pipeline for multiple artifacts, you can use runtime parameters and conditional insertions within your YAML file. This allows you to dynamically select which artifacts to build and publish based on the parameters passed at the start of the pipeline run.

Here’s a simplified example of how you might set up your YAML pipeline to handle multiple artifacts:

```yaml
parameters:
- name: buildArtifact
  displayName: 'Artifact to Build'
  type: string
  default: 'all'
  values:
  - 'api'
  - 'ui'
  - 'all'

stages:
- stage: Build
  jobs:
  - job: BuildAPI
    condition: or(eq('${{ parameters.buildArtifact }}', 'api'), eq('${{ parameters.buildArtifact }}', 'all'))
    steps:
    - script: echo Building API
      displayName: 'Build API'
    - publish: $(System.DefaultWorkingDirectory)/api
      artifact: API

  - job: BuildUI
    condition: or(eq('${{ parameters.buildArtifact }}', 'ui'), eq('${{ parameters.buildArtifact }}', 'all'))
    steps:
    - script: echo Building UI
      displayName: 'Build UI'
    - publish: $(System.DefaultWorkingDirectory)/ui
      artifact: UI
```

In this example, the `parameters` section defines a parameter `buildArtifact` that can take the values ‘api’, ‘ui’, or ‘all’. The `condition` for each job checks this parameter to determine whether to run the job. If ‘all’ is selected, both jobs will run and publish their respective artifacts.

For more complex scenarios, you might need to use templates or scripts to handle the artifacts more dynamically. [You can find more detailed examples and explanations in the Azure DevOps documentation and community resources like Stack Overflow](https://devops.stackexchange.com/questions/9156/single-build-with-multiple-artifacts)[1](https://devops.stackexchange.com/questions/9156/single-build-with-multiple-artifacts)[2](https://stackoverflow.com/questions/69104964/azure-devops-release-pipeline-with-multiple-artifacts-and-stages). Remember to test your pipeline thoroughly to ensure that the parameterization works as expected.

## ❷
To set up Azure DevOps pipeline parameters outside of the YAML file, you can use the Azure DevOps user interface (UI). Here’s how you can do it:

1. **Navigate to your Pipeline**: Go to your Azure DevOps project and select the pipeline you want to configure.
2. **Edit the Pipeline**: Click on the “Edit” button to open the pipeline editor.
3. **Access the Variables Section**: Look for the “Variables” tab or section in the pipeline editor.
4. **Add a New Variable**: Click on “New variable” or “Add” to create a new variable.
5. **Set the Variable Name and Value**: Enter the name for your variable and its value. If you want to create a secret variable (like a password or token), you can mark it as secret.
6. **Save the Changes**: After adding all the necessary variables, save your changes.

These variables will be available for use in your YAML pipeline as if they were defined within the YAML file itself. [You can reference them using the standard syntax, such as `$(variableName)`](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops).

For more complex parameterization, such as defining runtime parameters with specific data types and allowed values, you would still need to define these within the YAML file. [However, the UI approach is useful for simpler scenarios and for managing secret variables securely](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[2](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/runtime-parameters?view=azure-devops)[3](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/template-parameters?view=azure-devops).

[Remember that variables set in the UI can be encrypted and marked as secret, providing an additional layer of security for sensitive information](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops).