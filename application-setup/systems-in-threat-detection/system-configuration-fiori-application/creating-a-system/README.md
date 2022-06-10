---
description: A walkthrough to create a system within Protect4S Threat Detection
---

# Creating a system

To create system, open the System Fiori application.

Click on create ![](<../../../../.gitbook/assets/image (71) (1).png>)

You should get a new screen displayed like below:

On the left side the System Attributes are defined (System Role, System Description, Business Relevance, Data Sensitivity). All these information will be parsed to the Security Information and Event Management (SIEM) system depending on which you have linked Threat Detection to.\
For this reason it is important to be thoughtful how these should be defined.

![Configuring a new system](<../../../../.gitbook/assets/image (61) (1) (1).png>)

On the right hand side the Threat Detection settings can be defined specifically how you want the Protect4S Threat Solution to behave for this particular system.

For each system you setup you can define their own Threat Detection Settings. The proposed initial values can be changed per your needs.

![Threat Detection Settings](<../../../../.gitbook/assets/image (42).png>)

**Threat Detection Interval in Seconds**

This parameter defines the interval used to collect the data from this satellite system. Setting this parameter too low might keep work processes being occupied in the central and monitored system. Setting it too high can cause your monitoring to be delayed.

**Data Source Max. Read History in Seconds**

This parameter is used to define the time Threat Detection looks back during the first read of data for this system or after a connection issue has been fixed. The value is set to 900 seconds (15 minutes) by default.

**Data Source Max. Seconds per Part**

This parameter is used to split reading large amounts of data. It defines the maximum amount of time in seconds that a Threat Detection read uses to retrieve data from the satellite system. This is used to avoid large sum data being collected at once which is especially noticeable if the "Data Source Max. Read History in Seconds" is set to a high value or in combination of many events occurred during the time in which the system became unreachable.

**Example:**

With the initial settings it means that Threat Detection will read the history back up to 15 minutes (900 seconds) but for each time 180 seconds it will not read more than 5 minutes (300 seconds) of history at once.
