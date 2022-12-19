---
description: Use Case Selection configuration
---

# Use Case Selection

If you have been granted the security configurator role or the administrator role, you can access the "Use Case Selection" Fiori Tile. Please visit [this](system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations.

![Use case Selection Configuration Fiori Application](<../.gitbook/assets/image (63) (1) (1) (1) (1).png>)

The Use Case Selection application allows you to define what use cases you want to activate for each systems. It is possible that in specific cases you do not need or want specific use cases to be active for a specific system. You may switch the use cases On or Off by clicking on "Set Inactive" to Deactivate or "Set active" to Activate them. By default all use cases will be activated upon adding the system in Threat Detection solution. To view the specific details about any use case, the "Use Case Information" application can be used for this purpose. More information regarding this application can be found [here](../application-usage/use-case-information.md).

### Using the Use Case Selection

Upon opening this Fiori application, you will get a screen like below:

![Use Case Selection overview](<../.gitbook/assets/image (76) (1).png>)

This is a list of all the use cases that are applicable for the systems in the Protect4S Threat Detection Solution. On the left you see a colored bar. <mark style="color:green;">**Green**</mark> means that the use case is active for that particular system, <mark style="color:red;">**Red**</mark> means it is not active for that system.

By clicking on a specific line you can see details about the use case and the system it belongs to:&#x20;

![Use Case settings](<../.gitbook/assets/image (61) (1) (1).png>)

On the top right you can set the use case to _**inactive**_ to disable the use case so that this won't be checked for this particular system or switch it back to active.

**Note**: Not all use cases are applicable for all system types, for example Use Case S-000120-1 (ABAP debugging) is only applicable for system role types: "Acceptance / QA / Test", "Pre-production" and "Pre-production". \
More information can be found for each Use Case under the Use Case Information application.
