# Recommendations

### Sizing

**Workprocesses:**

In order for the Protect4S Threat Detection to function properly and in a timely manner, some sizing rules apply.

A general rule of thumb for the sizing of the Central Protect4S TD system is:

* 3 general dialog processes + 1 dialog process per connected system.

If for example 20 ABAP systems need to be connected, then the sum is like this:&#x20;

> 3 + 20 = 23 dialog work processes that need to be configured via the parameter `rdisp/wp_no_dia`.&#x20;

The above sum has some slack though. If the connected systems are a **non-prd** systems then you can roughly use, at a minimum, **50%** of that amount. For **PRD** systems this percentage is **80%** at a minimum. Specific sizing may apply depending on the number of events generated, the used hardware, number of users, etc. Fine-tuning for these specific situations might be needed.

**Memory:**

On the central Protect4S TD system, use **300 MB** per work process to estimate the needed memory. So for example if we take 80% of 23 processes (\~18 processes) and multiply that with 300 MB then the Protect4S TD application needs \~5,5 GB. This is apart from the OS, DB and other application needs. The above is a rough estimation and depends on the size of data to be read, settings of the read interval and number and type of connected systems.

Best practice is to connect a maximum of 180 SAP systems to one Protect4S worker.

### Use of HTTPS

We recommend to only use HTTPS (based on TLS 1.2 or higher) to connect to the Protect4S Threat Detection solution and to send data to SIEM to ensure the integrity of data being transferred.
