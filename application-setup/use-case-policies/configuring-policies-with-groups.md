---
description: This page explains how to define Use Case Policy with groups.
---

# !Configuring policies with groups

In order to make use of a group you first need to have created a group.

The details are explained [here](../group-application.md).



We will be re-using the PRD\_GROUP we created in our example shown earlier.

<figure><img src="../../.gitbook/assets/image (1) (6).png" alt=""><figcaption><p>System group</p></figcaption></figure>

__

Depending on what kind of group you have created, you can use that group for the particular group exemption. You cannot use a group with type Hosts or User Names for System for example.

To use a group in the Policy, simply enter the group name for the corresponding Threat you would like to exempt, In our example:

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>Use Case policy edit</p></figcaption></figure>

Only 1 group can be assigned per Threat, But should you have multiple groups, you can define different groups per Threat, should you wish to do so.
