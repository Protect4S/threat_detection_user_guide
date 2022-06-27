# Post-installation processing

### Run the post-installation wizard <a href="#run-the-post-installation-wizard" id="run-the-post-installation-wizard"></a>

After the installation via transaction SAINT is done, run the post-installation wizard **in the client where Protect4S TD needs to run,** not in client 000. The post-installation wizard is started by executing transaction: **/n/TDWO/PI**. The wizard will activate the [necessary SICF services](../troubleshooting/sicf-services.md) and will also prompt for the license installation.

![](https://files.gitbook.com/v0/b/gitbook-legacy-files/o/assets%2F-M4DeA\_ch2aT\_DMIXtj1%2F-M4DeCFgK1Kor0XH90AI%2F-M4DeKsFHHQTfTDDaEVZ%2Fimage009.png?generation=1586162673680417\&alt=media)

### License installation (Not applicable for the first release) <a href="#license-installation" id="license-installation"></a>

Protect4S TD needs a valid license in order to execute. The first time that Protect4S TD is started, this license must be installed. A valid license file will be supplied by the Protect4S Support team during the purchasing process.

#### Requesting a Protect4S TD license <a href="#requesting-a-new-protect4s-license" id="requesting-a-new-protect4s-license"></a>

Requesting a new Protect4S TD license can be done by selecting the option "Request license" from the menu:

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-M4DeA\_ch2aT\_DMIXtj1%2Fuploads%2FlpABSLg8wjMsdY05dACo%2Fimage.png?alt=media\&token=e3d48863-20a7-4f96-94a7-43a5bd76fe02)

This will show you the relevant information of the Protect4S TD system (System number and Installation number) that we need for generating the license:

![](https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-M4DeA\_ch2aT\_DMIXtj1%2Fuploads%2FqZ6wlogI50S0clUj1trK%2Fimage.png?alt=media\&token=5ac7b421-1906-45dd-a186-72d2d18a4c4f)

When the "Open e-mail" option is chosen, a mail will be composed with a template. The relevant information mentioned in the mail is required for Protect4S support to generate your license file:

![](<../../.gitbook/assets/image (33) (1).png>)

Then, send the mail to us and we will generate a license file for you. Should you have lost this file or never received it, please contact the Protect4S support team.

#### Uploading the license file

![](<../../.gitbook/assets/image (17) (1).png>)

This will start up a new screen in which you can upload and save the license key file:

![](<../../.gitbook/assets/image (19) (1).png>)

After uploading and saving the license key file, you will be able to see the license in the overview in the License Administration:

![](<../../.gitbook/assets/image (13).png>)

After having installed the license: select **Yes**.

![](<../../.gitbook/assets/image (68).png>)

### Application settings

Next inspect and update the Application settings:

![](<../../.gitbook/assets/image (53).png>)

You must supply data for generic settings and for SIEM specific settings.

**General settings**

A lot of specific tuning can be done any time when working with the application. For now, after installation, at least provide a background user for the background jobs. This must be a user with the role **/TDWO/BACKGROUND\_EXECUTOR.**

**SIEM settings**

Depending on the type of SIEM you operate, some SIEM specific settings need to be provided for connecting and authenticating to the SIEM solution.

For Microsoft Sentinel you need to provide these settings:

![](<../../.gitbook/assets/image (41).png>)

* **Customer ID**: This value can be retrieved in Microsoft Sentinel under "Log Analytics Workspaces" --> "Agents Management" --> "Workspace ID".
* **Security Key**: This value can be retrieved in Microsoft Sentinel under "Log Analytics Workspaces" --> "Agents Management" --> "Primary Key".
* **URL**: This value is made up by the Customer ID and a fixed part: [https://\<Customer ID>.ods.opinsights.azure.com/api/logs?api-version=2016-04-01](https:/%3CCustomer\_ID%3E.ods.opinsights.azure.com/api/logs)

**Remark:** For Microsoft Sentinel as well as other SIEM vendors you might need to import the HTTPS certificates into transaction STRUST for the connection to work. [See here ](../../application-setup/troubleshooting/siem-certificates.md)for details.

**Remark**: For testing purposes or tuning it can be considered to only provide the SIEM settings later and first keep the Threats locally in the Protect4S TD solution.



After the Post-Installation processing is done, the application is ready to be used. The Protect4S Threat Detection solution is started via transaction: `/n/ui2/flp`, which opens the Fiori launch pad containing the Protect4S TD applications. Should the transaction timeout, please refresh the page again with the F5 key or set a higher value for SAP parameter **rdisp/plugin\_auto\_logout** using transaction: **RZ11**.

After running the Post installation wizard, refresh your browser cache (CTRL-F5) to make sure the application icons are displayed correctly.

Every menu Item selected will start in a new browser tab. When you have finished using an application, you may simply close the tab.
