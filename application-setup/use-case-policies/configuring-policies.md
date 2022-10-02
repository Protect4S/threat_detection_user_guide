# Configuring Use Case Policies

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

If your company makes use of CUA / IAM, or even when you don't, you likely have a few user-accounts that are responsible for the creation of SAP users. This can be dialog users from user administrators or rfc users that are used in RFC connections to remotely create SAP users from a central place. These users should be added to the use case policy since otherwise they would trigger a Threat when a legitimate users is created by those users.&#x20;

To configure, the first step is to duplicate the Use Case Policy to your own version. Any non standard policy appears as: '**Default: No**'. Below you can see an example where values are already defined for user CUAADM and any user that starts with 'GRC' because a wildcard is used at the end.&#x20;



<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Value list</p></figcaption></figure>

If you enter the policy in edit mode, you can change or add values of the policy, in our example, we have changed the value "CUAADM" to "CUAADMINISTRATOR".

<figure><img src="../../.gitbook/assets/image (8) (2).png" alt=""><figcaption><p>Editing policy</p></figcaption></figure>

To add values in the policy, while in edit mode; click on the Create button. A new line will appear where you can enter the value you wish to add.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Adding new policy to a Use Case</p></figcaption></figure>

Click on Save to commit your changes at the lower right corner. ![](<../../.gitbook/assets/image (33).png>)

To remove a policy value, simply enter edit mode, select the rule you wish to remove and click on delete. The below screenshot we will remove the rule we just created.

<figure><img src="../../.gitbook/assets/image (77).png" alt=""><figcaption><p>Deleting a policy</p></figcaption></figure>

To finalize, click on Save to commit your changes at the lower right corner. ![](<../../.gitbook/assets/image (33).png>)

Should you want to keep the policy record and only want to temporary turn it off, deactivate the checkbox in front of the line to deactivate without deleting. Additionally you can use the comment field to explain why it was deactivated.

For more information on the different fields see [this chapter.](use-case-policy-attributes.md)

#### Use Case with known Threat Value

Use cases with known Threat Values have a column named "Threat Value". This column has a red background color for easier indication and specifies the specific value that triggers a Threat.

<figure><img src="../../.gitbook/assets/image (1) (2).png" alt=""><figcaption><p>Use Case with Threat values</p></figcaption></figure>

The creation and editing of these lines work the same as described above, with the exception that Threat Values need to be provided. In the above screenshot you can specify critical ABAP program names that when executed should trigger an alert (with taking into account possible exceptions). When duplicating a use case policy for a specific scope, if there are default values these will be copied. You can de-activate those if unwanted and extend the use case policy with your own Threat Values that should trigger a threat.

Many exception fields allow multiple values, these should be provided comma separated. See [this page](use-case-policy-attributes.md#threat-value-attributes) for details.

#### Handling of multiple same Threat Value

Threat Values on different lines are processed by the framework as seperate lines in an "OR" relation. Values for exceptions within the same line are processed in an "AND" relation. So if you specify e.g. that transaction ABC is a threat and you specify a USER XYX and a client 000 then only a Threat will be created when transaction ABC is not started by user XYZ in client 000 specifically. When transaction ABC is started by user XYZ in client 999 then a Threat IS created.&#x20;

See picture below which illustrates this:

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Multiple entries with same Threat Value</p></figcaption></figure>
