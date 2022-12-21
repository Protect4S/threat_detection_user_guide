---
description: RFC Gateway Log archiving
---

# RFC Gateway Log

The gateway log is stored in a file located in the work directory of each SAP instance. Although we cannot provide specific recommendations for each customer situation, we can provide some general guidelines:

1. Data that is not created, does not need to be archived so decide carefully what events to log.&#x20;
2. You can archive audit log events. The threshold for archiving depends on your guidelines. Archiving in this case means to still have the files available offline for forensic purposes, so don't delete the data directly after 3 days, instead you can move the files to a central storage facility. Make sure that the connection between the files and the source instance remains recognisable in the new folder structure (log files contain no information about the source instance).&#x20;

&#x20;
