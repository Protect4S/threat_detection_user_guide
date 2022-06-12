# !Application Settings

![Application Settings configuration](<../.gitbook/assets/image (29).png>)

If you have the been granted to technical configurator role or the administrator role, you can access "Application Settings configuration" Fiori Tile. Please visit [this](systems-in-threat-detection/system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations.



### Application settings overview

Upon accessing the application settings, you will see the following screen:

#### General tab:

![General settings](<../.gitbook/assets/image (20).png>)

In this application, you define configurations and behavior of Threat Detection which includes General settings, Threat Detection and Storage length and the settings for SIEM.

**The Worker ID**\
This parameter is used to indicate how the the name should be identified and referenced in Security Information and Event Management (SIEM) that it comes from the Protect4S Threat Detection solution.

<mark style="color:red;">**The Company Name**</mark>\ <mark style="color:red;">attribute here is to...?</mark>

**Background Executor User Name**\
This is the user that is used to perform all the background activities and daemon schedules.\
It is not to be mixed with the background service user in the satellite system which you define separately in each individual systems.

**Activate Use Cases on System Create/Update**\
****This setting is used to configure the behavior Whether Use Cases (all) should be activated upon creation or update of the systems within the System Application [here](systems-in-threat-detection/system-configuration-fiori-application/).

**TD Server Group** (Optional)\
****Should you wish to have Threat Detection to use a specific server group, define it here.

<mark style="color:red;">**TD interval for Landscape in Seconds**</mark>

****

<mark style="color:red;">**No Threats for System Shutdown from**</mark> <mark style="color:red;"></mark><mark style="color:red;">&</mark> <mark style="color:red;"></mark><mark style="color:red;">**to**</mark> <mark style="color:red;"></mark><mark style="color:red;">(situational/optional)</mark>



#### SIEM settings

This section is used to configure the link between SIEM and Threat Detection solution.

![SIEM settings](../.gitbook/assets/image.png)

\<To do: Explain what settings do and how to get data to fill there>

After setting the SIEM Active checkbox, click elsewhere in the screen to see the specific SIEM settings.

