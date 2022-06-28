# Custom Allow / Deny Policy

You can copy allow deny policies to your own version and assign this particular allow deny policy to just 1 system or whole landscape.

Notice if you choose to assign the Allow / Deny Policy to just one system whilst you have created more than 1 system to the same system in the Threat Detection Solution you will have to create another additional custom allow / deny policy and adapt the values where needed in the policy should you wish to adapt the same values, you may just create a copy of the custom policy you created. Do notice that they will have to be adjusted individually should there a need of change.



**To copy a policy.**

Select the policy you wish to copy in the Allow / Deny application

![Selecting a policy](<../../.gitbook/assets/image (57).png>)

Click on copy. ![](<../../.gitbook/assets/image (65) (1).png>)\


Click on Create before proceeding then click on the newly created policy to adapt your own settings in in the policy as Fiori keeps the initial selected policy selected making you edit the actual source of the policy in certain situation which is a bug in Fiori. ![](<../../.gitbook/assets/image (38).png>)

After creation, click on Edit to proceed with your desired changes. ![](<../../.gitbook/assets/image (54).png>)

Policies can also have a specific scope to make it applicable for example for all systems, just the systems with a specific role or a single SAP system. From the scope dropdown menu, you may select how you would like to apply a specific policy.

![](<../../.gitbook/assets/image (59).png>)

* Selecting **All systems** will apply the policy on all systems configured in Threat Detection solution
* Select **Single System** to just apply to 1 system, if you have created multiple systems for the same actual system in Threat Detection, do notice that this policy will only be applied to that particular system selected.
* Select **System Role** to apply the policy to any systems with a specific role, like e.g. only Productive systems.



To configure policy values policy go in edit mode the click on Create to create the policy rules for your desired policy you wish to configure. ![](<../../.gitbook/assets/image (66).png>)

Then click save. ![](<../../.gitbook/assets/image (72).png>)

Should the list get very long and you would like to see what is configured, you can also export the list of rules by clicking on the export to Excel button
