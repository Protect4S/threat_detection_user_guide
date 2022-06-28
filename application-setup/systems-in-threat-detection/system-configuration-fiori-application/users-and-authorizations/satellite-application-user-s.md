---
description: Required application user(s)
---

# Satellite SAP application user

A dedicated SAP ABAP user must be created (type System or Service) in all applicable ABAP clients of the satellite systems and given the role **TDWO\_SATELLITE.** This role is delivered as part of the installation on the Central system. This role grants the rights to read datasources like the Security Audit Log, retrieves technical data, e.g. reads system time, system client settings and does not change any data. The role can be downloaded from the Protect4S Threat Detection central system using transaction PFCG and uploaded in the satellite system.

Protect4S recommends to create the SAP RFC users as type "System". This prevents misuse of this user via the SAPGUI. Make sure that both the background user in the Protect4S Threat Detection system and the RFC users in the satellite systems have the same date-format settings so that date and time calculations are executed correctly. This must be configured using transaction SU01 under the DEFAULTS tab and set as displayed in the figure below:

![Date and Time settings for the manually created RFC users](https://files.gitbook.com/v0/b/gitbook-legacy-files/o/assets%2F-Mee93KW0BtSWNWC0nS9%2F-MhIoDN1X2VnVwIeuzgJ%2F-MhIqhinNsb\_\_LCZuNle%2Fimage.png?alt=media\&token=54fb1975-7e71-486a-8e33-aba4a1b44bb5)

This user is used in during the setup of the [connection](../creating-a-system/setting-up-connections.md).
