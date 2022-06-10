# Operating System user other than \<sid>adm

When, for some reason, the default \<sid>adm OS user cannot be used, the following alternatives are possible. **Alternative A is best here**, because a cloned user can be protected using a no-login shell and is in all aspects equivalent to the \<sid>adm user. However: Alternative A is **not** available for the Windows operating system. For Windows, only the (sub-optimal) Alternative B can be used.

You should **only** consider alternative B when there is really no other option available, because some Protect4S checks on operating system level (the ones that need the OSExecute function of SAPControl) will not work.

**A) Clone the \<sid>adm user**

**1. Copy the \<sid>adm user record in /etc/passwd and /etc/shadow to a new user**

Copy the \<sid>adm user record in both the /etc/passwd and /etc/shadow files to a new user.

**2. In the /etc/passwd file, change the login shell for the new user into: /sbin/nologin and save**

![Cloned user smcadm](<../../../.gitbook/assets/image (27).png>)

​In the example above, the smdadm user record was copied to a new user called smcadm and the login shell was changed to: /sbin/nologin.

**3. Change the password for the newly created user**

(as root): set a new password:

\> passwd \<new user>

and use this new user and password to create the SAPControl connections in Threat Detection.

There is no equivalent option to clone a user in Windows.

### B) Use a newly created OS user

#### Procedure for Linux / UNIX:

**1. Create new OS-user**

(root):> useradd -d /home/\<os-user> -g \<sapsys GID> -G sapinst \<os-user>

**2. Set initial password**

(root):> passwd \<os-user>:Set initial passwd

**3. Set final passwd**

(root):> su - \<os-user>> passwdEnter initial password first then set final password twice

**4. set default shell as csh**

(root):> vi /etc/passwdChange shell for \<os-user> from /bin/bash to /bin/csh

**5. Create home directory**

(root):> mkdir /home/\<os-user>> chown \<os-user>:sapsys /home/\<os-user>> chmod 755 /home/\<os-user>

**6. Copy \<sid>adm env to \<os-user>**

(os-user):> cd > cp /home/\<sid>adm/.\* . Logout and login and check environment

**7. Check & set correct permissions on sapuxuserchk executable**

(root):

\> cd /sapmnt/\<SID>/exe/uc/linuxx86\_64

\> chown root:sapsys sapuxuserchk

\> chmod u+s,o-rwx sapuxuserchk

Also on all local instance exe directories (DVEBMGSxx, Dxx and ASCSxx):

(root):

\> cd /usr/sap/\<SID>/\<instance>/exe

\> chown root:sapsys sapuxuserchk

\> chmod u+s,o-rwx sapuxuserchk​

For SAP HANA Databases also do the above for the HDB executable directory (e.g. /usr/sap/\<HANA SID>/SYS/exe/hdb).

Documentation from SAP can be found in SAP note [927637.](https://launchpad.support.sap.com/#/notes/927637)

**8. Add the following 2 lines to the DEFAULT.PFL of the SAP satellite system (and also for the ASCS instance profile and HANA DB instance if applicable)**

service/protectedwebmethods = SDEFAULT

service/admin\_users = \<os-user>

* **On Unix** : service/admin\_users = \*\*<\*\*user1> \<user2>
* **On Windows**: service/admin\_users = domain\\\<user1> domain\\\<user2>

where \<user1> is the normal \<sid>adm user and \<user2> is the user that was created, separated by space, and restart the SAP satellite system on a suitable moment to activate these settings.

For HANA Databases do the above in the DEFAULT.PFL in directory /usr/sap/\<HANA SID>/SYS/profile​

**9. Re-Start SAP Control service for all instances (DVEBMGSxx, Dxx, (A)SCSxx)**

(official sap-user):

\> sapcontrol -nr \<instance# xx> -function RestartService

**10. (Re)create the SAPControl connections using the Systems menu**\
\*\*\*\*The connection will not turn green (as is the case with the \<sid>adm user), but yellow instead. This is OK. When you hover your cursor over the yellow icon it will show as:

**11. Verify that SAP Control works ok**\
\*\*\*\*In the Systems **overview select** the SAP satellite system concerned, perform a connection test and inspect the SAP Control context. It should now be filled for all instances:

![SAPControl connection with alternative OS-user](<../../../.gitbook/assets/image (57).png>)

_Notice: usernames are case sensitive in Linux / Unix._

\
**Procedure for Windows:**

For Windows you must create a user as a member of the Groups: **SAP\_LocalAdmin** and **Users:**![](https://files.gitbook.com/v0/b/gitbook-legacy-files/o/assets%2F-Mee93KW0BtSWNWC0nS9%2F-MhItKeLzfio6uiJOuVS%2F-MhIu1QF9pXCwpWmlDqM%2Fimage.png?alt=media\&token=996e2640-e96c-4261-8916-f3dfbeecfb05)\
Windows Roles required for Protect4S satellite OS user

**Next:** Follow step 8-11 from the above procedure for non-windows systems.
