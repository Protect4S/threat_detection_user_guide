---
description: Operating system user in the satellite system
---

# Operating System User

The Protect4S Threat Detection solution will be capable of checking conditions on the Operating System platform layer and e.g. to read specific data sources using the SOAP interface of SAPControl.&#x20;

**An Operating System user is needed for this connection. This connection is not mandatory but needed for use cases that make use of data sources like the RFC Gateway log and others. Use cases that depend on these data sources can only be used once a SAPControl connection is created.**&#x20;

In order to authenticate, a valid operating system user/password combination for the satellite system must be provided in the System connection wizard. Some use cases rely on the SAPcontrol **OSExecute** function, which can only be executed by the \<sid>adm user (the standard SAP system owner) or a new user that was cloned from \<sid>adm (for non-Windows Operating Systems).

When allowed by your security policy, Protect4S recommends to supply the \<sid>adm user/password combination for the SAP Control connection when running the System connection wizard. In practice this means that this combination will be stored in the SAP secure store of the system where Protect4S Threat Detection is installed (as all other Protect4S users).

If using \<sid>adm is not allowed, you can use an operating system user other than \<sid>adm. For more details see [this](operating-system-user-other-than-less-than-sid-greater-than-adm.md) chapter.
