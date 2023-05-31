---
description: Satellite system settings
---

# Message Server log

The Message Server log in SAP systems is used to store runtime information related to the Message Server process. The Message Server log is activated after installation by default. The status of the Message Server process can be monitored with transaction SMMS.

The logging level is controlled by parameter "**rdisp/TRACE**" and is by default set to value "**1**" which is the minimum required value for the Message Server to be used as a data source. The default file format is "**dev\_ms**". This format is also a required setting.
