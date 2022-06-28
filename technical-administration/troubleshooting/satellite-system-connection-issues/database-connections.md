# Database connections

For all database types, errors are written to the work process trace files (**dev\_w\***) in the SAP work directory. Consult these files for additional information and also transaction SM21 might provide some further details.

In case of SSL certificate errors for the Hana Database, specifically when you use self-signed certificates, you might add the SSL option "_**sslvalidatecertificate=false"**_ in the Encryption parameters when creating the DB connection. This is not recommended but might apply for testing and troubleshooting purposes.

In case the Central Protect4S system has another Database type as the monitored SAP system, make sure to install the proper [Database client libraries](../../../application-setup/troubleshooting/heterogeneous-db-connections-and-installing-db-libraries/).
