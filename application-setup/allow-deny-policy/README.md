---
description: Allow and Deny policy configuration
---

# Allow / Deny Policy

![Allow / Deny Policy configuration](<../../.gitbook/assets/image (40).png>)

If you have the been granted to security configurator role or the administrator role, you can access "Allow / Deny Policy configurator" Fiori Tile. Please visit [this](../systems-in-threat-detection/system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations.

The allow and deny policies are one of the configurations is one of the most critical step to configure, you may configure the policy per your needs per system.

****\
**Note:**\
****Awareness is critical here, a misconfiguration here means that certain threats might not get reported to SIEM.\
For example if you added a user to this allow list that should not be allowed to perform user administration. The system will then not report the threat to SIEM and will only see this as an event.



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
