---
description: Creating and using groups to simplify TD usage
---

# !Group application



<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Group configuration application</p></figcaption></figure>

A group is a collection of values which can be used to group to assign a set of users or hosts or clients or systems together. Using a group simplifies and ease the administration work. Depending on the situation and purpose; it might be easier to use a group Instead of configuring and modifying policies separately for similar set of systems for example.

### Characteristic

Group type User Names, Hosts are free input. Client is limited the only 3 numbers per entry.\
Each entry stands for 1 value. Entering multiple entries in one row results in the system searching for that specific value that is likely non-existent.

### Group application usage

Upon opening the application, you have the option to create various types of Groups to simplify the  policy configuration so that you can create your own group and reuse them later.\
The number on the Fiori application tile indicates how many groups exist.

To create a group, click on create on the initial screen.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Creating a group figure 1</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption><p>Creating a group figure 2</p></figcaption></figure>

There are 3 attributes to be defined in this screen.



| Attribute:  | Description attribute:                                                                                                 |
| ----------- | ---------------------------------------------------------------------------------------------------------------------- |
| Group type  | Define the type of group here, depending on what is chosen, the group will have different characteristic for its usage |
| Group ID    | Define the technical name here, only numeric alphabet and underscores are allowed, space is not allowed                |
| Description | Description field you can use to provide some more details about the group                                             |

To create a new group in this application, the first step is to define the group type. The type affects how the Group will be used in the solution. For Instance Upon searching for a System group, any User Name group will not appear.



| Group type | Description of the type:                                                                    |
| ---------- | ------------------------------------------------------------------------------------------- |
| Clients    | List of  clients can be defined here, only used for ABAP systems                            |
| Hosts      | Terminal of the remote system                                                               |
| Systems    | P4S System ID, here you define the System ID's known in Protect4S Threat Detection solution |
| User Names | List of usernames that can be defined here                                                  |

In this initial screen you first have to define what kind of group you would like to create.&#x20;



<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption><p>Dropdown menu for Group Type</p></figcaption></figure>

