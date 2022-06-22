# Prerequisites

### Protect4S TD Central System s**oftware version requirements**

There are minimal software version requirements for the central Protect4S Threat Detection system. Below mentioned software components should be installed on at least the version and Support Package level indicated (a higher version or support package is supported, not lower):

\| **Software Component** | **Version** | **Support Package** |

\| SAP\_BASIS | 752 | 0005 |

\| SAP\_UI | 754 | 0000 |

\| SPAM/SAINT | 752 | 0078 |

The SAPUI component has been tested and is supported as of SAPUI 7.54 Support Package 0007 and higher, but might also work on lower support package levels within the 7.54 version. In case of issues though, we recommend to install at least the above mentioned version of the SAPUI component.

### Time settings

Make sure that on all SAP systems in your landscape the setting of time is synchronised with a central time server (e.g. via the NTP protocol) and that other Operating System time-settings (e.g. Daylight Saving Time settings) are set to the default settings. We don't take into account the parameter _`zdate/DSTswitch_contloctime`_.

### Check active HTTPS service <a href="#check-that-http-s-service-is-active" id="check-that-http-s-service-is-active"></a>

Make sure that on the central Protect4S system at least one HTTPS service is active using transaction SMICM before continuing with the next step.See transaction: SMICM, Goto, Services \<Shift-F1>:

![SMICM HTTPS Service should be active](<../../.gitbook/assets/image (56) (1).png>)

### Enable SAP Gateway & Fiori Launchpad

Make sure that on the central Protect4S system the SAP Gateway and Fiori Launchpad are activated. This can be tested by starting the transaction `/n/ui2/flp`. The output should be an empty Fiori Launchpad or contain some tiles.

If the above is not the case, then use transaction STC01 to activate the below two tasks:

* SAP\_GATEWAY\_BASIC\_CONFIG
* SAP\_FIORI\_LAUNCHPAD\_INIT\_SETUP

<mark style="background-color:blue;">Also activate the SICF service:</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">**/sap/public/bc/uics/whitelist**</mark>

<mark style="background-color:blue;">****</mark>

### Monitored SAP systems s**oftware version requirements**

The monitored SAP systems should be running on SAP Netweaver release 7.40 or higher. Apart from that, there are no specific software version requirements.
