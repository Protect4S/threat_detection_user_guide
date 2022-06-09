---
description: Database user in the satellite systems
---

# Satellite system database user

Database connections are not mandatory for most systems (apart for Java), but in order to get the most out of Protect4S we recommend to create a database connection using the System connection wizard. For this connection you will need to create a database user in the database of the satellite system.&#x20;

Keep in mind that if you connect to a database type other then the one on the SAP Solution Manager you must install Database libraries for that Database. **See Appendix B: Installation database libraries**.

✔ If you choose not to create a database connection this implies that some specific database checks might fail with the error message “_Unable to process the check by a technical error_”.

✔ If the database connection is not available then in some cases a fallback mechanism is used to retrieve database specific information. For example for ABAP systems an RFC is used for MSSQL and MAXDB. For HANA a fallback is implemented via the OS command HDBCLI. This will only work if the SAPControl connection user is the \<sid>adm OS user and can access the hdbuserstore.

✔ For Java systems, Database connections are mandatory as many checks rely on this connection type.

In the System connection wizard, you must a database user that has **read-only** access (SELECT privilege) on the following tables (Depending if you have an **ABAP** or **JAVA** stack):

| All Database Types ABAP Schema                                                                                                                                                                                                                                                                                                                          | Additional tables for MSSQL                                                                         | Additional tables for HANA                                                                                                                                                                                                                                | All Database Types JAVA Schema |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| <p>DD09L, USRACL, SEC_POLICY_ATTR, SEC_POLICY_RT, EWOSS, SPTH, USR02 (no pw hashes read), TDDAT, RSAUPROF, VSCAN_PROF, AGR_USERS,<br>SRT_CFG_CLI_ASGN,<br>USR40, UST04, PRGN_CUST, SXPGCOSTAB, RFCDES, RFCCBWHITELIST, SXROUTE, TCCSEC, SSF_PSE_H, SSF_PSE_L, ADIRACCESS, TMSPVERS, /SSF/DHEAD, DEVACCESS, ICF_SESSION_CNTL, VSCAN_SERVER, TMSPCONF</p> | sys.objects, sys.server\_principals, sys.server\_role\_members, sys.sql\_logins, sys.configurations | SYS.GRANTED\_ROLES, SYS.M\_PASSWORD\_POLICY, SYS.M\_DATABASE\_HISTORY, SYS.USERS, SYS.M\_INIFILE\_CONTENTS, SYS.GRANTED\_PRIVILEGES, SYS.LCM\_SOFTWARE\_COMPONENTS, \_SYS\_REPO.DELIVERY\_UNITS, \_SYS\_SECURITY.SYS\_PASSWORD\_BLACKLIST, SYS.M\_LICENSE | J2EE\_CONFIGENTRY              |

To create the database user you can use the standard database tooling or a SQL scripts. See some examples specifically for creating users for the **ABAP** stack below).

In the examples below:

* the placeholders %user% and %password% should be replaced with your own username and password.
* the placeholder %SAPSID% need to be replaced by the SAP Database schema. This depends on the Database used, for Oracle this is typically SAPR3 or SAPSR3 and for MaxDB this is typically SAP%SID% (ABAP) or SAP%SID%DB (JAVA) where %SID% is the SAP System-ID.

## MAXDB: <a href="#maxdb" id="maxdb"></a>

