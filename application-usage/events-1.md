---
description: Health checks
---

# Health checks

This functionality performs a health check on critical functions to ensure a proper functioning of Protect4S Threat Detection. There will be two types of health checks:

* Monitored systems health checks
* Protect4S central system health checks

This functionality checks the connectivity for Data Sources and System connections and the execution of needed Background jobs e.g. By default the output of the health check is displayed in the Messages application. You can filter in this application on the category "Health Check" to display these messages:

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>



If needed, you can choose to also forward messages in this category to SIEM, this can be set per system in the System Application by setting the flag "Create Threat" to Yes.

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>
