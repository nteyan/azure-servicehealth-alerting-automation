# Azure Service Health Email Notification Template - Multi Subscription deployment with Azure Policy

## Folder content and description
- [policy4all.json](https://github.com/nteyan/azure-servicehealth-alerting-automation/blob/main/Multi%20Subscriptions/Policy/policy4all.json): Deploy alert rules for all Service Health alert (All regions, all Services, all event types)
- [policy4incident.json](https://github.com/nteyan/azure-servicehealth-alerting-automation/blob/main/Multi%20Subscriptions/Policy/policy4incident.json): Deploy alert rules for all Service Health Service Issue (All regions, all Services)
- [policy4security.json](https://github.com/nteyan/azure-servicehealth-alerting-automation/blob/main/Multi%20Subscriptions/Policy/policy4security.json): Deploy alert rules for all Service Health Security Issue (All regions, all Services)

## Use the templates to deploy resources
1. To deploy this policy, you have to create an Action Group (the only requierement for this resource is to be deployed in the same tenant)

2. Once deployed, you will have to copy the resourceId. It should be something like this :
/subscriptions/'SubscriptionID'/resourceGroups/'ResourceGroupName'/providers/microsoft.insights/actionGroups/'ActionGroupName'

3. Copy the content of one of the [policy.json file](https://github.com/nteyan/azure-servicehealth-alerting-automation/tree/main/Multi%20Subscriptions/Policy) and create a new Policy Definition.

4. To create a Policy definition, go to the Azure Portal and go to the [Policy blade](https://portal.azure.com/#view/Microsoft_Azure_Policy/PolicyMenuBlade/~/Overview)

5. Go to "Definitions" and select "+ Policy Definition"
- Definition location : Can be a Management Group or a Subscription
- Name : The name of your policy definition
- Policy Rule : Paste the content of the policy.json file choosen

6. Save the Policy Definition by selecting "Save"

7. Once deployed, Assign this policy to a management group or a subscription, fill the "resourceGroupName" and "actionGroupId" in the Parameters tab, don't forget to change the System assigned identity to your region and then select "Review + Create"

The alert rules will be deployed in a new resource group on each subscription (if you have choosen "Management Group" as scope during the assignment). All of them will be attached to a "central" Action Group to each the configuration management