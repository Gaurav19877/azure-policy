# Apply Diagnostic Settings for Network Security Groups

This policy automatically deploys diagnostic settings to network security groups.

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/?feature.customportal=false&microsoft_azure_policy=true&microsoft_azure_policy_policyinsights=true&feature.microsoft_azure_security_policy=true&microsoft_azure_marketplace_policy=true#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-policy%2Fmaster%2Fsamples%2FMonitoring%2Fdefault-diagnostic-setting%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzureRmPolicyDefinition -Name "default-diagnostic-setting" -DisplayName "Apply Diagnostic Settings for Network Security Groups" -description "This policy automatically deploys diagnostic settings to network security groups." -Policy 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Monitoring/default-diagnostic-setting/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Monitoring/default-diagnostic-setting/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope>  -storagePrefix <Storage Account Prefix for Regional Storage Accounts> -rgName <Resource Group Name for Storage Accounts( must exists) > -PolicyDefinition $definition
$assignment 
````



## Try with CLI

````cli

az policy definition create --name 'default-diagnostic-setting' --display-name 'Apply Diagnostic Settings for Network Security Groups' --description 'This policy automatically deploys diagnostic settings to network security groups.' --rules 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Monitoring/default-diagnostic-setting/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Monitoring/default-diagnostic-setting/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "default-diagnostic-setting" 

````
