### Remember that
| Layer     | Data format                | Protocol                          |
| --------- | -------------------------- | --------------------------------- |
| Transport | Data transfers in Segments | HTTP, DHCP, POP etc.              |
| Network   | Data transfers in Packets  | TCP/UDP                           |
| Data Link | Data transfers in Frames   | IP which contains Network address |

# Routing


![[unicast_routing.jpg]]

So many routes are connected in between is called network. Every route has its own network address, which allows them to send data packets. This works like path finding algorithm.

When you send a packet to the receiver router will  check it with the destination address through forwarding table ([DNS forwarding table is like data structure](https://www.geeksforgeeks.org/routing-tables-in-computer-network/)), If it isn't found same then forward it to next router, This is called[ Hop-by-Hop routing](https://www.researchgate.net/figure/Source-Routing-vs-Hop-by-Hop-routing-In-source-routing-shown-left-source-node-u-on_fig1_325638695#:~:text=In%20hop%2Dby%2Dhop%20routing,sinks%20are%20the%20designated%20servers.&text=We%20study%20a%20problem%20of,over%20an%20arbitrary%20network%20topology.).

Every device has its own MAC address.

![[cn_purple_fig4.jpg]]

Network address lives in IP address. Refer to [GeeksForGeeks](https://www.geeksforgeeks.org/what-is-a-network-address/), [Tutorial Point](https://www.tutorialspoint.com/structure-and-types-of-ip-address) or [MS docs](https://learn.microsoft.com/en-us/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)

**Note:** Network address and subnet mask (Subnet ID) are same.

Control plane creates this routing tables which is superset of forwarding tables.

### Types of Routing

- **Static routing:** This is done by adding address manually which is time consuming.
- **Dynamic routing:** This is path finding algorithm.

Visit [Tutorial point](https://www.tutorialspoint.com/data_communication_computer_network/network_layer_routing.htm) for more information.

# IP (Internet Protocol)

It lies in network layer, Router works on [subnet mask](https://www.geeksforgeeks.org/role-of-subnet-mask/), There were group of IPs which is routing from Hop-to-Hop (Like a path finding algorithm), Not individual router does it. This routes are IPs called subnet.

![[internet-architecture.svg]]

### Classes of IP address

| Class | Range                       |
| ----- | --------------------------- |
| A     | 0.0.0.0 - 127.255.255.255   |
| B     | 128.0.0.0 - 191.255.255.255 |
| C     | 192.0.0.0 - 223.255.255.255 |
| D     | 224.0.0.0 - 239.255.255.255 |
| E     | 240.0.0.0 - 255.255.255.255 |

### IPv4

IPv4: 36 bit architecture, 4 words

![[0_o26gkcQ5xnr4gI0L.png]]

- 1 byte == 8 bits
- It includes IP version, Identification, Flags, Protocols, Checksums, Address, TTL etc.
- Size: 2^23  == 4294967296

### IPv6

IPv6: 128 bit architecture

![[it04-01-ipv-6-structure-and-format.PNG]]



Refer [Ms Docs](https://learn.microsoft.com/en-us/azure/architecture/networking/guide/ipv6-architecture) for more information.


### Why the world does not shift for IPv6 yet?

- It isn't backward compatible.
- Some devices which are configured with IPv4 cannot access to the IPv6 websites.
- ISP would have to shift their hardware for IPv6 which is lot of hardware work.

# Subnet Masking

## Introduction
- Subnet masking is a technique used in networking to divide a larger network into smaller subnetworks, or subnets.
- It allows for efficient use of available IP addresses and improved network organization and management.
- Subnet masks are 32-bit numbers used to differentiate the network portion and host portion of an IP address.

## Purpose of Subnet Masking
- Enables division of a single network into multiple smaller subnetworks.
- Allows for better utilization of available IP addresses within a network.
- Improves network security by separating different subnets and controlling traffic between them.
- Facilitates network organization and management by logically grouping devices or departments.

## Subnet Mask Structure
- A subnet mask is a 32-bit number represented in dotted-decimal notation (e.g., 255.255.255.0).
- The bits set to 1 in the subnet mask represent the network portion of the IP address.
- The bits set to 0 in the subnet mask represent the host portion of the IP address.

## Subnet Mask Examples
- **255.0.0.0**: Classful subnet mask for Class A networks.
- **255.255.0.0**: Classful subnet mask for Class B networks.
- **255.255.255.0**: Classful subnet mask for Class C networks.
- **255.255.255.192**: Subnet mask that divides a Class C network into 4 subnets.
- **255.255.255.240**: Subnet mask that divides a Class C network into 16 subnets.

## Calculating Subnets and Host Addresses
- The number of available subnets and hosts per subnet can be calculated based on the subnet mask.
- The number of available subnets is determined by the number of bits set to 1 in the host portion of the subnet mask.
- The number of available hosts per subnet is determined by the number of bits set to 0 in the host portion of the subnet mask.

## Subnet Mask and CIDR Notation
- CIDR (Classless Inter-Domain Routing) notation is an alternative way to represent subnet masks.
- It consists of an IP address followed by a forward slash (/) and the prefix length (number of bits in the subnet mask).
- Example: 192.168.1.0/24 represents the IP address 192.168.1.0 with a subnet mask of 255.255.255.0.

Subnet masking is a crucial concept in IP networking, allowing for efficient use of IP addresses, network organization, and improved security through the division of larger networks into smaller subnetworks.


# Middle-boxes

**Middleboxes: Firewalls and NAT**

Middleboxes are network devices or software components that sit between the end hosts (clients and servers) and perform various functions, such as security, optimization, or address translation. Here are some notes on two common types of middleboxes: firewalls and Network Address Translation (NAT).

**Firewalls**

1. **Definition**: A firewall is a network security device or software that monitors and filters incoming and outgoing network traffic based on predefined security rules.

2. **Purpose**: Firewalls are designed to protect internal networks from unauthorized access, prevent malicious traffic, and enforce security policies.

3. **Types**:
   - **Packet-filtering firewalls**: Inspect packets based on their source, destination, protocol, and port numbers.
   - **Stateful firewalls**: Keep track of active connections and their states, allowing or blocking traffic based on the connection state.
   - **Application-level gateways (ALGs)**: Inspect and filter traffic at the application layer, understanding application protocols.
   - **Next-generation firewalls (NGFWs)**: Combine traditional firewall capabilities with advanced features like application control, intrusion prevention, and deep packet inspection.

4. **Firewall Rules**: Firewalls operate based on a set of rules that define which traffic to allow or block. These rules can be based on various criteria, such as IP addresses, ports, protocols, and applications.

5. **Deployment**: Firewalls can be deployed at different locations, such as network boundaries (perimeter firewalls), between internal network segments (internal firewalls), or on individual hosts (host-based firewalls).

**Network Address Translation (NAT)**

1. **Definition**: NAT is a technique that maps one or more IP addresses to another IP address or set of IP addresses. It allows multiple devices to share a single public IP address for internet access.

2. **Purpose**: NAT serves two primary purposes:
   - **IP address conservation**: It helps conserve the limited pool of public IPv4 addresses by allowing multiple devices to share a single public IP address.
   - **Network security**: By hiding internal IP addresses behind a single public IP address, NAT provides an additional layer of security by making it harder for external hosts to directly access devices on the internal network.

3. **Types**:
   - **Static NAT**: A one-to-one mapping between a public IP address and a private IP address.
   - **Dynamic NAT**: A pool of public IP addresses is dynamically assigned to private IP addresses as needed.
   - **Port Address Translation (PAT) or Network Address Port Translation (NAPT)**: A single public IP address is shared among multiple private IP addresses by using different port numbers.

4. **NAT Operation**:
   - When an internal host sends a packet to the internet, the NAT device replaces the source IP address with its public IP address and updates the source port number.
   - When a response packet arrives from the internet, the NAT device checks its translation table, replaces the destination IP address and port with the internal host's IP address and port, and forwards the packet to the internal host.

5. **Limitations and Considerations**:
   - NAT breaks the end-to-end connectivity model of the internet, as internal hosts are not directly addressable from the internet.
   - NAT can cause problems for certain applications that embed IP addresses in the data stream or require end-to-end connectivity.
   - NAT traversal techniques, such as STUN (Session Traversal Utilities for NAT), are used to overcome NAT limitations for applications like VoIP and peer-to-peer applications.

Firewalls and NAT are essential middleboxes that provide security, address translation, and traffic control functionalities in modern networks, enabling secure and efficient communication between internal and external networks.