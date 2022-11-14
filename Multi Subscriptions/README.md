## Azure Service Health Email Notification Template - Multi Subscription
# High Level Design
![HLD](/images/mode1hld.png)

# Use the template to deploy resources
1. In the portal, search and select "Deploy a custom template"
![Deploy a custom template](/images/deploytemplate.png)

2. Click on " Build your own template in the editor"
![Build your own template in editor](/images/customdeployment.png)

3. Select "Load File" and choose the "Action Group" template first
![Load Template](/images/loadtemplate.png)

4. Fill out the form and select "Review + Create". Keep in mind that the Action Group should be placed in a "central" subscription visible by users that will create the action groups. 
![Action Group Template](/images/agtemplate.png)

5. Go and copy the action group "resource id" previously created by going to "Monitor" -> "Alerts" -> "Action Groups" -> select your action group -> select "Properties" and copy the resource id.

6. Reproduce step 1, 2 & 3 with the "Alert Rule" template
![Alert Rule Template](/images/artemplate.png)

7. Fill out the form, paste the "resource id" previously copied, choose the "Event Type" and select "Review + Create".