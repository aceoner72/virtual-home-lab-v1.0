## SETTING UP THE NETWORK ENVIRONMENT  
**Step 1: Set Up the Initial Topology**  
We will start wth two PCs, a 2960-switch, a 2911 router, and a server with DHCP

![Initial Topology](Step1-InitialTopology.png)
*Initially planned network*

**Step2: Set the IP Addresses**  
Manually set the IP address for the router and the server 
- Router: 192.168.1.1 / 24 | default gateway: 192.168.1.1    (Make sure it's turned on)
- Server: 192.168.1.2 / 24 | default gateway: 192.168.1.1

**Step 3: Set Up the DHCP Server**  
Click on the server, navigate to services, select DHCP
- Initialize a pool with default gateway: 192.168.1.1; starting address: 192.168.1.100 / 24; determine number of users
- Add the new pool and turn on the service
- **Make sure the default serverPool's subnet mask is 0.0.0.0 and the number of users is 0 or else it will conflict with our newly created pool** 

**Step 4: Test DHCP on the PCs**  
Go to each PC and configure the network to get an IP address from the DHCP server
- In the IP config settings, enable a DHCP assignment
- Can test assignment by pinging
- Double check default gateway was set


![DHCP Assignment](Step4-DHCP.png)
*DHCP address assignment for end devices*
