---
description: This page explains the scope and policy rules
---

# !Configuring policy settings

​The policies are there to finetune the use cases and to prevent false positives.&#x20;

### Policy configuration

When opening the Use Case Policy application, the following screen shows the available policies:

<figure><img src="../../.gitbook/assets/image (1) (3).png" alt=""><figcaption><p>Use Case Policies application</p></figcaption></figure>

When selecting a specific policy you can see the details such as the scope and description of the use case and several other attributes of the policy (see [this page](./) for details).

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Use Case Policy details</p></figcaption></figure>

### Adjusting the policy&#x20;

The Use Case policies can be configured to avoid false-positives but also add more customer specific checks of the Threats in a SAP landscape. No SAP landscape is the same and customers have specific naming conventions for users, specific configurations and setup of the landscape. Via the policies you can finetune and drill down the specific checks.

After installation of Protect4S TD it is therefore important to tune the policies to reflect your specific situation. For each use case there are [recommendations](../recommendations/) for finetuning, find an example below:&#x20;

For use case S-000170-01 (User creation outside IAM\_CUA).&#x20;

Whether you company makes use of CUA, IAM, or neither, you will want to avoid false positives being reported. Add the users permitted for this activity in the policy list.

The policy can be used to add users to the exception list to avoid false positives. In the case of this particular use case, users that are allowed to create users, e.g. via Central User Administration or IDM solutions can be added here. Often customers use a fixed username(s) for these kind of systems that is used also in RFC connections for example. This use case detects any users that are creating users, adding users to the policy exempts them.&#x20;

To configure, the first step is to duplicate the Use Case Policy to your own version. Any non standard policy is appears as: '**Default: No**'.

Below you can see an example where values are already defined for CUAADM and any user that starts with GRC because a wildcard is used at the end.&#x20;

Notice be cautions when you are using wildcard.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Value list</p></figcaption></figure>

If you enter the policy in edit mode, you can change or add values of the policy, in our example, we have changed the value "CUAADM" to "CUAADMINISTRATOR".

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption><p>Editing policy</p></figcaption></figure>

To add values in the policy, while in edit mode; click on the Create button. A new line will appear where you can enter the value you wish to add.

![Adding a rule in a policy](<../../.gitbook/assets/image (19).png>)

Click on Save to commit your changes at the lower right corner. ![](<../../.gitbook/assets/image (33).png>)

To remove a policy value, simply enter edit mode, select the rule you wish to remove and click on delete. The below screenshot we will remove the rule we just created.

![Removing a rule](<../../.gitbook/assets/image (74).png>)

To finalize, click on Save to commit your changes at the lower right corner. ![](<../../.gitbook/assets/image (33).png>)

