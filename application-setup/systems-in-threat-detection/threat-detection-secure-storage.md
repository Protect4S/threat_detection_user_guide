# Threat Detection Secure Storage

Before you proceed adding systems to Threat Detection, please make sure that the SAP Secure Store of the Threat Detection system itself is properly protected. The Secure store key phrase should not set to the default key. This can be checked using SAP transaction SECSTORE:

![Checking to see if the Secure Store has a default key](<../../.gitbook/assets/image (21).png>)

**Transaction SECSTORE default Key warning**

In this case, consider implementation of the following SAP OSS Notes:

[1902258 - Secure Storage in the Database Key File Tool](http://service.sap.com/sap/support/notes/1902258)

[1902611 - Potential information disclosure relating to BC-SEC](http://service.sap.com/sap/support/notes/1902611)
