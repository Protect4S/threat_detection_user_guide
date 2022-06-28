# SAPcontrol

SAPcontrol connections are used to get data from the Operating System level. In case of issues with SAPcontrol connections, please check the following items:

Check:

* The [WIKI FAQ](https://wiki.scn.sap.com/wiki/display/SL/SAP+Host+Agent+Troubleshooting+Guide)
* SAP OSS Note [1563660 - sapcontrol, user authorization issues (SUM)](http://service.sap.com/sap/support/notes/1563660)
* SAP OSS Note [927637 - Web service authentication in sapstartsrv as of Release 7.00](http://service.sap.com/sap/support/notes/927637)
* Make sure the SAP kernel of the satellite system has a recent patch level, especially for old kernels 6.40 or 7.00
* Make sure that the ownership of the SAP kernel executable **sapuxuserchk** is correct for ALL sapususerchk file in all exe-subdirectories.
* For access to privileged OS Commands, the user configured must be added to the host profile of sapstartsrv (often in this location: **/usr/sap/hostctrl/exe/host\_profile**) using SAP parameter **service/admin\_users**
* On Windows (in Unix by default) the values for parameter **service/admin\_users** in the host\_profile are case sensitive and need to be defined exactly as the user running the service.\
  For example service running as "_domain\\**SAPServiceDAA**_" cannot be defined as "domain\\**SAPservicedaA**" in the host\_profile
* Multiple values for parameter **service/admin\_users** are possible. Use space as separator for multiple value. e.g. **service/admin\_users = SAPServiceDAA user1 sidadm user2.** The upper and the lower case letters must match.
* Add the SAP parameter parameter **service/admin\_users** to the Start- or Instance profile of the SAP satellite system.
* On Windows, the error _“Start service runs with administrative privileges, OSExecute disabled”_ might occur: the SAPService\<SID> user must not be part of the Administrators group. See also SAP Note [2480903 - "FAIL: Start Serv. runs with admin\*\*.\*\* priv., OSExecute disabled"](https://launchpad.support.sap.com/#/notes/2480903)
* On Linux: in case the error "FAIL: HTTP error, HTTP/1.1 401 Unauthorized" occurs: remove old **.sapstream\*** files from directory **/tmp** . See also SAP OSS Note [1565645 - SAP composite note: sapcontrol](http://service.sap.com/sap/support/notes/1565645)
* Whenever you have made changes to the file: **/usr/sap/hostctrl/exe/host\_profile** , you must restart sapcontrol with the command: **saphostexec –restart** in order to activate these changes.

**!!! General remark: Additional information can be obtained from the log in SMICM or when addding the "-debug" option on the OS command line when testing with sapcontrol.**

E.g.:

` sapcontrol -nr <NN> -host <a remote server> -function <any method>`` `` `**`-debug`**

If you get the error "Connection reset by peer" with "**bind (99: Cannot assign requested address)"** then see SAP Security note [2396062](https://launchpad.support.sap.com/#/notes/2396062).

General network related issues can be troubleshooted with the help of SAP note [3099550](https://launchpad.support.sap.com/#/notes/3099550).

**WAF / Firewall / IDS / IPS**

In modern networks, connections from the central Protect4S system to remote systems (especially in the cloud) might be blocked by network devices like (Web Application) Firewalls or IDS/IPS devices. Make sure that these devices do not interfere with the connections and if needed add these connections or source- and target IP-addresses to the allow-list.
