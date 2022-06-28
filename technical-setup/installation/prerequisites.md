# Prerequisites

### Protect4S TD Central System s**oftware version requirements**

There are minimal software version requirements for the central Protect4S Threat Detection system. Below mentioned software components should be installed on at least the version and Support Package level indicated (a higher version or support package is supported, not lower):

| Software Component | Version | Support Package |
| ------------------ | ------- | --------------- |
| SAP\_BASIS         | 752     | 0005            |
| SAP\_UI            | 754     | 0000            |
| SPAM/SAINT         | 752     | 0078            |

The SAPUI component has been tested and is supported as of SAPUI 7.54 Support Package 0007 and higher, but might also work on lower support package levels within the 7.54 version. In case of issues though, we recommend to install at least the above mentioned version of the SAPUI component.

### Time settings

Make sure that on all SAP systems in your landscape the setting of time is synchronized with a central time server (e.g. via the NTP protocol) and that other Operating System time-settings (e.g. Daylight Saving Time settings) are set to the default settings. We don't take into account the parameter _`zdate/DSTswitch_contloctime`_.

If you are encountering difficulties regarding this topic, please find more information [here](../troubleshooting/timezone-differences.md).&#x20;

### Check active HTTPS service <a href="#check-that-http-s-service-is-active" id="check-that-http-s-service-is-active"></a>

Make sure that on the central Protect4S system at least one HTTPS service is active using transaction SMICM before continuing with the next step. See transaction: SMICM, Goto, Services \<Shift-F1>:

![SMICM HTTPS Service should be active](<../../.gitbook/assets/image (56) (1).png>)

### Enable SAP Gateway & Fiori Launchpad

Make sure that on the central Protect4S system the SAP Gateway and Fiori Launchpad are activated. This can be tested by starting the transaction `/n/ui2/flp`. The output should be an empty Fiori Launchpad or contain some tiles.

If the above is not the case, then use transaction STC01 to activate the below two tasks:

* SAP\_GATEWAY\_BASIC\_CONFIG
* SAP\_FIORI\_LAUNCHPAD\_INIT\_SETUP

<mark style="background-color:blue;">Also activate the SICF service:</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">**/sap/public/bc/uics/whitelist**</mark>

### Threat Detection Secure Storage

Before you proceed adding systems to Protect4S Threat Detection, please make sure that the SAP Secure Store of the Threat Detection system itself is properly protected. The Secure store key phrase should not be set to the default key. This can be checked using SAP transaction SECSTORE:

![Checking to see if the Secure Store has a default key](<../../.gitbook/assets/image (24).png>)

In the above case, change the default keyphrase and consider implementation of the following SAP OSS Notes:

[1902258 - Secure Storage in the Database Key File Tool](http://service.sap.com/sap/support/notes/1902258)

[1902611 - Potential information disclosure relating to BC-SEC](http://service.sap.com/sap/support/notes/1902611)\


### SAP satellite systems s**oftware version requirements**

The SAP satellite systems should be running on SAP Netweaver release 7.40 or higher. Apart from that, there are no specific software version requirements.
