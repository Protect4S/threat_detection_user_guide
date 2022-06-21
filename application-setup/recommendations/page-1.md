---
description: Changes or Deactivation of Security Audit Log
---

# S-000010-01

#### Description

This use case detects changes or (de)activation of the SAP Security Audit Log (SAL).

#### Best practice

To minimize and avoid unwanted changes to the SAL configuration, make sure to limit the number of users that has access and authorizations to adjust the settings.

By having a scope which users have access to SAL and are able to alter settings it will help you fill out the policy. In case the authorizations and situation differs for each system it is advised to get a scope of users for each critical system that are to be connected to the Threat Detection solution.

To get an overview whom can access the SAL transactions, transaction SUIM can be used. Depending on which option you use in this transaction you can get an overview of all users or all roles first. Using the option to get an overview of users will also give you an overview of any users with _SAP\_ALL_. As a rule of thumb, any default SAP users and users with _SAP\_ALL_ and _SAP\_NEW_ should be monitored and it is important to keep in mind that having the authorization does not mean that one should change configurations at will. That means that these users should in general **not** be on the allow list.

#### Configuration

Policy 1003 can be used to define the users that can adjust the configuration without being supervised.
