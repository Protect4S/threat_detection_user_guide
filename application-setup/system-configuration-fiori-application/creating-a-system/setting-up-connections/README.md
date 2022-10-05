---
description: Setting up connections to the application, database and operating system
---

# Setting up Connections

As part of [creating the system](../), you need to create connections to the satellite system to be able to detect threats. While editing the system in the System application, press the "Create Connections" button to create connections. In the first step you need to enter mandatory data for at least one ABAP client. This user in the satellite system must have the role "TDWO\_SATELLITE". Notice that the client you enter here will be the default client and the connection to this client needs to work as it is mandatory for Protect4S TD to operate. In the next step you can optionally create connections to the other clients.

![Creating ABAP connection](<../../../../.gitbook/assets/image (51).png>)

![Creating RFCs in the back-end system](<../../../../.gitbook/assets/image (29) (1).png>)

By default the application will detect all available clients and list them and re-use the user that you have provided initially. If you want to use a different user you can change it or you can uncheck the row of the client to skip creating the RFC for that particular client.

**Database connection:**

![Setting up database connection](<../../../../.gitbook/assets/image (14).png>)

The database connections are not mandatory. However activated use cases that rely on the database datasources, require the database connections to function. Otherwise these use cases will not work.

**Operating System connection:**

An Operating System user is not mandatory for ABAP systems, for JAVA systems it is mandatory. Enter here the OS user as described [here](../../users-and-authorizations/operating-system-user.md).

![Connecting to the operating system of the satellite system](<../../../../.gitbook/assets/image (52) (1).png>)

For SAPControl connections with Encryption (SSL), see [here](using-https-for-sapcontrol.md).

![Overview of all the instances where sapcontrol will be used](<../../../../.gitbook/assets/image (25) (1).png>)

Review and confirm the list of all the applications servers **** applicable for your system and in the next screen save the connections.

If you are running the Protect4S Threat Detection solution on the same system as Protect4S Vulnerability Management. You will still need to create new connections because the user defined in the RFC plus its authorization set is different.
