---
description: Security Audit Log
---

# Security Audit Log

As the amount of events being stored can grow fast, sooner or later there might be a need to archive the data created by the Security Audit Log. Although we cannot provide specific recommendations for each customer situation, we can provide some general guidelines:

1. Data that is not created, does not need to be archived so decide carefully what events to log. Also see [this chapter](../../application-setup/data-source-configuration/security-audit-log-settings/audit-event-ids-to-record.md).
2. If you store the SAL events in the **Database**, SAP recommends that you archive audit log events older than 3 days. Archiving in this case means to still have it available offline for forensic purposes, so don't delete the data directly after 3 days. See [this SAP documentation](https://help.sap.com/docs/SAP\_NETWEAVER\_AS\_ABAP\_751\_IP/280f016edb8049e998237fcbd80558e7/a9e341f8142a41e59a307dee6904f267.html?version=7.51.13\&locale=en-US) for archiving documentation.
3. If you store the SAL events in the **Filesystem**, SAP describes some general recommendations in SAP note [2191612 ](https://launchpad.support.sap.com/#/notes/2191612)in section 73:

In general, there is no tool support from SAP for the external storage of audit log files. The following technical recommendations apply in order to ensure the legally compliant retention of the files:

**Security Audit Log WITHOUT integrity protection format**

* If you want to delete log files, we recommend that you use transaction RSAU\_ADMIN.
* If log files are to be retained but no longer accessed directly, **move** the log files to a suitable external storage medium using your system platform functions. Make sure that the connection between the files and the source instance remains recognisable in the new folder structure (log files contain no information about the source instance). Make sure that the valid code page for the storage media is identical. This is the only way to read historical log data in full once the files are restored correctly.
* We recommend that you upgrade the system to the correction level of SAP Note 3090362.

**Security Audit Log WITH integrity protection format**

* If you want to delete log files, we recommend that you use transaction RSAU\_ADMIN to do so.
* If log files are to be retained but no longer accessed directly, **copy** the log files to a suitable external storage medium using your system platform functions. Then delete the copied files using transaction RSAU\_ADMIN. Make sure that the connection between the files and the source instance remains recognisable in the new folder structure (log files contain no information about the source instance). Make sure that the valid code page for the storage media is identical. This is the only way to read historical log data in full once the files are restored correctly.
* Use the function for reorganising the file statistics in transaction RSAU\_ADMIN to remove statistics and integration protection information about log files that is no longer required.
* The integrity check is supported only for original log data that remains in the system. However, readability is possible for all files written in log format.
* We recommend that you upgrade the system to the correction level of SAP Note 3090362.
