---
description: This page explains how to define Use Case Policy with groups.
---

# !Configuring policies with groups

In order to make use of a group you first need to have created a group.

The details are explained [here](../../group-application.md).



We will be re-using the PRD\_GROUP we created in our example shown earlier.

<figure><img src="../../../.gitbook/assets/image (1) (6).png" alt=""><figcaption><p>System group</p></figcaption></figure>

Depending on what kind of group you have created, you can use that group for the particular group exemption. You cannot use a group with type Hosts or User Names for System for example.

To use a group in the Policy, simply enter the group name for the corresponding Threat you would like to exempt, In our example:

<figure><img src="../../../.gitbook/assets/image (1) (7).png" alt=""><figcaption><p>Use Case policy edit</p></figcaption></figure>

Only 1 group can be assigned per Threat, should you have multiple groups, you can define different groups per Threat, should you wish to do so.

#### Combining standard exceptions & exception groups

The standard exceptions can be defined and mixed with groups. The exception handling is an AND operator. Although there can be overlaps. But it is recommended to use groups instead if certain value are always with one another. This avoids some repetitive configuration and in the end it will be easier administration via groups.

#### Deleting a group

If a group is used in certain Policy, the group cannot be deleted. The delete option will be greyed-out.

Should you however delete a system that has been assigned in one or more groups. The group will be updated. The system that was in the group will be removed automatically as well, because we expect our users to have a definitive reason to delete a system.

