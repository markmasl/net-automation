# net-automation
BUILDING NETWORK AUTOMATION SOLUTIONS online training

The virtual environment is running on EVE-NG, which stands for Emulated Virtual Environment fo Network, Security and DevOps Professtionals.
Environment is built out of 7 network virtual appliances. Naming:
1. Two IOS-XRv boxes as a DC gateways, running vrf's with BGP towards border leaves in each vrf.
2. A pair of Arista vEOS border leaves, running mc-lag. Which are connecting to DC GWs and some hosts on the downlinks. In the starting version of the lab, there is only one Cumulus host, but there is a plan to add F5 BIGIP virtual appliance, as well as virtual Paloalto FW 
3. A Cumulus virtual box, running as a host connecting to the mc-lag leaves. 
4. Another Cumulus box running for out-of-band mgmt purpose, interconnecting each host with mgmt interface, as well as having uplink to the Ansible host.

The plan is to automate following scenarious in the daily operations
1. Creating new vrf's between dc-gw and leaves, as well as enabling BGP sessions dc-gw<->leaf + leaf1<->leaf2 + dc-gw1<->dc-gw2
2. Creating vlans on the Arista vEOS leaves, adding to the mc-lag peer-link and downlink ports towards hosts. Including L3 SVI interfaces.
3. Creating vlans and SVI interfaces on the Cumulus virtual box. Creating bond interfaces.
4. Creating interfaces and vlans on the Paloalto and F5 BIGIP appliances. 

There is also a plan to cover some sources of the information that could be used for data gathering and using it for automation scripts.
