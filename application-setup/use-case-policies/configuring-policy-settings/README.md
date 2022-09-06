---
description: This page explains the scope and policy rules
---

# Configuring policy settings

​The policies are used to finetune the use cases and to prevent false positives. In addition custom entries can be added.

### Policy configuration

When opening the Use Case Policy application, the following screen shows the available policies:

<figure><img src="../../../.gitbook/assets/image (1) (3).png" alt=""><figcaption><p>Use Case Policies application</p></figcaption></figure>

When selecting a specific policy you can see the details such as the scope, description of the use case and several other attributes of the policy (see [this page](../../allow-deny-policy/) for details).

<figure><img src="../../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Use Case Policy details</p></figcaption></figure>

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

### Adjusting the policy&#x20;

The Use Case policies can be configured to avoid false-positives but also add more customer specific checks of the Threats in a SAP landscape. No SAP landscape is the same and customers have specific naming conventions for users, specific configurations and setup of the landscape. Via the policies you can finetune and drill down the specific checks.

After installation of Protect4S TD it is therefore important to tune the policies to reflect your specific situation. For each use case there are [recommendations](../../recommendations/) for finetuning,&#x20;

Any Use Case policy change requires you to first make a copy to your own version.

The policies shipped by us cannot be deleted, should you however find a check unnecessary or unfit for your situation, you can deactivate it. This is also done in your own policy version as it is prioritized higher
