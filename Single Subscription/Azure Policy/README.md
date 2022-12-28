# Azure Service Health Email Notification Template - Single Subscription deployment with Azure Policy

## Use the templates to deploy resources
1. To deploy this policy, you have to create an Action Group (the only requierement for this resource is to be deployed in the same tenant)

2. Once deployed, you will have to copy the resourceId. It should be something like this :
/subscriptions/'SubscriptionID'/resourceGroups/'ResourceGroupName'/providers/microsoft.insights/actionGroups/'ActionGroupName'

3. Copy the content of one of the [policy.json file](https://github.com/nteyan/azure-servicehealth-alerting-automation/blob/main/Single%20Subscription/Azure%20Policy/policy.json) and create a new Policy Definition.

4. To create a Policy definition, go to the Azure Portal and go to the [Policy blade](https://portal.azure.com/#view/Microsoft_Azure_Policy/PolicyMenuBlade/~/Overview)

5. Go to "Definitions" and select "+ Policy Definition"
- Definition location : Can be a Management Group or a Subscription
- Name : The name of your policy definition
- Policy Rule : Paste the content of the policy.json file choosen

6. Save the Policy Definition by selecting "Save"

7. Once deployed, Assign this policy to a management group or a subscription, fill the "resourceGroupName" and "actionGroupId" in the Parameters tab, don't forget to change the System assigned identity to your region and then select "Review + Create"

The Action Group and the alert rule will be deployed in the same resource group