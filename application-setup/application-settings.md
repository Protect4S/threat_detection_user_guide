# Application Settings

![Application Settings configuration](<../.gitbook/assets/image (29).png>)

If you have been granted the technical configurator role or the administrator role, you can access "Application Settings configuration" Fiori Tile. Please visit [this](system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations. Upon accessing the application settings, you will see the following screen:

![General settings](<../.gitbook/assets/image (20).png>)

In this application, you define technical application settings of Threat Detection which includes General Settings, Threat Detection and Storage Settings and the settings for SIEM.

### **General settings & Threat Detection settings**

**Worker ID**\
This parameter is used to indicate how the the name should be identified and referenced in Security Information and Event Management (SIEM) that it comes from the Protect4S Threat Detection solution.

**Company Name**\ <mark style="color:red;"></mark>The entered value here will be send to the SIEM solution as part of the threat data.

**Background Executor User Name**\
This is the user that is used to perform all the background activities and daemon schedules. This user will be given the role /TDWO/BACKGROUND\_EXECUTOR upon saving. It is not to be mixed with the background service user in the satellite system which you define separately in each individual system.

**Activate Use Cases on System Create/Update**\
****This setting defines whether use cases are activated upon creation or update of the systems within the System Application as described [here](system-configuration-fiori-application/).

**TD Server Group** (Optional)\
****Protect4S Threat Detection can use a [specific RFC server group](troubleshooting/using-server-groups.md). The list is retrieved from RZ12.

**TD interval for Landscape in Seconds**\ <mark style="color:red;">****</mark>This parameter is used to define the interval frequency of checking the satellite systems specifically for the landscape-type of use cases.&#x20;

**No Threats for System Shutdown from** & **to** (situational/optional)\ <mark style="color:red;"></mark>If planned maintenance is scheduled, you can enter the stop and start times here so Protect4S Threat Detection solution will not send out the message that Threat Detection system is being shutdown (only when given a soft shutdown) during that timeframe.

### **Storage settings**

Protect4S Threat Detection objects can generate large amount of data, It will however be cleaned up and deleted automatically after some time. With the below thresholds you can define the threshold when the cleanup gets triggered for each kind of data:

* Maximum Event Storage in Hours (Default 2 hours)
* Maximum Threat Storage in Days (Default 180 days)
* Maximum Message Storage in Days (Default 180 days)

### SIEM settings

This section is used to configure the link between the Protect4S Threat Detection solution and your SIEM solution. Depending on the type of SIEM you operate, some SIEM specific settings need to be provided for connecting and authenticating to the SIEM solution. For Microsoft Sentinel you need to provide these settings:

![](<../.gitbook/assets/image (41).png>)

* **Customer ID**: This value can be retrieved in Microsoft Sentinel under "Log Analytics Workspaces" --> "Agents Management" --> "Workspace ID".
* **Security Key**: This value can be retrieved in Microsoft Sentinel under "Log Analytics Workspaces" --> "Agents Management" --> "Primary Key".
* **URL**: This value is made up by the Customer ID and a fixed part: [https://\<Customer ID>.ods.opinsights.azure.com/api/logs?api-version=2016-04-01](../technical-setup/installation/https:/%3CCustomer\_ID%3E.ods.opinsights.azure.com/api/logs)

#### SIEM Heartbeat

To make sure that the connection between Protect4S Threat Detection solution and SIEM is still working, you can turn on the heartbeat. Depending on the interval set, Protect4S Threat Detection will send a heartbeat message to SIEM. If the SIEM solution does not get any heartbeat messages anymore after some time, the SIEM solution can trigger an event. Additionally inside the Protect4S Threat Detection solution a message will be created that the communication is disrupted.

#### Testing the SIEM connection & authorization

After you have entered the credentials you can check if the connection can actually be established by clicking on the "Check Connection" button. ![](<../.gitbook/assets/image (7) (2).png>). This button is only visible in Display mode.

If the connection test went well, you should see the following message on the screen briefly:\
**"**_Connection is OK. A test message was sent to SIEM without errors._**".**

If you get an error please check detailed error messages. Generally it is the credentials or the certificates. Also __ make sure that the system can access the SIEM environment on network level (often port 443 but that can be different_)._ A successful sent test message can be seen at the SIEM side:

![](<../.gitbook/assets/image (25).png>)

#### **Remark:**

* For Microsoft Sentinel as well as other SIEM vendors you might need to import the HTTPS certificates into transaction STRUST for the connection to work. [See here ](troubleshooting/siem-certificates.md)for details.
* For testing purposes or tuning you may opt for configuring the SIEM at a later point and first keep the Threats locally on the Protect4S TD solution. Once completed with testing and tuning you can provide the SIEM information in Application Settings.
