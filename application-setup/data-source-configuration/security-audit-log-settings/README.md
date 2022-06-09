---
description: Satellite system
---

# Security Audit Log Settings



For the systems that is to be worked with Threat Detection Solution. It is important that the Security Audit Logging is turned on statically and in case of multiple application server that this is activated for each additional instances of that system. Using dynamic is temporary and logging will be switched off once the system or a particular application instance is restarted.

* This can be activated in RSAU\_CONFIG or SM19. The latter is obsolete in newer releases and we suggest to use the new application instead.
* As a minimum, the parameter "rsau/enable" needs to be set to be turned on by value 1. This is off by default (0). To confirm the activation, check the parameters set in the system under:
  * RSAU\_CONFIG: Security Audit Log Configuration -> Parameter
  * SM19: In the toolbar -> Environment -> Profile Parameters.
  * Notice if your system have multiple instances, it is best to confirm in the profiles per respective instances. All these related profile parameters cannot be changed dynamically and requires a restart.

Optionally, a different path can be defined for the SAL files as the the log files can take up a lot of space depending on the configuration (e.g. the use case you wish to use and the required Event ID needed, the retention dates of the log files).

The default path is \usr\sap\\\<SID>\\\<INST>\log for Unix and \<drive letter>:\usr\sap\\\<SID>\\\<INST>\log which is not ideal and will cause a lot of unpredictable system behavior once the drive is full.\
Be especially cautions when you are switching on successful events, as these happen often and will result in growth of log file(s). Alternatively has to be scheduled regularly to keep the free disk space steady.

And setting a limit per day to log for example will give an incomplete picture of what is happening, because your satellite system will stop recording once the limit has been reached for the day.

For more details related to the Security Audit Log profile parameters please see the the reference section and configure them as per your company's policy.

References:

[SAP Help: Security Audit Log](https://help.sap.com/docs/SAP\_NETWEAVER\_700/12b9c3746c53101486a59afda7426260/c769bcb7f36611d3a6510000e835363f.html)\
[SAP Blog: Analysis and Recommended Settings of the Security Audit Log](https://blogs.sap.com/2014/12/11/analysis-and-recommended-settings-of-the-security-audit-log-sm19-sm20/)\
[2546993 - Analysis and Recommended Settings of the Security Audit Log (SM19 / SM20)](https://launchpad.support.sap.com/#/notes/2546993)\
