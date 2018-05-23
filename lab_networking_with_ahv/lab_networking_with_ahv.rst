.. _lab_networking_with_ahv:

-------------------------
Lab - Networking With AHV
-------------------------

Overview
++++++++

Here is where we provide a high level description of what the user will be doing during this module. We want to frame why this content is relevant to an SE/Services Consultant and what we expect them to understand after completing the lab.

Using Text and Figures
++++++++++++++++++++++

Setup user VM network
.................

In **Prism > VM**, click ** VM**, then click **Table**

Click **Network Config**
Click **User VM Interfaces**

Click **Create Network**

Fill out the following fields and click **Save**:

- **Name** - Primary
- **VLAN ID** - 0
- **Enable IP Address Management** - Checked
- **Network IP Address / Prefix Length** - 10.x.x.0/25
- **Gateway** - 10.21.XX.1
- **DNS Servers** - 10.21.253.10,10.21.253.11
- **Domain Search** - nutanixdc.local
- **Domain name** - nutanixdc.local
- **TFT Server** - empty
- **Boot File** - empty
- **Create Pool** - 10.21.XX.50-10.21.XX.120
- **Override DHCP Server** - unchecked  


Takeaways
+++++++++

- Here is where we summarize any key takeaways from the module
- Such as how a Nutanix feature used in the lab delivers value
- Or highlighting a differentiator
