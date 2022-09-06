# !Examples of configuring policies

### Configuring policies

There are two kind of Use Case policy.

1. Use Case with no known Threat Value
2. Use Case with known Threats that can be pre-defined



\---

For configuring new policies, find an example below:&#x20;

For use case S-000170-01 (User creation outside IAM\_CUA).&#x20;

Whether you company makes use of CUA, IAM, or neither, you will want to avoid false positives being reported. Add the users permitted for this activity in the policy list.

The policy can be used to add users to the exception list to avoid false positives. In the case of this particular use case, users that are allowed to create users, e.g. via Central User Administration or IDM solutions can be added here. Often customers use a fixed username(s) for these kind of systems that is used also in RFC connections for example. This use case detects any users that are creating users, adding users to the policy exempts them.&#x20;

To configure, the first step is to duplicate the Use Case Policy to your own version. Any non standard policy is appears as: '**Default: No**'.

Below you can see an example where values are already defined for CUAADM and any user that starts with GRC because a wildcard is used at the end.&#x20;

Notice be cautions when you are using wildcard.

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Value list</p></figcaption></figure>

If you enter the policy in edit mode, you can change or add values of the policy, in our example, we have changed the value "CUAADM" to "CUAADMINISTRATOR".

<figure><img src="../../../.gitbook/assets/image (8) (2).png" alt=""><figcaption><p>Editing policy</p></figcaption></figure>

To add values in the policy, while in edit mode; click on the Create button. A new line will appear where you can enter the value you wish to add.

<figure><img src="../../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Adding new policy to a Use Case</p></figcaption></figure>

Click on Save to commit your changes at the lower right corner. ![](<../../../.gitbook/assets/image (33).png>)

To remove a policy value, simply enter edit mode, select the rule you wish to remove and click on delete. The below screenshot we will remove the rule we just created.

<figure><img src="../../../.gitbook/assets/image (77).png" alt=""><figcaption><p>Deleting a policy</p></figcaption></figure>

To finalize, click on Save to commit your changes at the lower right corner. ![](<../../../.gitbook/assets/image (33).png>)

Should you want to keep the policy and only want to temporary turn off, click the checkbox of the deactivate to deactivate without deleting. Additionally you can use the comment field to explain why it was deactivated.