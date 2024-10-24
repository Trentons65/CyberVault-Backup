**DHCP Conflicts (IPv4 only)** - 
- DHCP server uses pings to prevent
- Hosts use gratuitous ARP to avoid duplication (can not use discarded addresses until resolved)
**Automatic Private IP Addressing (APIPA)** - IP hosts use if DHCP is unavailable
- IP range (169.254.0.1 -> 169.254.255.254)
- Class B mask (255.255.0.0)
**Transport Layer (Host-to-Host)** - Shields upper-level applications from network complexities. Uses two protocols:
1. Transmission Control (TCP)
2. User Datagram (UDP)
**TCP** -
- Takes application data and breaks it into segments that are numbered and sequenced
- Virtual circuit is created between clients before transmission (Connection-Oriented)
- Full-duplex, reliable, and accurate but has costly overhead (Header of 20-24 bytes)
Structure -
1. Source port (16-bit)
2. Destination port (16-bit)
3. Sequence # (32-bit)
4. Acknowledgement # (32-bit)
5. Header length (4-bit)
6. Reserved
7. Code bits/flags - functions for setup & termination of sessions
8. Window (16-bit) - size sender is willing to send
9. Checksum (16-bit) - cyclic redundancy check (CRC)
10. Urgent (16-bit) - offset from current sequence # if set
11. Options (0/multiples of 32-bit)
12. Data

**UDP** -
- Scaled down version of TCP w/ less overhead 
- Should be used when application handles reliability
- Doesn't sequence segments or perform checks
- Connection-less Protocol

**Internet Protocol (IP)** - IP receives segments from transport layer & fragments into packets if necessary reassembling on receiving

