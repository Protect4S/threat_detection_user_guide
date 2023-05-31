# Post-installation processing

### Run the post-installation wizard <a href="#run-the-post-installation-wizard" id="run-the-post-installation-wizard"></a>

After the installation is done, run the post-installation wizard **in the client where Protect4S TD needs to run,** this cannot be done in client 000. The post-installation wizard is started by executing transaction: **/n/TDWO/PI**. The wizard will activate the [necessary SICF services](../troubleshooting/sicf-services.md) and will also prompt for the license installation. Since the applications are launched for the first time you might need to refresh them sporadically to see the content. When doing an upgrade you might not get all the below popups as some settings are already in place.

![](https://files.gitbook.com/v0/b/gitbook-legacy-files/o/assets%2F-M4DeA\_ch2aT\_DMIXtj1%2F-M4DeCFgK1Kor0XH90AI%2F-M4DeKsFHHQTfTDDaEVZ%2Fimage009.png?generation=1586162673680417\&alt=media)

### License installation <a href="#license-installation" id="license-installation"></a>

Protect4S TD needs a valid license in order to function. From the post-installation wizard you are prompted to install a valid license.&#x20;

#### Requesting a Protect4S TD license <a href="#requesting-a-new-protect4s-license" id="requesting-a-new-protect4s-license"></a>

Requesting a new Protect4S TD license can be done by selecting the option "Request license" in the License Administration application:



<figure><img src="../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

This will compose an email with a template. Please fill out the required information shown in the mail. This is required for Protect4S support to generate your license file (The installation and system number can be retrieved from transaction SLICENSE):

<figure><img src="../../.gitbook/assets/image (1) (8).png" alt=""><figcaption></figcaption></figure>

Send the mail to us and we will generate a license file for you. Should you have lost this file or never received it, please contact the Protect4S support team.

#### Uploading the license file

From the License Administration application press the INSTALL button: This will start a popup in which you can upload and save the license key file:

<img src="../../.gitbook/assets/image (2) (1).png" alt="" data-size="original">

After uploading and saving the license key file, you will be able to see the license in the overview in the License Administration:

<figure><img src="../../.gitbook/assets/image (1) (3).png" alt=""><figcaption></figcaption></figure>

After having installed the license: select **Yes**.

![](<../../.gitbook/assets/image (68) (1).png>)

### Application Settings

During the post-installation steps, inspect and update at least the mandatory fields in the Application Settings. Later, when using the Protect4S TD application you can configure more detailed [application settings](../../application-setup/application-settings.md) like for example the SIEM settings.

![](<../../.gitbook/assets/image (53) (1) (1).png>)

At least provide a **name** for the Worker ID, A **Company name** and a **background user** for the background jobs. This must be a user with the role **/TDWO/BACKGROUND\_EXECUTOR** and the Logon Language and Date Format settings for this user must be set to this default in SU01:

<figure><img src="../../.gitbook/assets/image (3) (3) (1).png" alt=""><figcaption></figcaption></figure>

After the Post-Installation processing is done, the application is ready to be used. The Protect4S Threat Detection solution is started via transaction: **`/n/ui2/flp`**, which opens the Fiori launchpad containing the Protect4S TD applications. Should the transaction timeout, please refresh the page again with the F5 key or set a higher value for SAP parameter **rdisp/plugin\_auto\_logout** using transaction: **RZ11**. After running the Post installation wizard, optionally refresh your browser cache (CTRL-F5) to make sure the application icons are displayed correctly.

Every menu Item selected will start in a new browser tab for many browsers (some browsers like Edge will open a new browser windows though). When you are finished using an application, you may simply close the tab or windows. Since the applications are launched for the first time you might need to refresh them sporadically to see the content.



On recent S4/HANA systems the Fiori Launchpad may show up empty, like in the below example:

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

In that case you case add the application by adding them to a new so called space or by adding them to the "My home" page. To do so click on the EDIT PAGE button as shown above and then on the "ADD TILE" button in the right upper corner:

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Select the Protect4S Application like below to have them shown in the "My Home" page:

<figure><img src="../../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>
