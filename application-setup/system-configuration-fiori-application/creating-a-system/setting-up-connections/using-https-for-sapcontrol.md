---
description: Connecting to sapcontrol on the satellite systems with https
---

# Using HTTPS for SAPControl





![SAPControl setup](<../../../../.gitbook/assets/image (40).png>)

During the creation of the system, you can choose to use https for the sapcontrol connection (step 4).

By configuring the sapcontrol connections this way, the following requirements must be met.

#### Requirements

* HTTPS service active in SMICM on the system where VM is installed (permanent created via profile, not just dynamically activated in SMICM as it will be removed after a restart)
* PSE keystore ‘SSL client SSL Client (Anonymous)’  is activated in transaction STRUST
* HTTPS port is enabled of the P4 port 5<##>14 on the satellite systems
* Satellite OS certificates will have to be imported into the Anonymous PSE keystore on the system where Protect4S Threat Detection solution is installed.

In general the sapcontrol connection (sapstartsrv) is activated for both protocol http and https. Do confirm this in your situation.

#### Getting the certificate&#x20;

Certificate can be saved via a browser on a system that can reach this satellite system by navigating to the URL https://\<satellite hostname>:5<##>14 where ## is the instance number.

We'd suggest to save the certificate with base-64 x.509 format should you get the option to choose. The method how to save the certificate varies as it depends on what browser you use.

&#x20;

If the certificate is not yet signed by your infrastructure, we'd strongly suggest to have it signed.
