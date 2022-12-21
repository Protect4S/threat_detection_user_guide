---
description: RFC Gateway Log archiving
---

# RFC Gateway Log

The gateway log is stored in a file located in the work directory of each SAP instance. Although we cannot provide specific recommendations for each customer situation, we can provide some general guidelines:

1. Data that is not created, does not need to be archived so decide carefully what events to log.&#x20;
2. You can archive audit log events older than 3 days. Archiving in this case means to still have it available offline for forensic purposes, so don't delete the data directly after 3 days, instead you can copy the files to a central storage facility.
3. If you store the SAL events in the **Filesystem**, SAP describes some general recommendations in SAP note [2191612 ](https://launchpad.support.sap.com/#/notes/2191612)in section 73:

There is no tool support from SAP for the external storage of RFC Gateway log files.&#x20;
