---
description: This page explains the use case policie attributes
---

# Use Case Policy attributes

### **Attribute legend:**

Below is a list of attributes that exist for the use case policies.

| Attribute name:        | Description of the attribute:                                                                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Use Case ID            | The unique Use Case identifier number. Use Case policies are linked with each other.                                                                   |
| Default                | Indicates whether this policy is the initial shipped or not.                                                                                           |
| Threat Value Type      | Indicates type of threat the Use Case detects.                                                                                                         |
| Use Case Description   | Human readable description of the use case.                                                                                                            |
| Policy Description     | Human readable description of the policy.                                                                                                              |
| Additional Description | As the description is fixed in our solution it cannot be changed. However with this extra field customers can specify their own description if needed. |
| Scope                  | Type of scope this policy applies to. Possible values are: All Systems, System Role, System Group, Single System.                                      |
| Case Sensitive         | Indicates whether the values entered are Case sensitive or not. For example, Function Module related Use Cases are case sensitive.                     |



### Threat value attributes

Below is a list of attributes available as part of the Threat Value section.

| Threat value attribute:  | Description:                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Active                   | Use this option to activate or deactivate threat values. The Threat Values we have pre-defined cannot be removed. You can use this option to deactivate instead.                                                                                                                                                                                                                      |
| Threat Value             | The Value that triggers the Use Case to send alert. For some use cases any value is considered a risk. In that case this this field won't be shown.                                                                                                                                                                                                                                   |
| Risk                     | This field indicates the risk assigned when a Threat gets created and send to SIEM.                                                                                                                                                                                                                                                                                                   |
| Client Exception         | Defines a SAP system client for a threat value exception. The value here is a single value but can be comma separated to exempt multiple clients in one line.                                                                                                                                                                                                                         |
| Client Exception Group   | A group of clients defined in the Group application, this can be used to exclude a threat value for multiple clients at once via a group.                                                                                                                                                                                                                                             |
| System                   | You can enter here the SAP SID or you can enter the Protect4S TD system number between brackets. The value here are single values and can be comma separated to create exceptions for multiple systems in one line.                                                                                                                                                                   |
| System Exception Group   | A group of systems defined in the Group application, this can be used to exclude a threat value for multiple systems at once.                                                                                                                                                                                                                                                         |
| Host Exception           | Define a host/terminal for a threat exception. The value here can be either hostname, FQDN or ip address. The  host must correspond to what is shown in the audit log or other log. Wildcards can be used here. IP ranges however cannot be defined with hyphens. The values here are single values and can be comma separated to create exceptions for multiple clients in one line. |
| Host Exception Group     | A group of hosts/terminals defined in the Group application, this can be used to exclude a threat value for multiple hosts at once.                                                                                                                                                                                                                                                   |
| Username Exception       | Define a user here to create an exception for a threat. The value here are single values and can be comma separated to exempt multiple usernames in one line.                                                                                                                                                                                                                         |
| Username Exception Group | A group of users defined in the Group application, this can be used to exclude a threat value for multiple users at once.                                                                                                                                                                                                                                                             |
| Comment                  | This field can be used to add additional information about the exception.                                                                                                                                                                                                                                                                                                             |



### Risk value

The risk value per threat can be configured and changed. This can be used in your SIEM solution to apply certain rules you want there. If there are multiple entries with the same Threat Value, the risk can only be defined for the first threat.

### Types of Policies

There are two kind of Use Case policy.

1. Use Case with no known Threat Value
   * Any Policy that considers everything to be a threat does not have a Threat Value, for example debugging detection Use Case.
2. Use Case with known Threats that can be pre-defined
   * Policies with known Threats such as certain table or transactions have a Threat Value in the Use Case. These can be recognized with a red column which stands for Threat Value.

### Wildcard usage

Wildcards can be used for exceptions. For _**Hosts**_ we have listed a few examples of wildcards that can be used for host exceptions.

The table is formatted like this: The first column is the explanation of the wildcard value that you enter in the 2nd column (labeled as Exception values). The third column is how the TD application processes or sees these values. These are the values that are excluded preventing the creation of Threats.

See note [574914](https://launchpad.support.sap.com/#/notes/574914) and [2488648 ](https://launchpad.support.sap.com/#/notes/0002488648)for details. For example if you want to use the specific value "SAP\*" to address the emergency user in a policy you can use the value "SAP#\*".

| Explanation:                                                              | Value entered in the policy configuration: | Processed exceptions:                                                                                                                                                           |
| ------------------------------------------------------------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IP address with wildcard in an octet                                      | 10.2.1.2\*                                 | <p>Below values for example are excluded with the wildcard value:</p><p>10.2.1.2</p><p>10.2.1.22</p><p>10.2.1.23</p><p>10.2.1.24</p><p>10.2.1.25</p><p>10.2.1.26</p><p>etc.</p> |
| IP address with wildcard as a subset                                      | 10.2.1.\*                                  | <p>10.2.1.1</p><p>10.2.1.2</p><p>10.2.1.13</p><p>10.2.1.22</p><p>10.2.1.23</p><p>10.2.1.24</p><p>10.2.1.25</p><p>10.2.1.26</p><p>etc.</p>                                       |
| Wildcard in a hostname                                                    | p4ssol\*                                   | <p>p4ssoldev.p4s.com</p><p>p4ssolqua.p4s.com</p><p>p4ssolprd.p4s.com</p><p>etc.</p>                                                                                             |
| Wildcard in a Fully Qualified Domain Name                                 | \*.p4s.com                                 | <p>p4ssoldev.p4s.com</p><p>p4ssolqua.p4s.com</p><p>p4ssolprd.p4s.com</p><p>p4shanatd.p4s.com</p><p>p4sfrunsb.p4s.com</p><p>etc.</p>                                             |
| Wildcard for a hostname and the Top Level Domain (last part of the FQDN). | \*.p4s.\*                                  | <p>p4ssoldev.p4s.com</p><p>p4ssolqua.p4s.com</p><p>p4ssolprd.p4s.com</p><p>p4ssolsb.p4s.local</p><p>p4ssolsb.p4s.local</p><p>p4ssolprd.p4s.eu</p><p>etc.</p>                    |

_Notice, hostname here are just examples, they are not actual hostnames of any of our system._
