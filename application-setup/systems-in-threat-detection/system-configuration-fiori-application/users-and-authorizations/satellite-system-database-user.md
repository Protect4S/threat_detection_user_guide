---
description: Database user in the satellite systems
---

# Satellite system Database user

Database connections are not mandatory for most systems (apart for Java systems and systems running on SAP HANA), but in order to get the most out of Protect4S we recommend to create a database connection using the System connection wizard. For this connection you will need to create a database user in the database of the satellite system. If you connect to a database type other then the database typeof the Central system, you must install Database libraries for that Database. See [this chapter](../../../troubleshooting/heterogeneous-db-connections-and-installing-db-libraries/) for more information.

✔ If you choose not to create a database connection this implies that specific database use cases might fail.

✔ If the database connection is not available then in some cases a fallback mechanism is used to retrieve database specific information. For example for ABAP systems an RFC is used for MSSQL and MAXDB. For HANA a fallback is implemented via the OS command HDBCLI. This will only work if the SAPControl connection user is the \<sid>adm OS user and can access the hdbuserstore.

✔ For Java systems, Database connections are mandatory as data retrieval relies on this connection type.

For now only SAP HANA database users are mandatory, but since the specific use cases are not yet developed you can provide the SAP HANA DB users with only SQL connect rights as a minimum.

