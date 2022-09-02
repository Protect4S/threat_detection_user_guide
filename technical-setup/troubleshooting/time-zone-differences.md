# Time zone differences

In case you are facing time zone related differences or inconsistency, the following transactions and programs helps you troubleshoot. At least make sure that the timezone defines in transaction STZAC matches the same timezone as defined on your Operating System.

#### Time zone reports/programs:

* **tzcusthelp** - Reports to troubleshoot time zone issues like different time zone on the OS
* **rsbdtime** - Compare system, database and OS time
* **tzonecheck** - Check time zone consistency for any client (input the client in the report)

#### Time zone transactions:

* **STZAD** - Display current system and default user time zone
* **STZAC** - Edit current system and default user time zone

#### Notes:

* [161837 - Manual change from winter to summer time](https://launchpad.support.sap.com/#/notes/161837)
* [481835 - Analyzing the time zone settings](https://launchpad.support.sap.com/#/notes/481835)
* [1428174 - Nonsensical date specifications in the central syslog](https://launchpad.support.sap.com/#/notes/1428174)

\
Indirectly related note:

* [926290 - SWNCCOLL: SAP workload NW collector collects no data](https://launchpad.support.sap.com/#/notes/926290)
