Here are detailed notes on the OSI (Open Systems Interconnection) model:

# OSI Model

The OSI model is a conceptual framework used to describe the functions of a networking system. It consists of seven layers, each with specific responsibilities for facilitating communication between devices on a network.


![[Communication-between-the-layers-in-OSI-model.jpg]]

## 1. Physical Layer

- Responsible for the physical connection and transmission of raw data bits over the communication medium.
- Defines specifications for cables, connectors, signal levels, and timing.
- Examples: Ethernet cable, fiber optic cable, wireless radio frequencies.

## 2. Data Link Layer

- Handles reliable data transfer between adjacent nodes (devices) on the same network.
- Divides data into frames, adds physical addresses (MAC addresses), and performs error detection and correction.
- Includes sublayers: Logical Link Control (LLC) and Media Access Control (MAC).
- Examples: Ethernet, Wi-Fi, Point-to-Point Protocol (PPP).

## 3. Network Layer

- Responsible for logical addressing, routing, and forwarding data between different networks.
- Determines the best path for data to travel through the interconnected networks.
- Handles logical addressing (IP addresses), packet fragmentation, and reassembly.
- Examples: Internet Protocol (IP), Internet Control Message Protocol (ICMP).

## 4. Transport Layer

- Ensures end-to-end reliable data transfer between applications running on different hosts.
- Handles segmentation, flow control, error correction, and connection establishment/termination.
- Provides services such as multiplexing, virtual circuits, and quality of service (QoS).
- Examples: Transmission Control Protocol (TCP), User Datagram Protocol (UDP).

## 5. Session Layer

- Manages and coordinates communication sessions between applications.
- Establishes, maintains, and synchronizes sessions, including checkpointing, recovery, and restart capabilities.
- Provides mechanisms for data exchange and dialog control.
- Examples: Remote Procedure Call (RPC), Network File System (NFS).

## 6. Presentation Layer

- Ensures data is represented in a format that can be understood by both communicating devices.
- Handles data translation, compression, encryption, and character code conversions.
- Provides services like data compression, encryption/decryption, and multimedia formatting.
- Examples: JPEG, GIF, ASCII, EBCDIC.

## 7. Application Layer

- Provides services and interfaces for end-user applications to access network services.
- Handles application-specific protocols and data formats.
- Examples: HTTP (web browsing), SMTP (email), FTP (file transfer), DNS (domain name resolution).

The OSI model is a conceptual framework that helps standardize and modularize network communication functions. Each layer communicates with the layer above and below it, providing services to the upper layers while receiving services from the lower layers. This layered approach simplifies network design, development, and troubleshooting.

It's important to note that while the OSI model is widely used as a reference, not all networking protocols strictly follow its layer structure. Some protocols, like TCP/IP, combine or omit certain layers for efficiency or practical implementation reasons.