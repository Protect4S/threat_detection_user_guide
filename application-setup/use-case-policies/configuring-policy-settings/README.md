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
| ---- | ------------- |
| 1    | Single System |
| 2    | System group  |
| 3    | System role   |
| 4    | All System    |

* Select **Single System** to just apply to one system, if you have created multiple systems for the same actual system in Threat Detection, do notice that this policy will only be applied to that particular system selected.
* Select **Systems group** to apply the policy to all systems defined in the group application. The group type of the group _must_ be System.
* Select **System Role** to apply the policy to any systems with a specific role, like e.g. only Productive systems.
* Select **All systems** to apply the policy on all systems configured in Threat Detection solution

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

### Risk value

The risk value per threat can be configured and changed. This can be used in your SIEM solution to apply certain rules you want there. If there are multiple entries with the same Threat Value, the risk can only be defined for the first threat.

