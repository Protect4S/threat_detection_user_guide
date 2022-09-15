---
description: Use Case Policy configuration
---

# Use Case Policies

If you have been granted the security configurator role or the administrator role, you can access the Use Case Policy Fiori tile. Please visit [this](../system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Use Case Policy Configuration</p></figcaption></figure>

In this application you can configure use cases for example to minimise false positives.&#x20;

No SAP landscape is the same and use cases often need some tweaking and tuning in order to be effective, to limit false positives and add specific data for your situation. All fields are wildcard-enabled and you can use the hash symbol (#) to escape characters.

See note [574914](https://launchpad.support.sap.com/#/notes/574914) and [2488648 ](https://launchpad.support.sap.com/#/notes/0002488648)for details. For example if you want to use the specific value "SAP\*" to address the emergency user in a policy you can use the value "SAP#\*".

If you add values to the exception list, then no Threat will be created. In the next chapter, few list of available attributes are explained.
