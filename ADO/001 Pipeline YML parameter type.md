In Azure DevOps (ADO), when defining parameters in a YAML pipeline, you can specify various data types. Here’s a list of the parameter types you can use:

- **string**: A sequence of characters.
- **number**: Numerical values, which can be restricted to specific values.
- **boolean**: `true` or `false`.
- **object**: Any YAML structure.
- **step**: A single step.
- **stepList**: A sequence of steps.
- **job**: A single job.
- **jobList**: A sequence of jobs.
- **deployment**: A single deployment job.
- **deploymentList**: Sequence of deployment jobs.
- **stage**: A single stage.
- **stageList**: A sequence of stages.

Parameters must contain a name and a data type, and they cannot be optional. You need to assign a default value in your YAML file or when you run your pipeline. [If you don’t assign a default value or set default to false, the first available value is used](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[2](https://learn.microsoft.com/en-us/azure/devops/pipelines/yaml-schema/parameters-parameter?view=azure-pipelines).

Here’s an example of how you might define parameters in your YAML pipeline:

```yaml
parameters:
  - name: image
    displayName: 'Pool Image'
    type: string
    default: 'ubuntu-latest'
    values:
      - 'windows-latest'
      - 'ubuntu-latest'
      - 'macOS-latest'

  - name: test
    displayName: 'Run Tests?'
    type: boolean
    default: false
```

[In this example, the `image` parameter allows you to select an agent image from a predefined list, and the `test` parameter controls whether tests are run in the pipeline](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[3](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/runtime-parameters?view=azure-devops). Remember to check the for the most up-to-date information on YAML schema and parameter types.