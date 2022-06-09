---
description: List of minimum audit event IDs that needs to be recorded vs recommended
---

# Audit Event IDs to record

As mentioned earlier, logging too many events can result in large log files in SAL.\
If disk space is not a subject, you may activate all, but do notice in some releases SM19 can only have a limited set of Event IDs to be recorded.

We have two options for our customers to choose between recording the Event recommended by SAP which includes our minimum requirements or just the minimum needed Events for Threat Detection or proceed with.\
Option 1 is a recommendation by SAP, which may affect large size log files.\
Option 2 is the minimum, avoiding Events to be logged that are not used in Threat Detection but might need to be extended more frequently in the future, depending on the use case we release with future updates.

**Option 1**: In order to provide a more wide future proof solution we propose to activate the Event recording listed in the table overview below combined with the recommendations shared by Frank Buchholz [\[1\]](https://answers.sap.com/questions/9791383/recommended-settings-for-the-security-audit-log-sm.html). The User Master record changes should be selectively activated though as certain Use Case in Threat Detection relies on these.

**Option 2**: Select the minimum amount of needed events (See the overview table below). Keep in mind that this might need to be extended with future released use cases

### Option 1: Recommendation by SAP

Maintain static filters to:

* Log all actions by the standard SAP\* user in all clients
* Logons and transaction starts by the DDIC user in all clients
* Severe and Critical events for all audit classes and users in all clients
* Log the Event ID shown **in the overview**, plus the following Event IDs **AUO, AUP, AUQ, AUZ, BU4, BU5, BU6, BU7, BU9, BUA, BUB, BUC, BUH, CUQ, CUR, CUS, CUT, DU5, DUI, DUJ, DUK**
* If you have yet to remove the Early Watch client (066), also create a filter to monitor events for all audit classes and users in client 066\
  For 7.50 or higher make sure that the recording target is set to Record in File System or Record in Database and File System

### Option 2: Minimum recording

#### Event IDs overview

This is a list of the _**minimum**_\*\* \*\* required Event IDs that is needed to be activated for the use cases to work properly.\
This overview will be updated whenever new Use Cases are released that requires new Events to be monitored for our Threat Detection solution. Thus this list will be updated regularly.

| Event ID: | Description:                                                           |
| --------- | ---------------------------------------------------------------------- |
| AU1       | Logon successful (type=\&A, method=\&C)                                |
| AU2       | Logon failed (reason=\&B, type=\&A, method=\&C)                        |
| AU3       | Transaction \&A Started                                                |
| AU5       | RFC/CPIC logon successful (type=\&A, method=\&C)                       |
| AU6       | RFC/CPIC logon failed, reason=\&B, type=\&A, method=\&C                |
| AU7       | User \&A Created                                                       |
| AU8       | User \&A Deleted                                                       |
| AUF       | Audit: Slot \&A: Class \&B, Severity \&C, User \&D, Client \&E, \&F    |
| AUI       | Audit: Slot \&A Inactive                                               |
| AUJ       | Audit: Active Status Set to &1                                         |
| AUK       | Successful RFC Call \&C (Function Group = \&A)                         |
| AUT       | Authorization/Authorization Profile \&B Changed                        |
| AUU       | Authorization/Authorization Profile \&B Activated                      |
| AUW       | Report \&A Started                                                     |
| AUX       | Start Report \&A Failed (Reason = \&B)                                 |
| AUY       | Download \&A Bytes to File \&C                                         |
| BU1       | Password check failed for user \&B in client \&A                       |
| CUZ       | Generic table access by RFC to \&A with activity \&B                   |
| DU9       | Generic table access call to \&A with activity \&B (auth. check: \&C ) |
| EU1       | System change options changed ( \&A to \&B )                           |
| EU2       | Client \&A settings changed ( \&B )                                    |

_Notice, **Event IDs mentioned separately in the option 1** are **not** listed in the overview because this is not part of our minimum needed Event IDs to cover all the use case we have. Although you may include them._

\_\_

References:

\[1] [SAP Community - Recommended Settings for the Security Audit Log (SM19 / SM20)](https://answers.sap.com/questions/9791383/recommended-settings-for-the-security-audit-log-sm.html)
