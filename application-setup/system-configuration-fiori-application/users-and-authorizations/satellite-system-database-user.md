---
description: Database user in the satellite systems
---

# Satellite System Database User

Database connections are not mandatory, but in order to get the most out of Protect4S and to be able to use the use cases on Database level, it is needed to create a database connection using the System Connection wizard. For this connection you will need to create a database user in the database of the satellite system. If you connect to a database type other than the database type of the Central system, you must install Database libraries for that Database. See [this chapter](../../troubleshooting/heterogeneous-db-connections-and-installing-db-libraries/) for more information.

✔ If you choose not to create a database connection this implies that specific database use cases might fail.

✔ If the database connection is not available, then in some cases a fallback mechanism is used to retrieve database specific information. For example for ABAP systems a RFC is used for MSSQL and MAXDB. For HANA a fallback is implemented via the OS command HDBCLI. This will only work if the SAPControl connection user is the \<sid>adm OS user and can access the hdbuserstore.

Current status: Use cases on DB level are not yet present so DB users are not yet needed.

