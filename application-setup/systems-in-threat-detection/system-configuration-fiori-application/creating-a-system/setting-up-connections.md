---
description: Setting up connections to the application, database and operating system
---

# Setting up connections

If you are running the Protect4S Threat Detection solution on the same system as Protect4S Vulnerability Management. You will still need to create create new connections because the user defined in the RFC plus its authorization set is different.

In the first step you enter the user that will be used in the RFC for Threat Detection. This user in the satellite system must have the role "TDWO\_SATELLITE".

Notice the client you enter here will be the main client and you cannot remove the connection later without removing the whole system and recreated with different settings if needed. The other additional clients will that is not the main client assigned here can be removed freely after from this system. exclude it later should you decide to change it.

![Creating ABAP connection](<../../../../.gitbook/assets/image (51).png>)

![Creating RFCs in the back-end system](<../../../../.gitbook/assets/image (29).png>)

By default the application will detect all available clients and list them here re-use the user that you have provided initially. If you want to use a different user or if the password is different from the one than you have provided previously, you can change it here, or you can uncheck the line to skip creating the RFC if you do not wish an RFC to be created for a particular RFC.

Database connection:

![Setting up database connection](<../../../../.gitbook/assets/image (14).png>)

The database is not necessary only for certain specific use case that requires database access a connection to the database this needs to be create.

Enter here the manual created database user and password. Regarding the hostname, if you get an error. Please check on the operating system of the Threat Detection system whether you can ping or telnet to the system via its RFC port or Database

![Connecting to the operating system of the satellite system](<../../../../.gitbook/assets/image (52).png>)

Enter here the OS user to sapcontrol, you may enter \<sid>adm or a different user that has sufficient authorization to make use of the sapcontrol.

![Overview of all the instances where sapcontrol will be used](<../../../../.gitbook/assets/image (25).png>)

Review and confirm the list of all the applications applicable for your system. If there is a system missing confirm whether the system is reachable.

![Total overview of the to be created RFCs.](<../../../../.gitbook/assets/image (73) (1).png>)

This screen is a confirmation of all the connections that will be created, in our example we have skipped the database connection because it is not mandatory.
