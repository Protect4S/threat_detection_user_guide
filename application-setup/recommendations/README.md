---
description: Tips and tricks
---

# !Recommendations

This chapter covers best practices, tips and tricks to limit as many false positives as possible.\
With the provided recommendations this chapter will guide you configuring the parameters for each use case to detect, mitigate, and harden the security as a final result.

All general information and details for each use case is described in within solution and can be found under the Fiori Application "Use Case Information".

#### _Proceeding with the recommendations_

To proceed with the configuration, first it is suggested to have a knowhow about the capabilities and the usage of each Use Case and which dynamic data can be used to detect (possible) threats which you may then use to create a rule for that in the Allow Deny Policy application per use case per system, system role or all systems connected to the solution.

As a rule of thumb from the security perspective: the less authorization the more secure.

Once configured you are not quite done yet as it is advised to revisit the configuration once in a while to make sure that all configuration is still at what it should.\
__For example if someone left the company or has changed switched to a different function within the organization and his/her user is someone defined in one of the policy it should be removed from the solution as well.&#x20;

Do note that if any user is compromised immediate action should take place, eg. blocking the user one of them however is to remove it from any policy list in Threat Detection at its earliest. This way you can monitor the user closely to see whether the user gets re-used and misused again.

_Make sure not to mix up Allow and Deny policies with each other, using it incorrectly blindfolds the system._
