---
description: This page explains the scope and policy rules
---

# Configuring policy settings

​For the scope dropdown menu, you may select how you would like to apply this policy.

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-Mi7S7PK2B4qxyBrzXwx%2Fuploads%2FcwJLou2uKIDnfvjMI0xO%2Fimage.png?alt=media\&token=e0e9274d-2125-43be-b966-0554be422675)

* Selecting All systems will apply the policy on all systems configured in Threat Detection solution
* Select Single System to just apply to 1 system, if you have created multiple systems for the same actual system in Threat Detection, do notice that this policy will only be applied to that particular system selected.
* Select System Role to apply the policy to any systems with a specific role

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

