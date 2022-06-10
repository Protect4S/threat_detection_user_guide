# HTTPURLLOC table

The HTTPURLLOC table is used to reroute HTTP(S) traffic based on the used URL's. For example this was used in the case of the SAP Solution Manager or other dual stacks in the past. In case you use the HTTPURLLOC table to reroute specific HTTP(S) requests, make sure to route the /sap/bc/ui5\_ui5/tdwo/\* URL's to the ABAP stack and port of the Central Protect4S TD system. Otherwise traffic might end up on a wrong stack or port.

A valid entry in the table specifically might look like this:

![](<../../.gitbook/assets/image (74) (1).png>)

Where the PORT (443 in this case) is the ABAP port as defined in transaction SMICM --> Services and the HOST is the hostname of the Protect4S system.

**Make sure to set the SORT KEY field to a low value so this entry will have priority over other entries.**