```
CREATE USER %user% PASSWORD %password% STANDARD ENABLE CONNECT //
GRANT SELECT ON %SAPSID%.USR40 TO %user% //
GRANT SELECT ON %SAPSID%.PRGN_CUST TO %user% //
GRANT SELECT ON %SAPSID%.UST04 TO %user% // 
GRANT SELECT ON %SAPSID%.SXPGCOSTAB TO %user% //
GRANT SELECT ON %SAPSID%.RFCDES TO %user% //
GRANT SELECT ON %SAPSID%.RFCCBWHITELIST TO %user% //
GRANT SELECT ON %SAPSID%.SXROUTE TO %user% //
GRANT SELECT ON %SAPSID%.TCCSEC TO %user% //
GRANT SELECT ON %SAPSID%.SSF_PSE_H TO %user% //
GRANT SELECT ON %SAPSID%.SSF_PSE_L TO %user% //
GRANT SELECT ON %SAPSID%.ADIRACCESS TO %user% //
GRANT SELECT ON %SAPSID%.TMSPVERS TO %user% //
GRANT SELECT ON %SAPSID%./SSF/DHEAD TO %user% //
GRANT SELECT ON %SAPSID%.ICF_SESSION_CNTL TO %user% //
GRANT SELECT ON %SAPSID%.DEVACCESS TO %user% // 
GRANT SELECT ON %SAPSID%.VSCAN_SERVER TO %user% // 
GRANT SELECT ON %SAPSID%.TMSPCONF TO %user% //
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user% //
GRANT SELECT ON %SAPSID%.SRT_CFG_CLI_ASGN TO %user% //
GRANT SELECT ON %SAPSID%.DD09L TO %user% //
GRANT SELECT ON %SAPSID%.USRACL TO %user% //
GRANT SELECT ON %SAPSID%.SEC_POLICY_ATTR TO %user% //
GRANT SELECT ON %SAPSID%.SEC_POLICY_RT TO %user% //
GRANT SELECT ON %SAPSID%.EWOSS TO %user% //
GRANT SELECT ON %SAPSID%.SPTH TO %user% //
GRANT SELECT ON %SAPSID%.USR02 TO %user% //
GRANT SELECT ON %SAPSID%.TDDAT TO %user% //
GRANT SELECT ON %SAPSID%.RSAUPROF TO %user% //
GRANT SELECT ON %SAPSID%.VSCAN_PROF TO %user% //
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user% //
```

## ORACLE / DB2/SYBASE: <a href="#oracle-db2-sybase" id="oracle-db2-sybase"></a>

```
CREATE USER %user% IDENTIFIED BY %password%;
GRANT CONNECT TO %user%;
GRANT SELECT ON %SAPSID%.USR40 TO %user%;
GRANT SELECT ON %SAPSID%.PRGN_CUST TO %user%;
GRANT SELECT ON %SAPSID%.UST04 TO %user%;
GRANT SELECT ON %SAPSID%.SXPGCOSTAB TO %user%;
GRANT SELECT ON %SAPSID%.ICFSERVLOC TO %user%;
GRANT SELECT ON %SAPSID%.RFCDES TO %user%;
GRANT SELECT ON %SAPSID%.RFCCBWHITELIST TO %user%;
GRANT SELECT ON %SAPSID%.SXROUTE TO %user%;
GRANT SELECT ON %SAPSID%.TCCSEC TO %user%;
GRANT SELECT ON %SAPSID%.SSF_PSE_H TO %user%;
GRANT SELECT ON %SAPSID%.SSF_PSE_L TO %user%;
GRANT SELECT ON %SAPSID%.ADIRACCESS TO %user%;
GRANT SELECT ON %SAPSID%.TMSPVERS TO %user%;
GRANT SELECT ON %SAPSID%./SSF/DHEAD TO %user%;
GRANT SELECT ON %SAPSID%.ICF_SESSION_CNTL TO %user%;
GRANT SELECT ON %SAPSID%.DEVACCESS TO %user%;
GRANT SELECT ON %SAPSID%.VSCAN_SERVER TO %user%;
GRANT SELECT ON %SAPSID%.TMSPCONF TO %user%;
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user%;
GRANT SELECT ON %SAPSID%.SRT_CFG_CLI_ASGN TO %user%;
GRANT SELECT ON %SAPSID%.DD09L TO %user%;
GRANT SELECT ON %SAPSID%.USRACL TO %user%;
GRANT SELECT ON %SAPSID%.SEC_POLICY_ATTR TO %user%;
GRANT SELECT ON %SAPSID%.SEC_POLICY_RT TO %user%;
GRANT SELECT ON %SAPSID%.EWOSS TO %user%;
GRANT SELECT ON %SAPSID%.SPTH TO %user%;
GRANT SELECT ON %SAPSID%.USR02 TO %user%;
GRANT SELECT ON %SAPSID%.TDDAT TO %user%;
GRANT SELECT ON %SAPSID%.RSAUPROF TO %user%;
GRANT SELECT ON %SAPSID%.VSCAN_PROF TO %user%;
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user%;

/*** For DB2 ONLY:
GRANT SELECT ON SYSCAT.SCHEMATA TO %user%;
```

