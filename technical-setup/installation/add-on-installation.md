# Add-on Installation

Protect4S Threat Detection is delivered as an SAP Add-On and must be installed using transaction SAINT in client 000 on the Central Protect4S TD system.

The Protect4S Threat Detection solution requires the Protect4S TD initial base package plus the latest Protect4S TD Support package. Support packages are non-incremental (**they contain all predecessors**) and can be merged into the installation queue to install Protect4S TD to the latest version in one SAINT run.

During the installation, a warning may state that the Base package or Support Package are not digitally signed, this is standard SAP behaviour (see also OSS Note [2645739](https://launchpad.support.sap.com/#/notes/2645739)), and the warning can be ignored. Protect4S customers can always check the downloaded Support Packages against the SHA256 checksum on the Protect4S website:

![Checking the checksum of a Protect4S downloaded file](<../../.gitbook/assets/image (67) (1).png>)

When the installation is finished in transaction SAINT, the Post-installation transaction **/n/TDWO/PI** must be executed \*\*\*\* in the productive client in which you use Protect4S TD. See the next chapter for details.
