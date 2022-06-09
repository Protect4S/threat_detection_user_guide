---
description: Required application, database and operating system users
---

# Satellite application user(s)

A dedicated SAP User must be created (type System or Service) in all applicable ABAP clients of the satellite system and provided with the role **TDWO\_SATELLITE.SAP** that is delivered as part of the installation. This role only grants the rights to read SAL, retrieve technical data, e.g. reads system time, system client settings and does not change any data.

**The role must be downloaded from the Protect4S Threat Detection system using transaction PFCG and uploaded in the satellite system.**

Protect4S recommends to create the SAP RFC users as type "System". This prevents misuse of this user via the SAPGUI. For short term assessments also limit the validity period of the user to the period of the assessment. This can be set on the LOGON DATA tab.

Make sure that both the background user in the Protect4S Threat Detection system and the RFC users in the satellite systems have the same date-format settings so that date and time calculations are executed correctly.

This must be configured using transaction SU01 under the DEFAULTS tab and set as displayed in the figure below:&#x20;

![Date and Time settings for the manually created RFC users](https://files.gitbook.com/v0/b/gitbook-legacy-files/o/assets%2F-Mee93KW0BtSWNWC0nS9%2F-MhIoDN1X2VnVwIeuzgJ%2F-MhIqhinNsb\_\_LCZuNle%2Fimage.png?alt=media\&token=54fb1975-7e71-486a-8e33-aba4a1b44bb5)

This user is used in during the setup of the [connection](../creating-a-system/setting-up-connections.md).
