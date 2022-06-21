---
description: Detect changes or (de)activation of the SAP Security Audit Log
---

# S-000010-01

#### Description

This use case detects changes or (de)activation of the SAP Security Audit Log (SAL).

#### Configuration

Policy 1003 can be used to define the users that can adjust the configuration without being supervised. This can be someone from the audit team you entrust or a specific user you entrust.

Do note that if the user is compromised that the user is at least removed from Threat Detection at its earliest. During the time the user is compromised any SAL changes will also not be seen.
