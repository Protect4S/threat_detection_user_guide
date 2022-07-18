# SSL certificate errors

If the following errors occur it is in most cases because the certificates of the to-be connected satellite system are not trusted (not imported in transaction STRUST) in the system Protect4S Threat Detection solution.

* "`SSSLERR_PEER_CERT_UNTRUSTED`"
* "`SSSLERR_SERVER_CERT_MISMATCH`"
* "`ICF Error when creating object - Argument not found`"&#x20;
* or other certificate related errors

#### To solve this please follow the below steps. 

**Get the certificate(s) from the Satellite system by** [**downloading**](https://support.shift4.com/hc/en-us/articles/360038747254-Export-an-Existing-Certificate-from-a-Web-Browser) **them for example from the browser**

1. Use your Internet browser to connect to the required satellite destination address 'https://...'
2. As soon as the connection has been established, display the security details (usually, by double clicking the lock symbol)
3. Display the certificate of the server
4. Export the server certificate into a file (for example, in the format 'Base64')
5. If necessary, open the certificate or the certificates of the certificate chain from the certificate hierarchy, and also export this certificate or these certificates

**Import the certificates in STRUST**

1. In the Protect4S central system call transaction _STRUST_ and double-click on _SSL client (Standard)_ in the left tree view of PSEs (also called "SAPSSLC.pse")
2. From Menu, choose _Certificate->Import_. In the _File_ tab enter the filename of the downloaded cert into the field _File path_, or use the selection help at the end of that field for an Open File popup window of the OS
3. When the proper certificate appears in the certificate details view in the lower right area of transaction _STRUST_, press the _Add to Certificate List_ button on the bottom.
4. Save the changes to the PSE with _Save_ button
5. Redo steps 1-4 for _SSL client (Anonymous)_ PSE (also called "SAPSSLA.pse")

Newer Releases of SAP Netweaver (702 and 710+) will automatically reload the SSL PSE after saving the change. If the error PEER\_CERT\_UNTRUSTED persists, please try manually restarting the icman process. For old Netweaver Releases (6xx, 700 and 701) you will always have to manually restart the icman process for the PSE change to take effect. Use transaction SMICM and from Menu "Administration"->"ICM"->"Exit Soft"->"Global" to manually restart the icman process.

#### **For specific "`ICF Error when creating object - Argument not found`":**

Make sure the HTTPS service on the VM system is active in SMICM and that PSE keystore "`SSL client SSL Client (Anonymous)`" is activated in STRUST.\


References with more information:

SAP Wiki: [How to troubleshoot SSSLERR\_PEER\_CERT\_UNTRUSTED](https://wiki.scn.sap.com/wiki/display/Security/Troubleshooting+Guide+-+How+to+troubleshoot+the+SSSLERR\_PEER\_CERT\_UNTRUSTED+\(peer+certificate+\(chain\)+is+not+trusted\)+issue)\
SAP Note: [2461900 - SSSLERR\_PEER\_CERT\_UNTRUSTED error in dev\_icm trace](https://launchpad.support.sap.com/#/notes/1094342)\
SAP Note: [1094342 - ICM trace contains verification of the server's certificate](https://launchpad.support.sap.com/#/notes/2461900)\
SAP Note: [510007 - Setting up SSL on Web Application Server ABAP\
](https://launchpad.support.sap.com/#/notes/510007)SAP Note: [2469949 - ICF Error when creating HTTP client object by Config for URL](https://launchpad.support.sap.com/#/notes/2469949)
