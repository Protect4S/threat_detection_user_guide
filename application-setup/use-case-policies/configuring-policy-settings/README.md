---
description: This page explains the scope and policy rules
---

# !Configuring policy settings

​The policies are used to finetune the use cases and to prevent false positives. In addition custom entries can be added.

### Policy configuration

When opening the Use Case Policy application, the following screen shows the available policies:

<figure><img src="../../../.gitbook/assets/image (1) (3).png" alt=""><figcaption><p>Use Case Policies application</p></figcaption></figure>

When selecting a specific policy you can see the details such as the scope, description of the use case and several other attributes of the policy (see [this page](../../allow-deny-policy/) for details).

<figure><img src="../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>Use Case Policy details</p></figcaption></figure>

### Hierarchy of the scope

With each Use Case you configure it for your specific needs and requirements.\
This is mainly done via the scope.&#x20;

The following is an overview of the hierarchy along with its rank:

| Rank | Scope         |
| :--: | ------------- |
|   1  | Single System |
|   2  | System group  |
|   3  | System role   |
|   4  | All System    |

* Select **Single System** to just apply to one system, if you have created multiple systems for the same actual system in Threat Detection, do notice that this policy will only be applied to that particular system selected.
* Select **Systems group** to apply the policy to all systems defined in the group application. The group type of the group _must_ be System.
* Select **System Role** to apply the policy to any systems with a specific role, like e.g. only Productive systems.
* Select **All systems** to apply the policy on all systems configured in Threat Detection solution

### **Attribute legend:**

Below is a list of attributes that is shown for each Use Case Policy.

| Attribute name:        | Description of the attribute:                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Use Case ID            | The unique Use Case identifier number. Use Case policies are linked with each other.                                                                                                                                                                                                                                                                                                                                                                       |
| Default                | Indicates whether this policy is the initial shipped or not.                                                                                                                                                                                                                                                                                                                                                                                               |
| Threat Value Type      | Indicates type of threat the Use Case detects.                                                                                                                                                                                                                                                                                                                                                                                                             |
| Use Case Description   | Human readable description of the use case.                                                                                                                                                                                                                                                                                                                                                                                                                |
| Policy Description     | Human readable description of the policy.                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Additional Description | <p>As the description is fixed in our solution it cannot be changed. However with this extra field customers can specify own description if needed.<br><br>Depending on user preferences, this field can be adapted in your View for easier readability.</p>                                                                                                                                                                                               |
| Scope                  | Type of systems this policy applies to. Possible values are: All Systems, System Role, System Group & Single System.                                                                                                                                                                                                                                                                                                                                       |
| Case Sensitive         | Indicates whether the values entered are Case sensitive or not. For example, Function Module related Use Cases are case sensitive.                                                                                                                                                                                                                                                                                                                         |
| Wildcard Enabled       | <p>By default value list which is the policy are all wildcard symbol (asterisk) enabled. </p><p></p><p>All fields are wildcard-enabled. should you want to monitor something that includes a special character, you can use the SAP standard hash escape character (#), see note <a href="https://launchpad.support.sap.com/#/notes/0000574914">574914</a> and <a href="https://launchpad.support.sap.com/#/notes/0002488648">2488648 </a>for details.</p> |
| Risk-Enabled           | Indicates whether the risk field is included along.                                                                                                                                                                                                                                                                                                                                                                                                        |



### Threat value attributes

Below is a list of attributes available as part of the Threat Value section.

| Threat value attribute:  | Description:                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Active                   | Use this option to activate or deactivate Threat values. The Threat Values we have pre-defined cannot be removed. You can use this option to deactivate instead.                                                                                                                                                                                                                                                                                                     |
| Threat value             | The Value that triggers the Use Case to send alert. For some use cases any value is considered a risk. Because the threat value is unknow this field won't be shown. E.g. you cannot tell upfront whom will be debugging in your system.                                                                                                                                                                                                                             |
| Risk                     | If the Use Case is Risk Enabled, this field gets displayed and you can define for each Threat a risk. This will be used to indicate the risk in threat that also gets send to SIEM.                                                                                                                                                                                                                                                                                  |
| Client Exception         | Define a SAP system client for a threat value exempted for a systems/system role/system group or specific single system. The value here are single values and can be comma separated to exempt multiple clients in one line.                                                                                                                                                                                                                                         |
| Client Exception Group   | A group of clients defined in the Group application, this can be used to exclude a threat value for multiple clients at once.                                                                                                                                                                                                                                                                                                                                        |
| System                   | Define a system for a threat exempted for systems/system role/system group or a specific single system You can enter here the SAP SID or you can enter the TD system number with bracket. The value here are single values and can be comma separated to exempt multiple clients in one line.                                                                                                                                                                        |
| System Exception Group   | A group of systems defined in the Group application, this can be used to exclude a threat value for multiple systems at once.                                                                                                                                                                                                                                                                                                                                        |
| Host Exception           | Define a host/terminal for a threat exempted for systems/system role/system group or a specific single system. The value here can be either hostname, FQDN or ip address. The exempted host must correspond to what is shown in the audit log or gateway log. Wildcard can be used to define multiple hostnames. IP range however cannot be defined with hyphen. The value here are single values and can be comma separated to exempt multiple clients in one line. |
| Host Exception Group     | A group of hosts/terminals defined in the Group application, this can be used to exclude a threat value for multiple hosts/terminals at once.                                                                                                                                                                                                                                                                                                                        |
| Username Exception       | Define a user to exempt for a for a threat specific for systems/system role/system group or a specific single system. The value here are single values and can be comma separated to exempt multiple clients in one line.                                                                                                                                                                                                                                            |
| Username Exception Group | A group of users defined in the Group application, this can be used to exclude a threat value for multiple users at once.                                                                                                                                                                                                                                                                                                                                            |
| Comment                  | This field can be used to add additional information about the exception.                                                                                                                                                                                                                                                                                                                                                                                            |

### Risk value

The risk value per threat can be configured and changed. This can be used in your SIEM solution to apply certain rules you want there. If there are multiple entries with the same Threat Value, the risk can only be defined for the first threat.

### Types of Policies

There are two kind of Use Case policy.

1. Use Case with no known Threat Value
   * Any Policy that considers everything to be a threat does not have a Threat Value, for example debugging detection Use Case.
2. Use Case with known Threats that can be pre-defined
   * Policies with known Threats such as certain table or transactions have a Threat Value in the Use Case. These can be recognized with a red column which stands for Threat Value.

### Adjusting the policy&#x20;

The Use Case policies can be configured to avoid false-positives but also add more customer specific checks of the Threats in a SAP landscape. No SAP landscape is the same and customers have specific naming conventions for users, specific configurations and setup of the landscape. Via the policies you can finetune and drill down the specific checks.

After installation of Protect4S TD it is therefore important to tune the policies to reflect your specific situation. For each use case there are [recommendations](../../recommendations/) for finetuning,&#x20;

Any Use Case policy change requires you to first make a copy to your own version.

The policies shipped by us cannot be deleted, should you however find a check unnecessary or unfit for your situation, you can deactivate it. This is also done in your own policy version as it is prioritized higher
