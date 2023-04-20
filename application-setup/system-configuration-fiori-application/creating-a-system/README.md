---
description: A walkthrough to create a system within Protect4S Threat Detection
---

# Creating a System

To be able to monitor satellite systems they need to be added to the Protect4S Central system. To create a system, open the System application from the Fiori Launchpad:

![](<../../../.gitbook/assets/image (52).png>)

Then click on the ![](<../../../.gitbook/assets/image (71) (1).png>)button. You should get a new screen displayed like below:

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

On the left side of the screen provide the system role, etc. On the right side you can set some system-specific settings:

**Threat Detection Interval in Seconds (180 seconds by default)**

This parameter defines the polling interval used to collect the data from this satellite system. Setting this parameter too low might lead to increased workload in the central and monitored system. Setting it too high can delay the detection of threats.

**Data Source Max. Read History in Seconds (900 seconds by default)**

This parameter is used to define the time Threat Detection looks back during the first read of data for this system (for example after starting up the system or after a connection issue has been fixed). Setting it higher might increase workload in the central and monitored system.

**Data Source Max. Seconds per Part (300 seconds by default)**

This parameter is used to split reading large amounts of data and splits up the read intervals in smaller pieces when needed. It defines the maximum amount of time in seconds that a Threat Detection read part uses to retrieve data from the satellite system. This is used to avoid large amount of data being collected in one read, which is especially noticeable if the "Data Source Max. Read History in Seconds" is set to a high value or in combination of many events occurred in case a system became unreachable.

**Activate new use cases automatically**

This flag is switched on by default and defines whether new use cases become active automatically.

**Health Check Settings**

With the "Create Threat" mark you can define whether health check messages are only created in the Messages application or if an additional threat is send to SIEM. By default this is not done.



**Example:**

With values set to the default settings, this means that Protect4S Threat Detection will read the history back to a maximum of 15 minutes (900 seconds). In that case of reading back 900 seconds it will split that into 3 different calls because of the Data Source maximum of 300 seconds per part. After a first read it will keep on collecting data on a 180 seconds interval.



### Creating Connections

Before saving the system, make sure to [create the needed connections](setting-up-connections/) to make the Threat Detection operational for this system.
