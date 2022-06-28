---
description: This page explains the scope and policy rules
---

# Configuring policy settings

​The Allow / Deny policies are there to finetune the use cases and to prevent false positives.&#x20;

### Policy configuration

When opening the Allow / Deny Policy application, the following screen shows the available policies:

![Allow / Deny Polices list](<../../.gitbook/assets/image (31) (1).png>)

When selecting a specific policy you can see the details such as the scope they apply to, the use cases they are linked to and several other attributes of the policy (see [this page](./) for details).

![Policy details](<../../.gitbook/assets/image (71).png>)

### Adjusting the policy&#x20;

The Allow / Deny policies allow modifications to better detect Threats in a SAP landscape. No SAP landscape is the same and customers have specific naming conventions for users, specific configurations and setup of the landscape. Via the policies you can finetune the details to limit false positives. After installation of Protect4S TD it is therefore important to tune the policies to reflect your specific situation. For each use case there are [recommendations](../recommendations/) for finetuning, find an example below:&#x20;

Below you can see that the current values are already defined for CUAADM and any user that starts with GRC because a wildcard is used at the end.

![Policy values](<../../.gitbook/assets/image (63) (1) (1).png>)

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

