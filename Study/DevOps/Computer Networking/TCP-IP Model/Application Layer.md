# Client-server Architecture

Client-server architecture is a fundamental network model that divides tasks and responsibilities between two types of programs: clients and servers. This division of labor streamlines network operations and makes it efficient to manage resources and serve multiple users.

**Key Players:**

- **Clients:** These are software applications that initiate requests for resources or services from a server. They typically run on user devices like personal computers, laptops, or mobile phones. Examples include web browsers, email clients, and online gaming applications.
- **Servers:** Powerful computers that store data and applications. They listen for requests from clients, process them, and send back the requested information or perform the desired action. Servers can host a variety of services, including web servers, file servers, email servers, and database servers.

![[client-server-architecture.png]]

**Communication Cycle:**

The client-server architecture follows a well-defined communication cycle:

1. **Client Request:** The client initiates the interaction by sending a request to the server. This request specifies the service or data needed. The request may include details like the desired web page, a specific file to download, or an email to be sent.
2. **Server Processing:** Upon receiving the request, the server interprets it and locates the requested resource. This might involve accessing a database, retrieving a web page, or performing a specific operation.
3. **Server Response:** Once the server processes the request, it sends a response back to the client. The response could be the requested data (e.g., a web page), a confirmation message (e.g., email sent successfully), or an error message if the request couldn't be fulfilled.
4. **Client Action:** The client receives the server's response and takes appropriate action based on it. This might involve displaying the requested information on the screen, saving a downloaded file, or informing the user of an error.

**Benefits of Client-Server Architecture:**

- **Centralized Management:** Data is stored and managed on a central server, simplifying data backup, security, and access control.
- **Scalability:** Servers can handle multiple client requests simultaneously, making the architecture suitable for large networks with many users.
- **Resource Sharing:** Clients can share resources like printers, databases, and applications hosted on the server, eliminating the need for each device to have its own copy.
- **Improved Performance:** Servers can be more powerful machines than client devices, offloading processing tasks and improving overall network efficiency.
- **Security:** Centralized data storage on the server allows for robust security measures to be implemented, protecting sensitive information.

**Applications of Client-Server Architecture:**

Client-server architecture is widely used in various applications like:

- **World Wide Web:** Web browsers (clients) request web pages from web servers (servers).
- **Email:** Email client software (clients) send and receive emails through email servers (servers).
- **Online Banking:** Banking apps (clients) interact with a bank's server for account access and transactions.
- **Database Management:** Database applications (clients) access and manage data stored on a database server (server).
- **Network File Sharing:** Client devices can access and share files stored on a central file server (server).

**Types of Client-Server Architecture:**

There are various types of client-server architecture, each catering to specific needs:

- **Two-Tier Architecture:** The simplest form with clients directly interacting with a server.
- **Three-Tier Architecture:** Introduces an application server layer between clients and the database server, handling business logic and database access.
- **N-Tier Architecture:** A more complex architecture with multiple layers of servers, each performing specialized tasks.

In conclusion, client-server architecture provides a structured and efficient way to manage resources and deliver services on a network. By dividing tasks between clients and servers, this architecture offers scalability, security, and efficient resource utilization, making it a cornerstone of modern network infrastructure.

# Peer to Peer Architecture (P2P)

Peer-to-peer (P2P) architecture is a decentralized network model where devices, or peers, communicate directly with each other to share resources and services. Unlike the client-server model with dedicated servers, all devices in a P2P network have equal capabilities and responsibilities.

**Conceptual Shift:**

Imagine a network without a central authority, where devices collaborate and share resources directly. This is the essence of P2P architecture. Each device acts as both a client, requesting resources, and a server, providing resources to others.

![[client-server-vs-p2p.png]]

**Benefits of P2P Architecture:**

- **Decentralization:** No single point of failure; the network continues to function even if some peers become unavailable.
- **Scalability:** The network can easily grow by adding more peers without requiring additional central server infrastructure.
- **Efficiency:** Utilizes the combined resources of all peers, potentially reducing reliance on expensive central servers.
- **Direct Communication:** Enables faster data transfer speeds as data travels directly between peers.

**Applications of P2P Architecture:**

- **File Sharing:** Popular for sharing large files like music, movies, and software. Examples include BitTorrent networks.
- **Collaboration:** Used for real-time communication and collaboration tools. Examples include video conferencing and online gaming applications.
- **Blockchain Technology:** The foundation of cryptocurrencies like Bitcoin, where all transactions are verified and recorded on a distributed ledger across all participating nodes.

**Challenges of P2P Architecture:**

- **Security:** Without a central authority, ensuring data security and access control can be more complex.
- **Scalability (Double-Edged Sword):** While the network can grow easily, managing large-scale content discovery and efficient resource allocation can be challenging.
- **Content Legality:** Copyright infringement can be an issue in file-sharing P2P networks.

