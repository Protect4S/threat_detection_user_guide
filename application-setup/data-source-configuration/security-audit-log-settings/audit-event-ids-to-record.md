---
description: List of minimum audit event IDs that needs to be recorded vs recommended
---

# Audit Event IDs to record

Logging too many events can result in large log files in SAL. If disk space is not an issue and regulations or internal policies requite it; you may activate all events, but do notice that in some releases the transaction SM19 can only have a limited set of Event IDs to be recorded. For the working of Protect4S TD not all events need to be activated. We have two options:\


**Option 1**: In order to provide a broad, future proof solution, customers can activate the event recording listed in the table overview below at option 2, combined with the generic recommendations [shared by SAP](https://answers.sap.com/questions/9791383/recommended-settings-for-the-security-audit-log-sm.html).&#x20;

**Option 2**: For a minimum of events selected, customers can select mentioned events (See the overview table below at option 2). Keep in mind that this might need to be extended with future released use cases

### Option 1: Recommendation by SAP

Maintain static filters to:

* Log all actions by the standard SAP\* user in all clients
* Logons and transaction starts by the DDIC user in all clients
* Severe and critical events for all audit classes and users in all clients
* Log the Event ID's shown **in the below overview at option 2**, plus the following Event IDs **AUO, AUP, AUQ, AUZ, BU4, BU5, BU6, BU7, BU9, BUA, BUB, BUC, BUH, CUQ, CUR, CUS, CUT, DU5, DUI, DUJ, DUK**
* If you have yet to remove the Early Watch client (066), also create a filter to monitor events for all audit classes and users in client 066\
  For 7.50 or higher make sure that the recording target is set to Record in File System or Record in Database and File System

### Option 2: Minimum recording

#### Event IDs overview

This is the list of the _**minimum**_ required Event IDs that is needed to be activated for the use cases to work properly. This overview will be updated whenever new use cases are released that requires new events to be monitored for our Threat Detection solution.&#x20;

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

