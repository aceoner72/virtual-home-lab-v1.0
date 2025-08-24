## NAT AND INTERNET ACCESS 

**Step 5: Simulate Internet Access Using a Router** 
Add another router to the topology that connect to the "home" network
- Set the IP addresses of the new port connections
  - Home router Gig 0/1: 203.0.113.2 / 24
  - ISP/Internet Gig 0/0: 203.0.113.1 / 24
  - 
![ISP/Internet Router](Step5-InternetRouter.png)
*Simulate Internet Access*

**Step 6: Configure a NAT**
Configure NAT for the home router using CLI 
- Configure Gig 0/0 interface:
  - enable (en)
  - configure terminal (conf t)
  - interface Gig 0/0 (in gig 0/0)
  - ip nat inside (LAN)
  - end
- Configure Gig 0/1 interface:
  - enable (en)
  - configure terminal (conf t)
  - interface Gig 0/0 (in gig 0/0)
  - ip nat outside (WAN)
  - end
- Apply a NAT overload
*(this allows multiple private IP addresses on a local network to share a single public IP address)*
  - enable (en)
  - configure terminal (conf t)
  - ip nat inside source list 1 interface gigabitEthernet 0/1 overload
  - end
- Test with a ping to 203.0.113.1 from a PC to confirm it worked

**Step 7: Simulate a Public Web Server**
Add a switch and a server to the Internet-side network 
