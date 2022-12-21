---
description: Satellite system settings
---

# RFC Gateway Log

The RFC Gateway Log in SAP systems stores events related to the RFC Gateway working. It is important that the RFC Gateway Log is switched on for all application servers and that the correct events are recorded. The RFC Gateway Log can be activated in transaction SMGW.

As a minimum, the parameter "**gw/logging**" needs to be activated via transaction RZ10. If your system has multiple instances, make sure to activate the parameter for all individual instance profiles or set the parameter in the default profile for system-wide activation. This parameter cannot be changed dynamically and requires a restart.



Since the default setting for the parameter only logs changes to security settings and rejected actions you need to change to value of the included actions to at least those represented by the letters **Z, S** and **E**. The meaning of these actions can be found below (also see SAP note [2527689](https://launchpad.support.sap.com/#/notes/2527689)):

(T): Network actions: Opening and closing network connections\
(**E**): Starting external programs\
(R): Registering/deregistering servers\
(**S**): Security settings and their changes (reloading files)\
(s) Only rejected secinfo and reginfo accesses; see also (Z) \
(M): Monitor commands\
(P): Dynamic changes to parameters\
(X): Start/stop/signals of the gateway\
(V): Creating and deleting conversation IDs\
(O): Opening RFC connections\
(C): Open/close/data traffic for RFC connections\
(**Z**): secinfo and reginfo accesses for which no rule applies



On top of those action you might need to activate additional actions based on your company's policies. For example the ACTION option for gateway logging with the value **SZMPTER** is required to capture security events, configuration changes, network actions, registration of servers and monitor commands. Make sure there is enough size in the logfile via the MAXSIZEKB option.

In more recent systems consider using parameter **rsau/integrity = 1** for additional protection of the RFC GW log. See SAP note [2033317](https://launchpad.support.sap.com/#/notes/2033317) for more information).
