1. Set up an Ansible playbook.


1. Demo FHRP.


2. Configure a DHCP server.


3. Capture network traffic with Wireshark.


4. Deploy a WLC.


>Do a few simple projects that reinforce the basics. When you're ready, setup a network with one router and three layer 3 switches. Setup three VLANs and name them. One of those VLANs will be a management VLAN so you can SSH into your devices to administer them. That particular VLAN will NOT be VLAN 1. In fact, VLAN 1 will not be used at all.
  

  
The second VLAN is for a Call Center hosting 300+ PCs. The third VLAN is for an office staff off 195 people, their laptops and a few networked printers.
  

  
Create multiple links between your switches and configure trunking. Configure security on your access ports, and when I connect a PC to an access port, I want it to come up immediately, not take 30 seconds.
  

  
The management VLAN will run a Class B subnet. The other two VLANs will run Class A subnets. The link between the router and first switch will host a Class C subnet.
  

  
After you have it working properly, document it. If you can give that documentation to a co-worker of the same skill level as you, and they can recreate the project without much difficulty, then good job.
  

  
All of this can be done in Packet Tracer jhgfdsdfghjkl;
mn m,.
