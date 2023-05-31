---
description: This page explains the use case policie attributes
---

# Use Case Policy attributes

### **Attribute legend:**

Below is a list of attributes that exist for the use case policies.

<table><thead><tr><th width="276">Attribute name:</th><th>Description of the attribute:</th></tr></thead><tbody><tr><td>Use Case ID</td><td>The unique use case identifier number. Use case policies are linked with each other.</td></tr><tr><td>Default</td><td>Indicates whether this policy is the initial shipped or not.</td></tr><tr><td>Threat Value Type</td><td>Indicates type of threat the use case detects.</td></tr><tr><td>Use Case Description</td><td>Human readable description of the use case.</td></tr><tr><td>Policy Description</td><td>Human readable description of the policy.</td></tr><tr><td>Additional Description</td><td>As the description is fixed in our solution it cannot be changed. However with this extra field customers can specify their own description if needed.</td></tr><tr><td>Scope</td><td>Type of scope this policy applies to. Possible values are: All Systems, System Role, System Group, Single System.</td></tr><tr><td>Case Sensitive</td><td>Indicates whether the values entered are case sensitive or not. For example, Function Module related use cases are case sensitive.</td></tr></tbody></table>



### Threat value attributes

Below is a list of attributes available as part of the Threat Value section.

<table><thead><tr><th width="284">Threat value attribute:</th><th>Description:</th></tr></thead><tbody><tr><td>Active</td><td>Use this option to activate or deactivate threat values. The Threat Values we have pre-defined cannot be removed. You can use this option to deactivate instead.</td></tr><tr><td>Threat Value</td><td>The Value that triggers the use case to send alert. For some use cases any value is considered a risk. In that case this this field won't be shown. </td></tr><tr><td>Risk</td><td>This field indicates the risk assigned when a threat gets created and send to SIEM.</td></tr><tr><td>Client Exception</td><td>Defines a SAP system client for a threat value exception. The value here is a single value but can be comma separated to exempt multiple clients in one line.</td></tr><tr><td>Client Exception Group</td><td>A group of clients defined in the Group application, this can be used to exclude a threat value for multiple clients at once via a group.</td></tr><tr><td>System</td><td>You can enter here the SAP SID or you can enter the Protect4S TD system number between brackets. The value here are single values and can be comma separated to create exceptions for multiple systems in one line.</td></tr><tr><td>System Exception Group</td><td>A group of systems defined in the Group application, this can be used to exclude a threat value for multiple systems at once.</td></tr><tr><td>Host Exception</td><td>Define a host/terminal for a threat exception. The value here can be either hostname, FQDN or ip address. The  host must correspond to what is shown in the audit log or other log. Wildcards can be used here. IP ranges however cannot be defined with hyphens. The values here are single values and can be comma separated to create exceptions for multiple clients in one line.</td></tr><tr><td>Host Exception Group</td><td>A group of hosts/terminals defined in the Group application, this can be used to exclude a threat value for multiple hosts at once.</td></tr><tr><td>Username Exception</td><td>Define a user here to create an exception for a threat. The value here are single values and can be comma separated to exempt multiple usernames in one line.</td></tr><tr><td>Username Exception Group</td><td>A group of users defined in the Group application, this can be used to exclude a threat value for multiple users at once.</td></tr><tr><td>Comment</td><td>This field can be used to add additional information about the exception.</td></tr></tbody></table>



### Risk value

The risk value per threat can be configured and changed. This risk will be passed to your SIEM solution to optionally apply certain rules you want there. If there are multiple entries with the same threat value, the risk can only be defined for the first threat.

### Wildcard usage

Wildcards can be used for exceptions. For _**Hosts**_ we have listed a few examples of wildcards that can be used for host exceptions.

The table is formatted like this: The first column is the explanation of the wildcard value that you enter in the 2nd column. The third column is how the TD application processes or sees these values. These are the values that are used as exceptions, preventing the creation of Threats.



<table><thead><tr><th>Explanation:</th><th width="210">Value entered in the policy configuration:</th><th>Processed exceptions:</th></tr></thead><tbody><tr><td>IP address with wildcard in an octet</td><td>10.2.1.2*</td><td><p>Below values for example are excluded with the wildcard value:</p><p>10.2.1.2</p><p>10.2.1.22</p><p>10.2.1.23</p><p>10.2.1.24</p><p>10.2.1.25</p><p>10.2.1.26</p><p>etc.</p></td></tr><tr><td>IP address with wildcard as a subset</td><td>10.2.1.*</td><td><p>10.2.1.1</p><p>10.2.1.2</p><p>10.2.1.13</p><p>10.2.1.22</p><p>10.2.1.23</p><p>10.2.1.24</p><p>10.2.1.25</p><p>10.2.1.26</p><p>etc.</p></td></tr><tr><td>Wildcard in a hostname</td><td>p4ssol*</td><td><p>p4ssoldev.p4s.com</p><p>p4ssolqua.p4s.com</p><p>p4ssolprd.xyz.com</p><p>p4ssolabc</p><p>etc.</p></td></tr><tr><td>Wildcard in a Fully Qualified Domain Name</td><td>*.p4s.com</td><td><p>p4ssoldev.p4s.com</p><p>p4ssolqua.p4s.com</p><p>p4ssolprd.p4s.com</p><p>p4shanatd.p4s.com</p><p>xyz.p4s.com</p><p>etc.</p></td></tr><tr><td>Wildcard for a hostname and the Top Level Domain (last part of the FQDN).</td><td>*.p4s.*</td><td><p>p4ssoldev.p4s.com</p><p>p4ssolqua.p4s.com</p><p>p4ssolprd.p4s.com</p><p>p4ssolsb.p4s.local</p><p>p4ssolsb.p4s.local</p><p>p4ssolprd.p4s.eu</p><p>etc.</p></td></tr></tbody></table>

### Escape Characters

See note [574914](https://launchpad.support.sap.com/#/notes/574914) and [2488648 ](https://launchpad.support.sap.com/#/notes/0002488648)for details about escape characters. For example if you want to use the specific value "SAP\*" to address the emergency user in a policy, you can use the value "SAP#\*".
