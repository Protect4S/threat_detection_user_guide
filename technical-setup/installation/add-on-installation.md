# Add-on Installation

Protect4S Threat Detection is delivered as a SAP Add-On and must be installed using transaction SAINT in client 000 on the Central Protect4S Threat Detection system.

The Protect4S Threat Detection solution requires the Protect4S TD initial base package plus the latest Protect4S TD support package. Support packages are non-incremental (since the latest SP contains all predecessors) and can be merged into the installation queue to install Protect4S TD to the latest version in one SAINT run.

During the installation, a warning may state that the Base package or Support Package is not digitally signed, this is standard SAP behaviour (see also OSS Note [2645739](https://launchpad.support.sap.com/#/notes/2645739)), and the warning should be ignored. Protect4S customers can always check the downloaded support packages against the SHA256 checksum on the Protect4S website:

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Checking the checksum of a Protect4S package</p></figcaption></figure>

When the installation is finished in transaction SAINT, the Post-installation transaction **/n/TDWO/PI** must be executed in the productive client in which you use Protect4S TD. See the next chapter for details.
