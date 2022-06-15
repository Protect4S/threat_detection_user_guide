---
description: Allow and Deny policy configuration
---

# !Allow / Deny Policy

![Allow / Deny Policy configuration](<../../.gitbook/assets/image (40).png>)

If you have the been granted to security configurator role or the administrator role, you can access "Allow / Deny Policy configurator" Fiori Tile. Please visit [this](../systems-in-threat-detection/system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations.

The allow and deny policies are one of the configurations is one of the most critical step to configure, you may configure the policy per your needs per system.

****\
**Note:**\
****Awareness is critical here, a misconfiguration here means that certain threats might not get reported to SIEM.\
For example if you added a user to this allow list that should not be allowed to perform user administration. The system will then not report the threat to SIEM and will only see this as an event.

### Policy configuration

Upon opening the Allow / Deny Policy application, the following screen shows up:

![Allow / Deny Polices list](<../../.gitbook/assets/image (31) (1).png>)

On the left hand side, we can see the attributes of the policy.\
Each attribute have their own importance depending on the policy it applies for. See the table at the bottom of the page.

![Policy details](<../../.gitbook/assets/image (71).png>)

On the right side of the screen, we can see that this policy is used in 3 different Use Cases, this means that adjusting this policy affect the 3 Use Cases.

![Linked use cases](<../../.gitbook/assets/image (62).png>)

In this example Policy 1000 - User(s) allowed for user administration (technical name: Allowlisted\_useradmins) is used.&#x20;

![Policy details](<../../.gitbook/assets/image (31).png>)

We can see that this policy is about users, which means that Case sensitive has no meaning because users in SAP is in uppercase by default and Risk management is not applied it is an allow list where you rarely indicate what risk it would have whilst the user is permitted to perform certain action.

### Adjusting the policy rule

In this tutorial, we would like to change a user in this allow policy list for User Administration.

Below you can see that the current values are already defined for CUAADM and any user that starts with GRC because a wildcard is used at the end.

![Policy values](<../../.gitbook/assets/image (63) (1).png>)

If you enter in edit mode, you can change the value of the policy, in our example, we have changed the value "CUAADM" to "CUAADMINISTRATOR". The values entered here will be converted to uppercase automatically.

![Editing policy](<../../.gitbook/assets/image (61).png>)

After your changes, click on the save button at the lower right corner.

![](<../../.gitbook/assets/image (33).png>)

To create a rule in the policy, while in edit mode; click on the Create button a new line will appear, enter the value you wish to add.

![Adding a rule in a policy](<../../.gitbook/assets/image (19).png>)

Click on Save to commit your changes at the lower right corner.

![](<../../.gitbook/assets/image (33).png>)

To remove a policy rule, simply go to edit mode, select the rule you wish to remove and click on delete.

The below screenshot we will remove the rule we just created.

![Removing a rule](<../../.gitbook/assets/image (74).png>)

To finalize, click on Save to commit your changes at the lower right corner.

![](<../../.gitbook/assets/image (33).png>)



### **Attribute legend:**

| Attribute name:  | Description of the attribute:                                                                                                                                                                                                                                                                                                                                                                                                |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Policy ID        | The unique identifier number for the policy, Allow policies starts with 1000, Deny policies starts with 2000                                                                                                                                                                                                                                                                                                                 |
| Default          | Indicates whether this policy is the initial shipped or not                                                                                                                                                                                                                                                                                                                                                                  |
| Description      | Human readable description of the policy                                                                                                                                                                                                                                                                                                                                                                                     |
| Restriction Type | Indicates whether the policy is an allow or deny policy                                                                                                                                                                                                                                                                                                                                                                      |
| Scope            | Type of systems this policy applies to                                                                                                                                                                                                                                                                                                                                                                                       |
| Case Sensitive   | Indicates whether the values entered are Case sensitive or not                                                                                                                                                                                                                                                                                                                                                               |
| Wildcard Enabled | <p>Indicates whether the wildcard symbol (asterisk) can be used or will be seen as a wildcard. <br>Note, if the policy is related to users, where the username starts with SAP, do not use wildcard, but enter the user(s) manually. This is because of the existence of the emergency user that exist in the system (SAP*). In general you would not want anyone to misuse the emergency user SAP* to perform anything.</p> |
| Risk Enabled     | Indicates whether the risk field is included along                                                                                                                                                                                                                                                                                                                                                                           |
| Final            | Indicates whether the default shipped policy can be copied or not by customers. When Final = NO the default policy can be copied and customised by customers                                                                                                                                                                                                                                                                 |
| Technical Name   | Technical name of the policy which will be used to assign the policy to an use case along with the Policy ID                                                                                                                                                                                                                                                                                                                 |

The table above explains what each attribute means.
