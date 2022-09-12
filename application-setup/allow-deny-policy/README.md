---
description: Use Case Policy configuration
---

# Use Case Policies

If you have been granted the security configurator role or the administrator role, you can access the Use Case Policy Fiori tile. Please visit [this](../system-configuration-fiori-application/users-and-authorizations/authorizations.md) page for more details regarding the authorizations.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Use Case Policy Configuration</p></figcaption></figure>

In this application you can configure use cases for example to minimise false positives.&#x20;

No SAP landscape is the same and use cases often need some tweaking and tuning in order to be effective, to limit false positives and add specific data for your situation. All fields are wildcard-enabled and you can use the hash symbol (#) to escape characters. See note [574914](https://launchpad.support.sap.com/#/notes/574914) & [2488648 ](https://launchpad.support.sap.com/#/notes/0002488648)for details. For example if you want to use the specific value "SAP\*" to address the emergency user in a policy you can use the value "SAP#\*".

If you add values to the exception list, then no Threat will be created. Below overview lists the attributes for the use case policies:

### Example of wildcard usage

Wildcards can be used for exceptions. For _**Hosts**_ we have listed a few examples of wildcards that can be used for host exceptions.

The table is formatted like this: The first column is the explanation of the wildcard value that you enter in the 2nd column (labeled as Exception values). The third column is how the TD application processes or sees these values. These are the values that are excluded preventing the creation of Threats.&#x20;



| Explanation:                                                              | Value entered in the policy configuration: | Processed exceptions:                                                                                                                                            |
| ------------------------------------------------------------------------- | ------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IP address with wildcard in an octet                                      | 10.2.1.2\*                                 | <p>Below values for example are excluded with the wildcard value:</p><p>10.2.1.2</p><p>10.2.1.22<br>10.2.1.23<br>10.2.1.24<br>10.2.1.25<br>10.2.1.26<br>etc.</p> |
| IP address with wildcard as a subset                                      | 10.2.1.\*                                  | <p>10.2.1.1<br>10.2.1.2<br>10.2.1.13<br>10.2.1.22<br>10.2.1.23<br>10.2.1.24<br>10.2.1.25<br>10.2.1.26<br>etc.</p>                                                |
| Wildcard in a hostname                                                    | p4ssol\*                                   | <p>p4ssoldev.p4s.com<br>p4ssolqua.p4s.com<br>p4ssolprd.p4s.com</p><p>etc.</p>                                                                                    |
| Wildcard in a Fully Qualified Domain Name                                 | \*.p4s.com                                 | <p>p4ssoldev.p4s.com<br>p4ssolqua.p4s.com<br>p4ssolprd.p4s.com</p><p>etc.</p>                                                                                    |
| Wildcard for a hostname and the Top Level Domain (last part of the FQDN). | \*.p4s.\*                                  | <p>p4ssoldev.p4s.com<br>p4ssolqua.p4s.com<br>p4ssolprd.p4s.com</p><p>p4ssolsb.p4s.local<br>p4ssolsb.p4s.local<br>p4ssolprd.p4s.eu</p><p>etc.</p>                 |

_Notice, hostname here are just examples, they are not actual hostnames of any of our system._