## HANA as part of ABAP or Java: <a href="#hana" id="hana"></a>

```
/*** RUN AS SYSTEM OWNER:
CREATE USER %user% PASSWORD %password%; (Create the user with password)
ALTER USER %user% DISABLE PASSWORD LIFETIME; (Disable PW change on logon)
GRANT RESTRICTED_USER_ODBC_ACCESS TO %user%; (Provide grant for ODBC access)
GRANT SELECT ON _SYS_SECURITY._SYS_PASSWORD_BLACKLIST TO %user%;
GRANT SELECT ON _SYS_REPO.DELIVERY_UNITS TO %user%;
GRANT SELECT ON SYS.LCM_SOFTWARE_COMPONENTS TO %user%;
GRANT SELECT ON SYS.M_INIFILE_CONTENTS TO %user%;
GRANT SELECT ON SYS.GRANTED_PRIVILEGES TO %user%;
GRANT SELECT ON SYS.M_PASSWORD_POLICY TO %user%;
GRANT SELECT ON SYS.GRANTED_ROLES TO %user%;
GRANT SELECT ON SYS.M_DATABASE_HISTORY TO %user%;
GRANT SELECT ON SYS.USERS TO %user%;
GRANT SELECT ON SYS.M_LICENSE TO %user%;
GRANT CATALOG READ TO %user%;


/*** RUN AS SCHEMA OWNER OR SYSTEM OWNER:
GRANT SELECT ON %SAPSID%.USR40 TO %user%; (Provide grants for individual tables, SELECT only)
GRANT SELECT ON %SAPSID%.PRGN_CUST TO %user%;
GRANT SELECT ON %SAPSID%.UST04 TO %user%;
GRANT SELECT ON %SAPSID%.SXPGCOSTAB TO %user%;
GRANT SELECT ON %SAPSID%.ICFSERVLOC TO %user%;
GRANT SELECT ON %SAPSID%.RFCDES TO %user%;
GRANT SELECT ON %SAPSID%.RFCCBWHITELIST TO %user%;
GRANT SELECT ON %SAPSID%.SXROUTE TO %user%;
GRANT SELECT ON %SAPSID%.TCCSEC TO %user%;
GRANT SELECT ON %SAPSID%.SSF_PSE_H TO %user%;
GRANT SELECT ON %SAPSID%.SSF_PSE_L TO %user%;
GRANT SELECT ON %SAPSID%.ADIRACCESS TO %user%;
GRANT SELECT ON %SAPSID%.TMSPVERS TO %user%;
GRANT SELECT ON %SAPSID%."/SSF/DHEAD" TO %user%;
GRANT SELECT ON %SAPSID%.ICF_SESSION_CNTL TO %user%;
GRANT SELECT ON %SAPSID%.DEVACCESS TO %user%;
GRANT SELECT ON %SAPSID%.VSCAN_SERVER TO %user%;
GRANT SELECT ON %SAPSID%.TMSPCONF TO %user%;
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user%;
GRANT SELECT ON %SAPSID%.SRT_CFG_CLI_ASGN TO %user%;
GRANT SELECT ON %SAPSID%.DD09L TO %user%;
GRANT SELECT ON %SAPSID%.USRACL TO %user%;
GRANT SELECT ON %SAPSID%.SEC_POLICY_ATTR TO %user%;
GRANT SELECT ON %SAPSID%.SEC_POLICY_RT TO %user%;
GRANT SELECT ON %SAPSID%.EWOSS TO %user%;
GRANT SELECT ON %SAPSID%.SPTH TO %user%;
GRANT SELECT ON %SAPSID%.USR02 TO %user%;
GRANT SELECT ON %SAPSID%.TDDAT TO %user%;
GRANT SELECT ON %SAPSID%.RSAUPROF TO %user%;
GRANT SELECT ON %SAPSID%.VSCAN_PROF TO %user%;
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user%;
```

## HANA Standalone: <a href="#hana" id="hana"></a>

