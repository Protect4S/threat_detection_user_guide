# Configuring policies

The use case policies can be configured to avoid false-positives but can also be used to add more customer specific Threat values. No SAP landscape is the same and customers have specific naming conventions for users, specific configurations and setup of the landscape. Via the policies you can finetune the use cases.

After installation of Protect4S TD it is important to tune the policies to reflect your specific situation. For each use case there are [recommendations](../recommendations/) for finetuning,&#x20;

Any Use Case policy change requires you to first make a copy to your own version.

The policies shipped by Protect4S cannot be deleted, should you however find a specific Threat Value unnecessary or unfit for your situation, you can deactivate it. This is also done in your own policy version as it is prioritised higher

### Configuring policies

The policies are indicated with colors. Fields with a red background are used to specifiy the Threat values. These are the values that triggers a Threat in the respective use case. Fields with a green background are exceptions to the Threat Value that can be used for example to create a Threat in case a specific transaction is called, except for user XYZ.

Only Use Cases that have Threat values have an additional field, named Threat Value.

Customers can use the pre-delivered content and extend that with additional Threat Values relevant for their own situation.&#x20;

To configure new policies, a few examples are shown below:

#### Use Case with no known Threat Value

For use case S-000170-01 (User creation outside IAM\_CUA).&#x20;

Whether you company makes use of CUA, IAM, or neither, you will want to avoid false positives being reported. Add the users permitted for this activity in the policy list.

The policy can be used to add users to the exception list to avoid false positives. In the case of this particular use case, users that are allowed to create users, e.g. via Central User Administration or IDM solutions can be added here. Often customers use a fixed username(s) for these kind of systems that is used also in RFC connections for example. This use case detects any users that are creating users, adding users to the policy exempts them.&#x20;

To configure, the first step is to duplicate the Use Case Policy to your own version. Any non standard policy is appears as: '**Default: No**'.

Below you can see an example where values are already defined for CUAADM and any user that starts with GRC because a wildcard is used at the end.&#x20;

Notice be cautions when you are using wildcard.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Value list</p></figcaption></figure>

If you enter the policy in edit mode, you can change or add values of the policy, in our example, we have changed the value "CUAADM" to "CUAADMINISTRATOR".

<figure><img src="../../.gitbook/assets/image (8) (2).png" alt=""><figcaption><p>Editing policy</p></figcaption></figure>

To add values in the policy, while in edit mode; click on the Create button. A new line will appear where you can enter the value you wish to add.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Adding new policy to a Use Case</p></figcaption></figure>

Click on Save to commit your changes at the lower right corner. ![](<../../.gitbook/assets/image (33).png>)

To remove a policy value, simply enter edit mode, select the rule you wish to remove and click on delete. The below screenshot we will remove the rule we just created.

<figure><img src="../../.gitbook/assets/image (77).png" alt=""><figcaption><p>Deleting a policy</p></figcaption></figure>

To finalize, click on Save to commit your changes at the lower right corner. ![](<../../.gitbook/assets/image (33).png>)

Should you want to keep the policy and only want to temporary turn off, click the checkbox of the deactivate to deactivate without deleting. Additionally you can use the comment field to explain why it was deactivated.

#### Use Case with known Threat Value

Use cases with known threat value have a column named "Threat Value". This column has a red background color for easier indication.

<figure><img src="../../.gitbook/assets/image (1) (2).png" alt=""><figcaption><p>Use Case with Threat values</p></figcaption></figure>

#### Handling of multiple same Threat Value

If there are duplicate Threat value, the flow of handling will be an AND situation.

See picture below which illustrates it:

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Multiple entries with same Threat Value</p></figcaption></figure>