**Types of P2P Architecture:**

- **Pure P2P:** All peers have equal roles and responsibilities for searching, sharing, and routing data.
- **Centralized P2P:** A central server helps with tasks like indexing content and facilitating peer discovery, but doesn't store the actual data.
- **Hybrid P2P:** Combines elements of both pure P2P and centralized P2P, offering a balance between decentralization and efficiency.

**In Conclusion:**

P2P architecture offers a powerful and flexible way to share resources and build collaborative networks. However, it's important to consider its advantages and disadvantages to determine its suitability for specific applications. As technology evolves, P2P architecture will likely continue to play a significant role in distributed computing and resource sharing.


# Networking Devices

These devices play a vital role in connecting devices and managing data flow on a network. Here's a breakdown of each device and its function:

### Repeaters:

- **Function:** Signal boosters. They amplify weak network signals to extend their reach over longer distances. Often used in coaxial cable networks.
- **Drawbacks:** Can amplify noise along with the signal, potentially degrading signal quality.
- **Use Case:** Extending the range of a network segment where the signal has become weak.

### Hubs (Legacy Devices):

- **Function:** Simple data distribution points. They act as a central connection point for devices on a network, broadcasting any received data to all connected devices.
- **Drawbacks:** Inefficient for larger networks as broadcasts create congestion, especially with heavy traffic.
- **Use Case:** Rarely used in modern networks due to limitations. They might be found in older, very small networks.

### Bridges:

- **Function:** Connect separate network segments that use the same protocol (like Ethernet). They filter and forward data packets based on their MAC address, improving network efficiency compared to hubs.
- **Drawbacks:** Limited functionality compared to switches. They cannot segment networks based on IP addresses (Layer 3) and can create bottlenecks with heavy traffic.
- **Use Case:** Connecting two similar LAN segments that need to be separated but still allow some communication.

### Switches:

- **Function:** Intelligent data forwarding devices. They operate at the data link layer (using MAC addresses) and learn the MAC addresses of devices connected to their ports. When a device sends data, the switch forwards it only to the specific port of the intended recipient, reducing congestion and improving network performance.
- **Benefits:** More efficient than hubs and bridges, offering better performance and reduced network congestion.
- **Use Case:** Found in most modern networks to connect devices within a network segment and forward data efficiently.

### Routers:

- **Function:** The traffic directors of your network. Routers connect different networks (like your home network to the internet) and forward packets based on their destination IP addresses. They maintain routing tables that map IP addresses to network paths, ensuring data reaches its intended destination across different networks.
- **Benefits:** Essential for connecting networks and enabling communication between devices on different networks (e.g., your home network and the internet).
- **Use Case:** A core component for connecting networks and enabling internet access.

### Gateways:

- **Function:** Act as a general term for devices that provide access to another network. Routers can be considered a type of gateway, but gateways can have a broader meaning. For example, an email gateway might translate emails between different email systems.
- **Benefits:** Provide a connection point or protocol conversion between different networks.
- **Use Case:** Routers are a common example, but gateways can encompass various devices that enable communication between dissimilar networks.

### Brouters (Rare):

- **Function:** A combination of a bridge and a router. They can operate at the data link layer (like a bridge) and the network layer (like a router). This allows them to connect networks using different protocols and forward data packets based on MAC addresses or IP addresses.
- **Drawbacks:** Rarely used in modern networks as router functionality is often sufficient.
- **Use Case:** In specific scenarios where connecting networks with different protocols and needing both bridge and router functionalities.

# Protocols

### TCP/IP:
- [[HTTP-HTTPS]]
- [[DHCP]]
- [[FTP]]
- [[SMTP]]
- [[POP-IMAP]]
- [[SSH]]
- [[VNC]]

[[TELNET]] (Outside of TCP/IP)

[[TCP]] and [[UDP]] are Transport Layer protocols.
# How email works?

### How Email Works (From a Computer Networking Perspective)

#### Overview

Email communication involves sending and receiving electronic messages across the Internet. This process uses specific protocols to ensure that emails are transmitted, stored, and retrieved correctly.

#### Step-by-Step Workflow

1. **Email Composition and Sending (Client-Side)**
2. **Email Transfer (SMTP)**
3. **Email Storage and Retrieval (POP/IMAP)**

#### Step-by-Step Explanation

1. **Email Composition and Sending (Client-Side)**:
   - The user composes an email using an email client (e.g., Outlook, Gmail, Thunderbird).
   - Once the email is ready, the user hits "Send." The email client connects to the outgoing mail server using the SMTP protocol.

![[1_9ZW46uHlvlyvJb5moQs9aQ.jpg]]

