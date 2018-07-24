## Mario Marathon Stamp Monitor
#### Gage Ames (gage@gageames.com)
A simple [Azure Logic App](https://azure.microsoft.com/en-us/services/logic-apps/) to monitor the [Mario Marathon](http://www.mariomarathon.com) passport stamps. The app sends an email notification about passport stamps that recently became available.

### Getting Started
Update the [StampMonitorLogicApp.Parameters.json](.\StampMonitorLogicApp.Parameters.json) file with the desired notification email addresses and Azure API Connection IDs. After the parameters are configured, deploy a new Azure Logic App or update an existing Azure Logic App using the [Azure PowerShell](https://github.com/Azure/azure-powershell/releases) commands below.

### Deploy a New Instance
To deploy a new instance of the Azure Logic App, run the following command:
```PowerShell
New-AzureRmLogicApp -ResourceGroupName $resourceGroupName -Name $logicAppName -Location $logicAppLocation -State "Enabled" -DefinitionFilePath ".\StampMonitorLogicApp.json" -ParameterFilePath ".\StampMonitorLogicApp.Parameters.json"
```

### Updating the Definition
To update the definition on an existing Azure Logic App, run the following command:
```PowerShell
Set-AzureRmLogicApp -ResourceGroupName $resourceGroupName -Name $logicAppName -DefinitionFilePath ".\StampMonitorLogicApp.json"
```

### Updating the Parameters
To update the parameters on an existing Azure Logic App, run the following command:
```PowerShell
Set-AzureRmLogicApp -ResourceGroupName $resourceGroupName -Name $logicAppName -ParameterFilePath ".\StampMonitorLogicApp.Parameters.json"
```
