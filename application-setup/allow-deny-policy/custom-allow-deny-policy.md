# Custom Allow / Deny Policy

If you want to change the scope of a policy, copy original policy to your own version and change the scope for this particular policy to just 1 system, all systems with a specific system role or the whole landscape.

**Copying a policy**

Select the policy you wish to copy in the Allow / Deny application

![Selecting a policy](<../../.gitbook/assets/image (57).png>)

Click on copy ![](<../../.gitbook/assets/image (65) (1).png>)and edit the attributes like scope or values for this policy. Policies can have a specific scope to make it applicable for example for all systems, just the systems with a specific role or a single SAP system. From the scope dropdown menu, you may select how you would like to apply a specific policy.

![](<../../.gitbook/assets/image (59).png>)

* Selecting **All systems** will apply the policy on all systems configured in Threat Detection solution
* Select **Single System** to just apply to 1 system, if you have created multiple systems for the same actual system in Threat Detection, do notice that this policy will only be applied to that particular system selected.
* Select **System Role** to apply the policy to any systems with a specific role, like e.g. only Productive systems.

**Note: If a specific system falls outside the scope of a custom policy; then the default policy will apply.**

