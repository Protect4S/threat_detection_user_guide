# Protect4S TD dataobjects

Within the Protect4S solution there are several data objects that produce data that over time might grow big. It is therefore good to know what options there are to reduce this data while maintaining enough information to work with.

### Framework Messages&#x20;

The Protect4S application produces Framework messages that can be use for troubleshooting purposes. The number of messages can grow fast for example in the case of connection issues to the monitored SAP systems. By default the messages will be stored for 180 days as can be configured in the Application Settings:

![Framework Messages default storage in days](<../../.gitbook/assets/image (11).png>)

In the event you want to reduce the amount of days that these messages are stored it can be considered reducing this value.



### Events

The Protect4S events received from the monitored SAP systems are stored for some time for troubleshooting and forensic purposes. The number of events can grow fast depending e.g. on the amount of use cases activated and datasources being activated for the monitored SAP systems. By default the events will be stored on the Central Protect4S TD system for 2 hours as can be configured in the Application Settings:

![](<../../.gitbook/assets/image (69).png>)

In the event you want to reduce the amount of hours that these events are stored it can be considered reducing this value.



### Threats

The Protect4S threats created by the Protect4S TD Solution are stored for some time for consulting and forensic purposes. The number of threats can grow fast depending e.g. on the amount of use cases activated for the monitored SAP systems. By default the threats will be stored on the Central Protect4S TD system for 180 days as can be configured in the Application Settings:

![](<../../.gitbook/assets/image (7).png>)

In the event you want to reduce the amount of days that these threats are stored it can be considered reducing this value.