**IP Protocols** 
- ICMP (1)
- IP in IP (4)
- TCP (6)
- UDP (17)
- EIGRP (88)
- OSPF (89)
- IPv6 (40)
- GRE (47)
- L2TP (115
  ![[Attachments/ip_header.jpg]]
**ICMP** - Management protocol & messaging service provider
- Can provide hosts w/ information about problems
	- Destination unreachable
	- Buffer full/source quench - Router memory buffer is full
	- Hops/time exceeded
- Encapsulated w/in packets
**ARP** - Finds MAC address of host from IP by sending broadcast to domain. (Resolves IP to MAC)
**Hexadecimal** -

| 0 | 0000 |
| ---- | ---- |
| 1 | 0001 |
| 2 | 0010 |
| 3 | 0011 |
| 4 | 0100 |
| 5 | 0101 |
| 6 | 0110 |
| 7 | 0111 |
| 8 | 1000 |
| 9 | 1001 |
| A | 1010 |
| B | 1011 |
| C | 1100 |
| D | 1101 |
| E | 1110 |
| F | 1111 |

**Life of a Packet** -
- ARP request = Broadcast (FF:FF:FF:FF:FF)
- ARP reply = Unicast reply

1. Router looks for destination network in routing table
2. Router uses ARP to find MAC of destination based on IP.
3. Adds ethernet header with source MAC and destination MAC found from ARP reply.
4. Packet sent to Next hop
5. Removes ethernet header

## Troubleshooting Steps
1. Ping loopback (127.0.0.1)
	   Failure indicates IP stack failure -> Reinstall TCP/IP on host
2. Ping local host
	Failure indicates problem with NIC
3. Ping default gateway
	Failure indicates local physical problem 
4. Ping remote server
	Failure indicates layer 1/2 DNS problem

### Troubleshooting Commands

| Command | Function | OS |
| ---- | ---- | ---- |
| ping |  | Cisco/Windows |
| traceroute |  | Cisco |
| tracert |  | Windows |
| arp -a | Returns ip to MAC mapping | Windows |
| sh(ow) ip arp | Returns ip to MAC mapping | Cisco |
| ipconfig |  | Windows |
| ifconfig |  | Linux |
| ipconfig getifaddr en0/1 |  | Windows |
| curl ifconfig.me |  | Linux |
| curl ipecho.net/plain ; echo |  | MAC |
|  |  |  |
|  |  |  |
|  |  |  |
**Network Protocol Requirements**
- Encoding (Convert to acceptable form)
- Formatting & encapsulation
- Size
- Timing (Flow control, Response timeout, Access)
- Delivery options (Uni, Multi, & Broadcast)

## Internet Standards

**Internet Society (ISOC)** - Promote open internet development & evolution
**Internet Architecture Board (IAB)** - Internet standard management & development
**IETF** - Engineering
**IRTF** - Research
**ICANN** - IP allocation, info assignment, & coordination
**IANA** - Oversee & manage IP allocation, domain name & protocol identifiers
**Institute of Electrical and Electronic Engineers (IEEE)** - 
- Creates standards in power & energy, healthcare, telecommunications, & networking
**Electronic Industries Alliance (EIA)** - 
- Standards for electrical wiring, connections, & 19-inch racks
**Telecommunications Industry Association (TIA)** - 
- Standards for radio equipment, cellular towers, VOIP devices, satellite communications, etc.
**ITU-T** - Standards for video compression, IPTV, & broadband communications

## OSI & TCP/IP Models
![[Attachments/PROTOCOLS2.jpg]]

### Physical Layer Role

- Creates signals that represent the bits in each frame on to media

**Logical Link control (LLC)** - 
- Software implementation
- Used by data link to communicate w/ upper levels
### Ethernet Frames

- Operates at physical & data link layers

**LLC** - 802.2 (IEEE) Identify network layer (Enables IPv4 & IPv6 to utilize same interface & media | Adds layer 2 data to network protocol data)
**MAC** - 802.3 (IEEE) Data encap, protocol, media access control, & data link

**Frame Size** -
- Min - 64 bytes (Collision fragment)
	Doesn't include preamble
- Max - 1518 bytes (Jumbo frames)
![[Attachments/Pasted image 20240103202450.png]]
Nic examines destination MAC & compares to RAM

**Unicast MAC address**
- **Address resolution protocol (ARP)** -> IPv4
- **Neighbor discovery (ND)** -> IPv6 

**Broadcast MAC address**
- Destination MAC address of FF:FF:FF:FF:FF:FF
- Flooded out all Ethernet ports except incoming (Not forwarded by router)

**Multicast MAC address**
- IPv4 -> 01-00-5E
- IPv6 -> 33-33

## Spanning Tree Protocol (STP)

### MAC 
- Multicast dest MAC when data is not IP
- All frame IP address require MAC for casting
- Layer 2 switches use MAC addresses to make forwarding decisions
- Switches examine source MAC address & port #. It keeps entry for **5 Minutes** 
- If destination MAC address is unicast, switch matches to entry in address table
### Frame forwarding methods
**Store-and-Forward** - 
-  Receives entire frame and computes the CRC then looks up destination address.
- Required for QoS analysis (VOIP)
**Cut-through** - forwards frame before it is entirely received. Has two variants.
- *Fast-forward switching* - Forwards immediately after reading destination address. Destination NIC discards faulty packets
-  *Fragment-Free switching* - Stores & checks first 64 bytes before forwarding

### Memory Buffering
**Port-based memory** - Frames stored in queues linked to specific in/outgoing ports. Single frame can cause backup in memory
**Shared memory** - Frames deposited into common memory buffer (dynamically allocated) can receive and send frames on different ports. 

### Duplex Settings
**Auto-MDIX** - Detects cable & configs interface accordingly
**Full-duplex** - Both ends can send & receive simultaneously
**Half-duplex** - Only one end can send at a time

## Subnetting
### Classless Inter-Domain Routing (CIDR)
***Introduced by IEFT***

| CLASS | IPv4 Network/ Host | IP range |
| ---- | ---- | ---- |
| A | 0XXXXXXX | (0-127) /8 |
| B | 10XXXXXX | (128-191) /16 |
| C | 110XXXXX | (192-223) /24 |
| D | 1110XXXX | (224-239)* |
| E | 1111XXXX | (240-255)* |
****Special Devices

**IANA** - Assigns IPv4 networks

## Chapter 5 - Routing

### Routers

**What router needs to route packets
1. Destination address
2. Neighbor routers to discover remote routers
3. All possible routes to all remote networks
4. Best route to remote networks
5. Maintain & verify routing info

**Static routing** - Hand input manually into routing table
**Dynamic routing** - Protocol communicates to neighboring routers to build strong routing table
***Combination used in most networks

**Longest match rule** - IP scans routing table to find longest match compared to destination address of a packet.

### Routing steps
1. ICMP creates an echo request payload (alphabet in data)
2. ICMP hands payload to IP creating a packet that contains source & destination IP and protocol field at a min
3. IP determines whether destination IP is local/remote
4. Remote network bound traffic is sent to the default gateway (Windows Registry)
5. Because hosts on local networks use layer 2 to communicate, Packet must be framed and sent to MAC of router
6. ARP cache checked to find MAC of default gateway 
	ARP broadcast sent out if not found in cache
7. Frame is generated
	Destination MAC, source MAC, ether-type, packet, FCS of CRC
8. Frame gets handed down to physical medium one bit at a time
9. Every device in collision domain receives bits and build the frame. Each device runs CRC & checks against FCS -> dest MAC -> ether-type
10. Packet is pulled from frame then handed to protocol in ether-type field and given to IP
11. IP receives packet and checks IP destination address 
12. Routing table must have entry on remote networks or they will be discarded 
13. Packet sent to exit interface
14. Router packet-switches packet to buffer 
15. Buffer needs to know MAC address of destination host (Checks ARP)
16. Data link layer creates frame which is handed to physical layer
17. Destination host runs CRC -> MAC -> Ether-type checks
18. IP receives packet and runs CRC -> MAC -> protocol
19. Payload is handed to ICMP -> discards -> creates reply
20. Packet sent back to source device in reverse order |^|
**Destination unreachable** - Error on way to destination
**Request timed out** - Error on way back from destination
21. Packet is switched to interface ethernet 0
22. ARP checked again for source host
23. Data link layer builds new frame and sends out at layer 1
24. Packet handed to IP at network layer
25. ICMP acknowledges it receives reply & attempts process 3 more times

### Routing commands

#### DHCP commands
	Router(config)# ip dhcp excluded-add
	Router(config)# ip dhcp pool (NAME)
		Router(dhcp-config)# network (IP) (mask)
		Router(dhcp-config)# default-router (DefaultGate)
		Router(dhcp-config)# dns-server (IP)
	Router(config)# ip helper-add;
#### Static routing commands
	Router(config)# ip route (destination-IP)(mask)(next hop)(AD)(perm)
#### RIP routing commands
	Router(config)# router rip
		Router(config-router)# network (IP)
		Router(config-router)# version 2
		Router(config-router)# no auto-summary
	Router(config)# passive-interface FastEthernet 0/1
		Prevents RIP update propagation	
#### OSPF routing commands
	Router(config)# router ospf (process ID) 0 = backbone
		Router(config-router)# network (IP)(wildcard mask)
		Router(config-router)# area (decimal/IP)
	Router(config)# ip route 0.0.0.0 0.0.0.0 (int)
		Router(config-router)# default-information originate
	Always config loopback interface for active int
		Router(config)# int loop 0
			Router(config-line)# ip add (IP)
		Router(config)# router ospf
			Router(config-router)# router-id 233.255.255.254
			Router(config-router)# do clear ip ospf process
#### Switch security commands
	Switch(config-int)# switchport mode access
	Switch(config-int)# switchport port-security
	Switch(config-int)# switchport port-security mac-add sticky
	Switch(config-int)# switchport port-security maximum 2
	Switch(config-int)# switchport port-security vio shutdown
**Saves two MAC addressess coming into port. All others shut port**

	Switch(config-int)# switchport port-security violation restrict
	Switch(config-int)# switchport port-security mac-add (MAC)
**Only allows one MAC and drops packets from all other sources**

#### VLAN commands
	Switch(config)# vlan (1-4094(up to 1001 in most cases))
	Switch(config)# vlan name (NAME)
	
	Switch(config-int)# switchport mode access
	Switch(config-int)# switchport mode dynamic auto - old
	Switch(config-int)# switchport mode dynamic desirable - use
	Switch(config-int)# switchport mode trunk
		Switch(config-int)# switchport trunk allowed vlan (VLAN)
		Switch(config-int)# switchport trunk native vlan (#)
	Switch(config-int)# switchport nonegotiate - stop DTP
#### Inter-VLAN Routing commands
	Router(config)# int f0/0.X 
		Router(config-int)# encap dot1q
**Each VLAN should be in different subnet
### Static routing 

**Pros**
1. No overhead on router CPU
2. No bandwidth usage between routers
3. Adds security
**Cons**
1. Admin needs high level understanding of infrastructure 
2. Network growth is tedious
3. Not feasible for large networks

***Routing protocol basics***
**Administrative Distance** - Route w/ lowest metric is placed on routing table. If both routes share AD, the protocol will load-balance

| Route Source        | Default AD       |
| ------------------- | ---------------- |
| Connected Interface | 0                |
| Static route        | 1                |
| External BGP        | 20               |
| EIGRP               | 90               |
| OSPF                | 110              |
| RIP                 | 120              |
| External EIGRP      | 170              |
| Internal BGP        | 200              |
| unknown             | 255 (Never used) |
### Routing Information Protocol (RIP)
- RIP sends the complete routing table out of all active interfaces every 30 seconds
- Has default hop count of 15
- Classful routing
- Classless routing/ Prefix routing
- Used on legacy devices but should be translated to up-to-date protocols

## Chapter 6 - Open Shortest Path First (OSPF)

**OSPF features**
1. Allows creation of areas & autonomous systems
2. Minimizes routing update traffic
3. Highly flexible, versatile, and scalable
4. Supports VLSM/CIDR
5. Unlimited hop count 
6. Open standard
OSPF is a link-state routing protocol

**Reasons to implement**
- Decrease routing overhead 
- Speed up convergence
- Confine network instability to single areas of the network

***Terminology***
**Link** -
- Network/router interface assigned to any network
**Router ID** -
- IP address used to identify router name 
- Highest IP address of all configured loopback of router int -> highest of all active physical
**Neighbor** - 
- Two or more routers that have common interface on network. Area ID, stub area flag, pass, hello & dead int
**Adjacency** -
- Relationship between two OSPF routers that permits exchange of route updates (opposite side of connection)
**Designated router** - 
- Elected when OSPF routers are connected to same broadcast network
- Minimizes number of adjacencies formed & publicizes routing info 
- Router priority level -> Router ID used to break ties
**Backup designated router** - 
- Hot standby for the DR on broadcast, or multi-access, links. Receives all routing updates but doesn't disperse LSA updates
**Hello protocol** - 
- Provides dynamic neighbor discovery and maintains those relationships. Hello packets & link state advertisements (LSAs) maintain topological database 
- Multicast address: 224.0.0.5
**Neighborship database** - 
- List of all OSPF routers that have seen hello packets.
- Details (Router ID & state) are maintained here
**Topological database** - 
- Information from LSAs received on network
- Used to compute shortest path to each network
**Link state advertisement (LSA)**
- OSPF packet containing link-state and routing info shared among OSPF routers. 
- Only sends packets to established adjacency
**OSPF areas** - 
- Grouping of contiguous networks and routers that share a common area ID 
- Different interfaces can have different area IDs even on same router
**Broadcast (multi-access)** - 
- Allow multiple devices to connect to the same network. 
- DR & BDR must be elected on OSPF networks
- Hello packets sent every 10 minutes
**Nonbroadcast multi-access** - 
- Frame relay, X.25, & ATM allow multi-access without broadcasting
- Hello packets sent every 30 minutes
**Point-to-point** - 
- Direct connection between two routers
- Physical/ logical applications
- Hello packets sent every 10 minutes
**Point-to-multipoint** - 
- Series of connections made between a single interface on one router and multiple destination routers
- Hello packets sent every 30 minutes
***OSPF operation***
- **Neighbor and adjacency initialization**
- **LSA flooding**
- **SPF tree calculation**
**LSA update multicast addresses
- P-to-P -> 224.0.0.5 (All SPFRouters)
- Broadcast -> 224.0.0.6 (All DRouters)
- P-to-MP -> Adjacent routers unicast IP address
- Recipients must acknowledge updates
**SPF Tree calculation** -
- Each router calculates the best/shortest path to each network in the area
- Based upon the information collected in topology database
**OSPF cost  metric** - 
- 10^8/bandwidth - cost of each interface 

**OSPF RID**
- Always configure loopback interfaces with OSPF to ensure an interface is always active for processes.
- Highest IP address becomes routers RID
- RID used to elect the DR & BDR -> Who create adjacencies with new routers by exchanging LSAs
- **RID hierarchy**
	1. Highest active interface
	2. Highest logical interface
	3. router-id overrides

## Chapter 7 - Layer 2 switching

### Switching services
- Bridges use software to create and manage a content addressable memory (CAM) filter table.
- Switches rely upon application-specific integrated cicuits (asics) ti build & maintain MAC filter tables
- Hardware-based bridging (ASICs)
- Wire speed
- Low latency
- Low cost
Layer 2 switching is faster & less vulnerable to errors than routing while maintaining self contained collision domains

### Functions
**Address learning** - 
- Layer 2 switches remember source MAC address of each frame received
**Forward/ filter decisions** - 
- Switch looks at destination MAC address and chooses the correct exit interface
**Loop avoidance** - 
- Spanning Tree Protocol (STP) is used to prevent network loops

Frame filtering perserves bandwidth by only sending to correct interface based on table. 
	If not in table frame gets flooded out every active interface except for the receiving port

**Loop avoidance**
- Broadcast storms can happen without loop avoidance schemes
- Frame forward failure is called MAC table thrashing

## Chapter 8 - VLANs

**How VLANs simplify network management
- Network adds, moves, & changes are achieved w/ VLAN port config
- Groups can be seperated for increased security
- Logical grouping 
- VLANs greatly enhance network security
- Increase # of broadcast domains and decrease their size
**Broadcast Control**
Occurrence frequency depends on:
1. Protocol type
2. Applications running
3. Service usage
Switch ports (Layer 2)
- Access port -> single VLAN
- Trunk port -> all VLANs
Switches remove any VLAN info from frame before forwarding
	Can't communicate outside VLAN without routing
Each physical port can be either trunk/access/voice access

**Network requirements**
- Small network - up to 200 devices
- Medium network - 200 -> 1,000 devices
- Large network - 1,000+ devices

**Trunk link** -
- 100, 1,000, 10,000,or more Mbps 
- Point-to-point link between
	Two switches, Switch/router, or switch/server
- Carries traffic of up to 4094 VLANs
- Single port -> access to ALL VLANs
- Servers can be accessed from different broadcast domains without needing to use layer 3
- All VLANs send info on truck link until cleared
**Frame Tagging** -
- Uniquely assigns a user-defined VLAN ID to each frame
	Helps frame to destination
- Discarded by switch when destination is met
Trunk links support tagged & untagged traffic w/ 802.1q trunking
Assigns a default port VLAN ID where untagged traffic travels

**VLAN ID methods** -
- Inter-switch Link (ISL) - Tags VLAN info onto ethernet frame
- External encapsulation (Layer 2) adds header and new CRC
**IEEE 802.1q** -
- Inserts data into frame (802.1q tag control fields)
- CRC is encapsulated
- **12-Bit VLAN ID (^ to 4094 VLANs)
	- Designated trunk port
	- Other ports assigned VLAN ID
VLAN 1 is default native VLAN (All traffic untagged)

### Routing between VLANs
***Router-on-a-stick*** - 
- Uses ISL/802.1q trunking to allow all VLANs to communicate on one router interface
- Can also use different interfaces to connect VLANs w/ default gateways
**Inter-VLAN routing (IVR)** - Configured w/ SVI on backplane of layer 3 switch (Virtual router)
## Chapter 9 - Spanning Tree Protocol (STP) -
### Terms
**Root Bridge** - 
- Bridge w/ lowest ID (Best)
- *Root Port* - Port w/ best path
**Non-root bridge** - 
- All bridges that support root bridge
- Exchanges BPDUs w/ other bridges & updates STP topology
**BPDU** -
- Bridge ID is contained within
- Each switch compares sent & received data units
**Bridge ID** - 
- Cisco default (32,168)
- How STP keeps track of switches in the network
**Port cost** - 
- Determined by link bandwidth & used to determine most efficient path to root
**Path cost** - 
- All unique paths are analyzed & a path cost is calculated for each by adding port costs on path to root bridge

***Bridge port roles***

**Root Port** - 
- Link w/ lowest path cost to root bridge
- Higher bandwidth -> lower cost 
- Port connected to lowest port # on upstream switch is used
**Designated port** - 
- Lowest cost to get to on a network segment
- Marked as forwarding port (Only one per net segment)
**Non-designated port** - 
- Higher cost than designated
- Put in blocking/discarding (Not forwarding)
**Forwarding port** - 
- Forwards frames 
	- Root/designated ports

***Root Bridge Selection***

**Key bridge ID** - 
- 8 bytes
- Priority (26 bytes)
- MAC (6 bytes)
Can be set lower manually to ensure proper pathing

***Spanning Tree Protocols***

**802.1d** - Original standard common spanning tree
**PVST+** - 
- Cisco Default
- Provides seperate 802.1d STP instance for each VLAN
	Field inserted into BPDU for per-STP root selection
- Multiple root bridges
**802.1w** - 
- Rapid Spanning Tree protocol (RSTP)
- Higher bridge resource cost than CST but not PVST+
- Only one root bridge
- IEEE standard (nonproprietary)
**802.1s** - 
- MSTP
- Maps multiple VLANs into same STP instance
- Layered STP
**Rapid PVST+**
- Cisco RSTP 
- Uses PVST+ & provides seperate 802.1w (RSTP) for each VLAN
- Fastest convergence
**PVST+ Bridge ID**
- Priority (0-65535) 4 bits
- Sys-id-ext - 12 bits
- MAC - 6 bytes

**802.1d (Common) vs 802.1w (Rapid) States** 

| 802.1d     | 802.1w     |
| ---------- | ---------- |
| Disabled   | Discarding |
| Blocking   | Discarding |
| Listening  | Discarding |
| Learning   | Learning   |
| Forwarding | Forwarding |
1. Find Root Bridge (Bridge ID)
2. Root Ports (Lowest to Root Bridge)
3. Designated ports (Bridge ID)

**Blocked port** - Doesn't forward frames, listens to BPDUs from neighbors (dropping all others) and doesn't transmit frames

**Alternate port** (Only RSTP) - Located on switch connected to two or more switches and other switch holds designated port

**Backup port** (Only RSTP) - 
