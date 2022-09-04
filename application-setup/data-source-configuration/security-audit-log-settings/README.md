---
description: Satellite system settings
---

# Security Audit Log Settings

The Security Audit Logging (SAL) in SAP ABAP systems is an important resource for security relevant events. It is therefore important that the Security Audit Logging is switched on for all application servers and that the correct events are recorded. The SAL can be activated in transaction RSAU\_CONFIG or SM19. The latter is obsolete in newer releases.

As a minimum, the parameter "**rsau/enable**" needs to be set to value 1 via transaction RZ10. If your system has multiple instances, make sure to activate the parameter for all individual instance profiles or set the parameter in the default profile for system-wide activation. Do confirm that this parameter is **not** set to 0 in the instance profiles, because this will overwrite the parameter value set in the default profile. This parameter cannot be changed dynamically and requires a restart.

Optionally, a different path can be defined for the SAL files as the the log files can take up a lot of space depending on the configuration. The default path is under the \usr\sap\\\<SID>\ directory, which might cause unpredictable system behavior once the drive is full. So make sure to activate only relevant and needed events (see the [next chapter)](audit-event-ids-to-record.md), have enough diskspace available, monitor for full disk or mountpoints and archive files based on your archiving strategy.

Another option in systems with a release higher than 7.5 is to activate in RSAU\_CONFIG both the OS level logging and the Database logging. This might provide options to clear the OS-level logging periodically while retain the events in the Database for reference and analytics purposes: &#x20;

![](<../../../.gitbook/assets/image (1).png>)

For more details related to the Security Audit Log profile parameters please see the the reference section and configure them as per your company's policy.

References:

[SAP Help: Security Audit Log](https://help.sap.com/docs/SAP\_NETWEAVER\_700/12b9c3746c53101486a59afda7426260/c769bcb7f36611d3a6510000e835363f.html)\
[SAP Blog: Analysis and Recommended Settings of the Security Audit Log](https://blogs.sap.com/2014/12/11/analysis-and-recommended-settings-of-the-security-audit-log-sm19-sm20/)\
[2546993 - Analysis and Recommended Settings of the Security Audit Log (SM19 / SM20)](https://launchpad.support.sap.com/#/notes/2546993)