```
/*** RUN AS SYSTEM OWNER:
CREATE USER %user% PASSWORD %password%; (Create the user with password)
ALTER USER %user% DISABLE PASSWORD LIFETIME; (Disable PW change on logon)
GRANT RESTRICTED_USER_ODBC_ACCESS TO %user%; (Provide grant for ODBC access)
GRANT SELECT ON _SYS_SECURITY._SYS_PASSWORD_BLACKLIST TO %user%;
GRANT SELECT ON _SYS_REPO.DELIVERY_UNITS TO %user%;
GRANT SELECT ON SYS.LCM_SOFTWARE_COMPONENTS TO %user%;
GRANT SELECT ON SYS.M_INIFILE_CONTENTS TO %user%;
GRANT SELECT ON SYS.GRANTED_PRIVILEGES TO %user%;
GRANT SELECT ON SYS.M_PASSWORD_POLICY TO %user%;
GRANT SELECT ON SYS.GRANTED_ROLES TO %user%;
GRANT SELECT ON SYS.M_DATABASE_HISTORY TO %user%;
GRANT SELECT ON SYS.USERS TO %user%;
GRANT SELECT ON SYS.M_LICENSE TO %user%;
GRANT CATALOG READ TO %user%;
```

## MSSQL: <a href="#hana" id="hana"></a>

```
Run from MSSQL while logged on as <SID>adm:

USE [<DBSID>]
GO
CREATE LOGIN [%user%] WITH PASSWORD='%password%', DEFAULT_DATABASE=[<DBSID>]
GO
CREATE USER test FOR LOGIN %user% 
GO
ALTER USER [%user%] WITH DEFAULT_SCHEMA=[<SAPSID>]
GO
GRANT CONNECT TO [%user%]
GO
GRANT SELECT ON %SAPSID%.USR40 TO %user%
GRANT SELECT ON %SAPSID%.PRGN_CUST TO %user%
GRANT SELECT ON %SAPSID%.UST04 TO %user%
GRANT SELECT ON %SAPSID%.SXPGCOSTAB TO %user%
GRANT SELECT ON %SAPSID%.ICFSERVLOC TO %user%
GRANT SELECT ON %SAPSID%.RFCDES TO %user%
GRANT SELECT ON %SAPSID%.RFCCBWHITELIST TO %user%
GRANT SELECT ON %SAPSID%.SXROUTE TO %user%
GRANT SELECT ON %SAPSID%.TCCSEC TO %user%
GRANT SELECT ON %SAPSID%.SSF_PSE_H TO %user%
GRANT SELECT ON %SAPSID%.SSF_PSE_L TO %user%
GRANT SELECT ON %SAPSID%.ADIRACCESS TO %user%
GRANT SELECT ON %SAPSID%.TMSPVERS TO %user%
GRANT SELECT ON %SAPSID%./SSF/DHEAD TO %user%
GRANT SELECT ON %SAPSID%.ICF_SESSION_CNTL TO %user%
GRANT SELECT ON %SAPSID%.DEVACCESS TO %user%
GRANT SELECT ON %SAPSID%.VSCAN_SERVER TO %user%
GRANT SELECT ON %SAPSID%.TMSPCONF TO %user%
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user%
GRANT SELECT ON %SAPSID%.SRT_CFG_CLI_ASGN TO %user%
GRANT SELECT ON %SAPSID%.DD09L TO %user%
GRANT SELECT ON %SAPSID%.USRACL TO %user%
GRANT SELECT ON %SAPSID%.SEC_POLICY_ATTR TO %user%
GRANT SELECT ON %SAPSID%.SEC_POLICY_RT TO %user%
GRANT SELECT ON %SAPSID%.EWOSS TO %user%
GRANT SELECT ON %SAPSID%.SPTH TO %user%
GRANT SELECT ON %SAPSID%.USR02 TO %user%
GRANT SELECT ON %SAPSID%.TDDAT TO %user%
GRANT SELECT ON %SAPSID%.RSAUPROF TO %user%
GRANT SELECT ON %SAPSID%.VSCAN_PROF TO %user%
GRANT SELECT ON %SAPSID%.AGR_USERS TO %user%
EXEC master..sp_addsrvrolemember @loginame = N'%user%', @rolename = N'sysadmin'
GO
```
