---
description: Allow and Deny policy configuration
---

# !Allow / Deny Policy

![Allow / Deny Policy configuration](<../.gitbook/assets/image (40).png>)

The allow and deny policies are one of the configurations is one of the most critical step to configure, you may configure the policy per your needs per system.

If you have the been granted to security configurator role or the administrator role, you can either access "Use Case Selection" Fiori Tile. Please visit [this](systems-in-threat-detection/system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations.



Upon opening the Allow / Deny Policy application, the following screen shows up:

![Allow / Deny Polices list](<../.gitbook/assets/image (31).png>)

In the following example the Policy ID 1000 is used.&#x20;

On the left hand side, we can see the attributes of the policy.\
Each attribute have their own importance depending on the policy it applies for.



| Attribute name:  | Description:                                                                                                                                                                                       |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Policy ID        | This is the the unique identifier number for the policy, Allow policies starts with 1000, Deny policies starts with 2000                                                                           |
| Restriction Type | This attribute indicates whether the policy is an allow or deny policy                                                                                                                             |
| Technical Name   | This is the technical name of the policy which will be used to assign the policy to an use case along with the Policy ID                                                                           |
| Case Sensitive   | This indicates whether the values entered are Case sensitive or not                                                                                                                                |
| Wildcard Enabled | This indicates whether the wildcard symbol (asterisk) can be used or will be seen as a wildcard, Users related Policy lists does not work with wildcard, because of the emergency user that exist. |
| Risk Enabled     | This indicates whether the risk field is included along                                                                                                                                            |
| Final            | This is to indicate whether the policy has been released for use or not. (internal only)                                                                                                           |



On the right side of the screen, we can see that this policy is used in 3 different Use Cases, this means that adjusting this policy affect the 3 Use Cases.

![Policy details](<../.gitbook/assets/image (71).png>)

In this tutorial, we would like to change a user in this allow policy list for User Administration.\


Below you can see that the current values are already defined for CUAADM and any user that starts with GRC because a wildcard is used at the end.

![](<../.gitbook/assets/image (72).png>)

**Note:**\
****Awareness is critical here, a misconfiguration here means that certain threats might not get reported to SIEM.\
For example if you added a user to this allow list that should not be allowed to perform user administration. The system will then not report the threat to SIEM and will only see this as an event.
