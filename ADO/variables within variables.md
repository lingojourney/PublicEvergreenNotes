In Azure DevOps (ADO), you can use variables within other variables, but there are some limitations and specific methods to do so. Here’s a general overview:
AD
- **User-defined variables**: You can define variables at different levels (pipeline, stage, job) and use them throughout the pipeline. Variables are treated as strings and can be mutable. [The most locally scoped variable will take precedence if there are variables with the same name defined at multiple levels](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops).
    
- [**System variables**: Azure Pipelines also provides system variables with predefined values, which you can use alongside user-defined variables](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops).
    
- [**Variable syntax**: When defining a variable, you can use macro, template expression, or runtime syntax, which determines where in the pipeline your variable is rendered](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops).
    
- **Nested variables**: Directly nesting variables (using a variable within another variable) is not supported. However, you can define a new variable and map its value to the desired variable. [For example, if you have a variable `KeyVault_Key`, you can create another variable that takes its value](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[2](https://stackoverflow.com/questions/64229812/how-to-use-a-variable-within-another-variable-in-azure-devops).
    

Here’s an example of how you might use a variable within another variable in a YAML pipeline:

```yaml
variables:
  - name: sqlConnectionNameKey
    value: $(TF_VAR_MYSQL_SERVER_USERNAME_KEY)
  - name: sqlConnectionPwdKey
    value: $(TF_VAR_MYSQL_SERVER_PASSWORD_KEY)

jobs:
  - deployment: DeployApiDatabase
    pool:
      name: Default
    environment:
      name: Azure
    strategy:
      runOnce:
        deploy:
          steps:
            - task: AzureKeyVault@1
              displayName: 'Get Secrets'
              inputs:
                azureSubscription: ${{parameters.azureSubscription}}
                KeyVaultName: '$(TF_VAR_RESOURCE_PREFIX)-kv'
                SecretsFilter: '${{variables.sqlConnectionNameKey}}, ${{variables.sqlConnectionPwdKey}}'
                RunAsPreJob: true
            - task: AzureMysqlDeployment@1
              displayName: 'Deploy ApplicationConfigurationDbContext DB'
              inputs:
                azureSubscription: ${{parameters.azureSubscription}}
                ServerName: '$(sqlServerName).mysql.database.azure.com'
                DatabaseName: 'DatabaseName'
                SqlUsername: '$(sqlConnectionNameKey)@$(sqlServerName)'
                SqlPassword: '$(sqlConnectionPwdKey)'
                TaskNameSelector: 'SqlTaskFile'
                SqlFile: '${{variables.mySqlLocation}}DbContext.sql'
                IpDetectionMethod: 'AutoDetect'
```

[In this example, `sqlConnectionNameKey` and `sqlConnectionPwdKey` are variables that take their values from other variables and are then used within the Azure Key Vault task](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[2](https://stackoverflow.com/questions/64229812/how-to-use-a-variable-within-another-variable-in-azure-devops).

[For more detailed information and examples, you can refer to the official Azure DevOps documentation on defining variables](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops) [and discussions on Stack Overflow](https://stackoverflow.com/questions/64229812/how-to-use-a-variable-within-another-variable-in-azure-devops)[2](https://stackoverflow.com/questions/64229812/how-to-use-a-variable-within-another-variable-in-azure-devops). [Remember to format your variables correctly and be aware of the operating system of your agent when using multi-line variables](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops)[1](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/variables?view=azure-devops).