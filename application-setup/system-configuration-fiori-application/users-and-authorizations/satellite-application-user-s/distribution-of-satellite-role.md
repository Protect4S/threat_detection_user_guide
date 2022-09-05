---
description: Distributing satellite role in the back-end systems
---

# Distribution of Satellite Role

This chapter only applies if you want to make use of the feature to distribute the **TDWO\_SATELLITE** role from the central system to satellite systems. In case you use your own CUA or IDM solution to distribute roles you can skip this chapter. The distribution of the Protect4S satellite role can be done manually. Optionally **TDWO\_SATELLITE\_PUSH** can be used if you wish to use the automatic role distribution instead via Protect4S's Threat Detection solution.

### Distributing the role(s) manually.

Download the required Protect4S satellite role from the Solution Manager in which Protect4S is installed. The 2 roles **TDWO\_SATELLITE** for the ABAP RFC satellite system user and the (optional) role required for automatic role distribution **TDWO\_SATELLITE\_PUSH** are always shipped with every version of Protect4S.

#### **Download the Protect4S Threat Detection role(s) you require**

Log in on the system on which Protect4S Threat Detection solution has been installed and execute transaction **PFCG**. Select the appropriate role **TDWO\_SATELLITE** and select from the menu "Role", "Download":

![Enter the role you wish to download](<../../../../.gitbook/assets/image (65) (1) (1).png>)

From the PFCG menu, select "Role", "Download":

![Performing a download](<../../../../.gitbook/assets/image (49).png>)

Confirm the popup:

![Confirm popup](<../../../../.gitbook/assets/image (60) (1).png>)

Select a location for the role on your workstation and save the file. In this tutorial we will save this in our Temp directory:

![Choose a path to save the role](<../../../../.gitbook/assets/image (31) (1) (1) (1) (1).png>)

You may repeat this step for roles **TDWO\_SATELLITE\_PUSH** if you use the automatic distribution of Protect4S satellite user roles.

### **Upload the role to a satellite system**

Login to the satellite system, execute transaction PFCG and select Role, Upload from the PFCG menu:

![Select Role, Upload from the PFCG menu](<../../../../.gitbook/assets/image (1) (1).png>)

Select the role file you downloaded to your PC in the previous step:

![Select role file downloaded in the first step](<../../../../.gitbook/assets/image (55) (1).png>)

Provide permission to upload the file:

![Provide permission for upload](<../../../../.gitbook/assets/image (2) (1) (1).png>)

Overwrite the old version if the role that exists to update:

![Ignore warning and overwrite old role version](<../../../../.gitbook/assets/image (16).png>)

Make sure the color status for **Menu**, **Authorization** and **User** are green in PFCG:

![Make sure all 3 lights are green](<../../../../.gitbook/assets/image (43).png>)

You may repeat this step for role **TDWO\_SATELLITE\_PUSH** if you want to use automatic distribution of Protect4S satellite user roles.\
If one of the 3 mentioned tab is not green, it could be that the authorization profile needs to be regenerated and/or redistributed to the Protect4S satellite system user. Ask an SAP user administrator to do this if you do not know how to proceed.

Notice: If you have changed the namespace of the roles make sure it is that one is updated in that version.
