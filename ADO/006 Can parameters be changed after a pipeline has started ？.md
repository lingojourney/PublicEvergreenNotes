In Azure DevOps (ADO), once a pipeline has started, the parameters defined in the YAML file cannot be changed. Parameters are only available at template parsing time and are expanded just before the pipeline runs. If you need to use different values during your pipeline run, you should use variables instead of parameters¹.

However, you can set default values for parameters that will be used if no value is provided at runtime. You can also use runtime expressions to dynamically select jobs and stages based on parameter values¹.

For automatic pipelines, the default parameter values are used, and you can set these values conditionally based on the trigger method (manual or CI) using If expressions².

If you're looking to change the behavior of a running pipeline dynamically, consider using variables and conditional logic within your YAML file to achieve the desired flexibility. 😊

Source: Conversation with Bing, 04/04/2024
(1) Use runtime and type-safe parameters - Azure Pipelines. https://learn.microsoft.com/en-us/azure/devops/pipelines/process/runtime-parameters?view=azure-devops.
(2) Setting parameter value dynamically for automatic pipelines. https://stackoverflow.com/questions/66249541/setting-parameter-value-dynamically-for-automatic-pipelines.
(3) Is it possible to add runtime parameters based on condition - Azure .... https://stackoverflow.com/questions/67184922/is-it-possible-to-add-runtime-parameters-based-on-condition-azure-devops-pipel.
(4) Configure schedules to run pipelines - Azure Pipelines. https://learn.microsoft.com/en-us/azure/devops/pipelines/process/scheduled-triggers?view=azure-devops.