2. **Email Transfer (SMTP)**:
   - **Client to ISP Mail Server**:
     - The email client sends the email to the SMTP server of the user's Internet Service Provider (ISP).
     - The SMTP server authenticates the sender and processes the email for delivery.
   - **ISP Mail Server to Recipient's ISP Mail Server**:
     - The SMTP server of the sender's ISP looks up the recipient's domain (e.g., recipient@example.com) using the Domain Name System (DNS).
     - The DNS provides the IP address of the recipient's mail server.
     - The sender's SMTP server establishes a connection with the recipient's ISP mail server and transfers the email.
   - **Intermediate Transfers**:
     - Sometimes, the email may pass through multiple SMTP servers before reaching the recipient's server, especially if there are intermediary relays.

3. **Email Storage and Retrieval (POP/IMAP)**:
   - **Recipient's ISP Mail Server**:
     - The recipient's mail server receives the email and stores it in the recipient's mailbox.
   - **Retrieving the Email (POP/IMAP)**:
     - The recipient uses an email client to check for new emails.
     - The email client connects to the recipient's mail server using either POP or IMAP:
       - **POP (Post Office Protocol)**:
         - The client connects to the mail server using POP.
         - Emails are downloaded to the recipient's device.
         - The server may delete the emails after download (depending on client settings).
       - **IMAP (Internet Message Access Protocol)**:
         - The client connects to the mail server using IMAP.
         - Emails remain on the server, and the client synchronizes with the server.
         - Allows the recipient to manage emails directly on the server, accessible from multiple devices.

This was a brief information, You can refer to [[Email working]] for more details.

Got it, here are the notes based on the list you provided:

# DNS (Domain Name System)

## Domain Names and IP Mapping
- Domain names are human-readable names that are mapped to numerical IP addresses.
- DNS is responsible for translating domain names into their corresponding IP addresses, allowing users to access websites and online services.

## DNS Structure
- DNS has a hierarchical structure that helps to quickly find IP addresses associated with domain names.
- It consists of subdomains, domains, and top-level domains (TLDs).
- Subdomains are parts of the main domain (e.g., `www`, `mail`, `blog`).
- Domains are the main part of the domain name always known as second level domain (e.g., `example.com`).
- Top-level domains are at the highest level (e.g., `.com`, `.org`, `.net`).

## Root DNS Servers
- Root DNS servers are at the top of the DNS hierarchy.
- They store information about the IP addresses of TLD (Top-Level Domain) servers.
- There are 13 root servers globally, managed by different organizations.
- This thing makes tree-like structure.
## DNS Process

1. **User Layer**
   - When a user tries to access a domain (e.g., `example.com`) in a web browser or an application, the client (the user's device) first checks its local DNS cache for the IP address associated with the domain name.
   - If the IP address is not found in the local cache, the client sends a DNS query to the recursive DNS server configured on the client's system (typically provided by the user's Internet Service Provider (ISP)).

2. **ISP Layer**
   - The recursive DNS server at the ISP level is responsible for handling client requests and resolving domain names on their behalf.
   - The recursive DNS server first checks its own cache for the requested domain name. If the IP address is found, it returns the cached response to the client.
   - If the IP address is not in the cache, the recursive DNS server initiates the process of querying other DNS servers to find the IP address.
   - Your all domain data is stored by ISP, and that's why they can track you using your IP address.

3. **Root Server Layer**
   - If the IP address is not in the recursive DNS server's cache, it starts by querying one of the root DNS servers to obtain the IP addresses of the Top-Level Domain (TLD) name servers responsible for the requested domain (e.g., `.com`).
   - The root servers are at the top of the DNS hierarchy and store information about the IP addresses of TLD servers.

4. **Top-Level Domain (TLD) Layer**
   - After obtaining the IP addresses of the TLD name servers from the root server, the recursive DNS server queries these TLD name servers.
   - The TLD name servers respond with the IP addresses of the authoritative name servers responsible for the specific domain (e.g., `example.com`).

5. **Authoritative Name Server Layer**
   - The recursive DNS server then queries the authoritative name servers for the IP address associated with the requested domain name.
   - The authoritative name servers store the actual IP address mappings for the domains they are responsible for.
   - These servers respond to the recursive DNS server with the IP address associated with the requested domain name.

6. **Response Caching and Client Connection**
   - The recursive DNS server caches the IP address response received from the authoritative name servers.
   - The cached entry includes the IP address and a Time-to-Live (TTL) value, which specifies how long the entry can be cached before it needs to be refreshed.
   - The recursive DNS server returns the IP address to the client.
   - The client receives the IP address from the recursive DNS server and can now establish a connection with the requested domain using the obtained IP address.

References:
- Visit [Cloudeflare](https://www.cloudflare.com/learning/dns/what-is-dns/) or [GeeksForGeeks](https://www.geeksforgeeks.org/domain-name-system-dns-in-application-layer/) for more details about DNS.
- Visit [Cloudeflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/)



