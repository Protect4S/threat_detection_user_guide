---
description: Required application user(s)
---

# Satellite SAP Application User

A **dedicated** SAP ABAP user must be created (type System or Service) in all applicable ABAP clients of the satellite systems and given the role **TDWO\_SATELLITE** that is shipped with the Protect4S TD Solution. This user should only be used for the Protect4S Threat Detection solution. This role grants the rights to read data sources like e.g. the Security Audit Log, retrieves technical data, e.g. reads system time, system client settings and does not modify any data. The role can be downloaded from the Protect4S Threat Detection central system using transaction PFCG and uploaded in the satellite system.

Protect4S recommends to create the SAP RFC users as type "System". This prevents misuse of this user via the SAPGUI. Make sure that both the background user in the Protect4S Threat Detection system and the RFC users in the satellite systems have the same date-format settings so that date and time calculations are executed correctly. This must be configured using transaction SU01 under the DEFAULTS tab and set as displayed in the figure below:

<figure><img src="../../../../.gitbook/assets/image (2) (5).png" alt=""><figcaption></figcaption></figure>

This user is used in during the setup of the [connection](../../creating-a-system/setting-up-connections/).
