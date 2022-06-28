# Application Settings

![Application Settings configuration](<../.gitbook/assets/image (29).png>)

If you have been granted the technical configurator role or the administrator role, you can access "Application Settings configuration" Fiori Tile. Please visit [this](systems-in-threat-detection/system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations. Upon accessing the application settings, you will see the following screen:

![General settings](<../.gitbook/assets/image (20).png>)

In this application, you define technical application settings of Threat Detection which includes General settings, Threat Detection and Storage length and the settings for SIEM.

### **General settings**

**Worker ID**\
This parameter is used to indicate how the the name should be identified and referenced in Security Information and Event Management (SIEM) that it comes from the Protect4S Threat Detection solution.

**Company Name**\ <mark style="color:red;"></mark>The entered value here will be send to the SIEM solution as part of the Threat data.

**Background Executor User Name**\
This is the user that is used to perform all the background activities and daemon schedules. This user should have the role /TDWO/BACKGROUND\_EXECUTOR. It is not to be mixed with the background service user in the satellite system which you define separately in each individual systems.

**Activate Use Cases on System Create/Update**\
****This setting defines whether use Cases are activated upon creation or update of the systems within the System Application as described [here](systems-in-threat-detection/system-configuration-fiori-application/).

**TD Server Group** (Optional)\
****Protect4S Threat Detection can use a specific RFC server group. The list is retrieved from RZ12.

**TD interval for Landscape in Seconds**\ <mark style="color:red;">****</mark>This parameter is used to define the interval frequency of checking the satellite systems specifically for the Landscape type of Use Cases.&#x20;

**No Threats for System Shutdown from** & **to** (situational/optional)\ <mark style="color:red;"></mark>If planned maintenance is scheduled, you can enter the stop and start times here so Protect4S Threat Detection solution will not send out the message that the system is being shutdown (only when given a soft shutdown) during that timeframe.

### **Threat Detection settings**



### **Storage settings**



### SIEM settings

This section is used to configure the link between SIEM and Threat Detection solution.

![SIEM settings](../.gitbook/assets/image.png)

\<To do: Explain what settings do and how to get data to fill there>

\*\*\*\*\*\*\*\*\*\*\*\*\*\*

****

**SIEM settings**

Depending on the type of SIEM you operate, some SIEM specific settings need to be provided for connecting and authenticating to the SIEM solution.

For Microsoft Sentinel you need to provide these settings:

![](<../.gitbook/assets/image (41).png>)

* **Customer ID**: This value can be retrieved in Microsoft Sentinel under "Log Analytics Workspaces" --> "Agents Management" --> "Workspace ID".
* **Security Key**: This value can be retrieved in Microsoft Sentinel under "Log Analytics Workspaces" --> "Agents Management" --> "Primary Key".
* **URL**: This value is made up by the Customer ID and a fixed part: [https://\<Customer ID>.ods.opinsights.azure.com/api/logs?api-version=2016-04-01](../technical-setup/installation/https:/%3CCustomer\_ID%3E.ods.opinsights.azure.com/api/logs)

**Remark:** For Microsoft Sentinel as well as other SIEM vendors you might need to import the HTTPS certificates into transaction STRUST for the connection to work. [See here ](troubleshooting/siem-certificates.md)for details.

**Remark**: For testing purposes or tuning it can be considered to only provide the SIEM settings later and first keep the Threats locally in the Protect4S TD solution.



