---
description: Operating system user in the satellite system
---

# Operating System user

The Protect4S Threat Detection solution will be capable of checking conditions on the Operating System platform layer in the future using the SOAP interface of SAPControl.&#x20;

**For now this user is not mandatory and not needed to create for the satellite systems.**&#x20;

In order to authenticate, a valid operating system user/password combination for the satellite system must be provided in the System connection wizard.

Some operating system checks rely on the SAPcontrol **OSExecute** function, which can only be executed by the \<sid>adm user (the standard SAP system owner) or a new user that was cloned from \<sid>adm.

If this is allowed by your specific security policy, Protect4S recommends to supply the \<sid>adm user/password combination for the SAP Control connection when running the System connection wizard. In practice this means that this combination will be stored in the SAP secure store of the system where Protect4S Threat Detection is installed (as all other Protect4S users).

If using \<sid>adm is not allowed, you can use an operating system user other than \<sid>adm. For more details see [this](operating-system-user-other-than-less-than-sid-greater-than-adm.md) chapter.
