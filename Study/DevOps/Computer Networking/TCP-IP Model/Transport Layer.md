Transport Layer lies on Devices. It is a crucial part of the TCP/IP protocol suite, responsible for ensuring reliable and efficient data transfer between applications running on different hosts. Here are the key points about the transport layer:

## Roles and Responsibilities

![[diagram-export-7-6-2024-2_05_54-pm.png]]

- **End-to-End Communication**: The transport layer establishes logical communication channels between applications on different hosts, enabling end-to-end data transfer.
- **Segmentation and Reassembly**: It divides the data from the application layer into smaller units called segments (TCP) or datagrams (UDP) for transmission, and reassembles the segments/datagrams at the receiving end.
- **Multiplexing and Demultiplexing**: It multiplexes data from multiple applications onto a single physical connection and demultiplexes the incoming data to the appropriate applications.
- **Error Control and Flow Control**: The transport layer ensures reliable data transfer by implementing error control mechanisms (e.g., retransmissions, checksums) and flow control mechanisms to prevent overwhelming the receiver.
# Transport Layer Protocols

## TCP (Transmission Control Protocol)

- **Connection-oriented**: Establishes a reliable end-to-end connection before data transfer.
- **Reliable Data Transfer**: Ensures data integrity through error detection, retransmissions, and sequence numbering.
- **Flow Control**: Regulates the rate of data transmission to prevent overwhelming the receiver.
- **Congestion Control**: Adjusts the sending rate to avoid network congestion.
- **Examples**: Web browsing, file transfers, email, and other applications that require reliable data delivery.


### Features
- It takes care of data should be sent successfully and order should be maintained.
- It divides data into chunks, add header with checksums and send to next layer.
- It is connection oriented. And also does congestion control and error control.
- Functionality of [Flag](https://www.techopedia.com/definition/3796/flag) also.

### 3 way handshade
Here's a short introduction to the three-way handshake in TCP:

The three-way handshake is the process used in the Transmission Control Protocol (TCP) to establish a reliable connection between two hosts before data transmission can begin. It involves the exchange of three separate segments between the client (the host that initiates the connection) and the server (the host that listens for incoming connections).

In the first step, the client sends a SYN (Synchronize) segment to the server, indicating its intention to establish a connection. The server responds with a SYN-ACK (Synchronize-Acknowledge) segment, acknowledging the client's request and providing its own initial sequence number. Finally, the client sends an ACK (Acknowledge) segment to the server, acknowledging the server's response.

After this three-way exchange of segments, the TCP connection is established, and data transfer can commence between the client and server. The three-way handshake ensures synchronization of sequence numbers, establishes a bidirectional connection, prevents stale connections, and provides security against certain types of attacks.

Refer to [Tutorial point](https://www.tutorialspoint.com/tcp-3-way-handshake-process) and [Scaler-topics](https://www.scaler.com/topics/computer-network/tcp-3-way-handshake/) for more information.

### Data travels in packets
Transport layer attaches [socket](https://www.geeksforgeeks.org/socket-in-computer-network/) port number. And transport layer also takes care of [Congestion control](https://www.scaler.com/topics/computer-network/tcp-congestion-control/) Its like traffic control.

![[diagram-export-7-6-2024-2_14_47-pm.png]]

### Checksums

**Checksum Process in Transport Protocols**

The checksum is a mechanism used in transport protocols like TCP and UDP to detect errors in the transmitted data. It involves calculating a numerical value based on the data being transmitted and including this value in the protocol header. The receiving end recalculates the checksum and compares it with the received value to verify data integrity.

**TCP Checksum Process**

1. **Sender Side**:
   - The TCP sender calculates a 16-bit one's complement checksum over the following fields:
     - TCP header
     - TCP data (if present)
     - A pseudo-header (containing source and destination IP addresses, protocol number, and TCP segment length)
   - The calculated checksum value is placed in the checksum field of the TCP header.

2. **Receiver Side**:
   - The TCP receiver performs the same checksum calculation over the received TCP segment, including the TCP header, data, and pseudo-header.
   - The receiver compares the calculated checksum with the checksum value in the received TCP header.
   - If the checksums match, the data is considered to be received correctly.
   - If the checksums do not match, the TCP segment is discarded, and the receiver may request retransmission of the data.

**UDP Checksum Process**

1. **Sender Side**:
   - The UDP sender calculates a 16-bit one's complement checksum over the following fields:
     - UDP header
     - UDP data
     - A pseudo-header (containing source and destination IP addresses, protocol number, and UDP datagram length)
   - The calculated checksum value is placed in the checksum field of the UDP header.

2. **Receiver Side**:
   - The UDP receiver performs the same checksum calculation over the received UDP datagram, including the UDP header, data, and pseudo-header.
   - The receiver compares the calculated checksum with the checksum value in the received UDP header.
   - If the checksums match, the data is considered to be received correctly.
   - If the checksums do not match, the UDP datagram is typically discarded, as UDP does not have a built-in retransmission mechanism.

References:
- [Tutorial point](https://www.tutorialspoint.com/calculation-of-tcp-checksum)
- [GeeksForGeeks](https://www.geeksforgeeks.org/calculation-of-tcp-checksum/)

### Timers
![[tcp_half_closed_timers.png]]

Suppose you want to send a file to your friend over the internet. When you initiate the file transfer, your computer sets a timer for each packet of data it sends. The timer is an estimate of how long it should take for the packet to reach your friend's computer and for your computer to receive an acknowledgment.

If your computer receives the acknowledgment before the timer expires, it means the packet was delivered successfully, and your computer can send the next packet. The timer is then reset or stopped.

However, if the timer expires before receiving the acknowledgment, your computer assumes the packet was lost and retransmits it. It also restarts the timer with a slightly longer duration.

If the retransmitted packet is successful, your computer receives the acknowledgment and can continue sending the next packet. If not, the process repeats with an even longer timer duration.

If your computer reaches a certain threshold of unsuccessful retransmissions, it will assume the connection with your friend's computer has been lost and terminate the file transfer.

The timer concept helps manage reliable data transfer by detecting packet losses, ensuring correct delivery, and maintaining the integrity of the connection between the communicating devices.

Refer to [Scaler-topics](https://www.scaler.com/topics/tcp-timers/) or [Tutorial point](https://www.tutorialspoint.com/tcp-timers) for more details.

## UDP (User Datagram Protocol)

- **Connectionless**: No prior connection establishment is required so Data may or may not be delivered.
- **Unreliable Data Transfer**: Does not guarantee delivery or sequence preservation.
- **Best-Effort Delivery**: Data may be lost, duplicated, or delivered out of order.
- **Low Overhead**: Faster than TCP due to minimal processing and no reliability mechanisms.
- **Examples**: DNS, streaming media, online games, and applications that prioritize speed over reliability.
- **Connectionless:** UDP is connectionless protocol.

![[UDP-header.jpg]]

Header is a connected information with the actual data.
Total size of the protocol is 2^16 = 65536 bits.

**Use cases:**
- Video conference
- DNS servers
- Gaming

# Port Numbers

- Port numbers are used to identify specific applications or services on a host.
- Well-known port numbers (0-1023) are reserved for commonly used services (e.g., HTTP - 80, FTP - 21, SMTP - 25).
- Registered port numbers (1024-49151) are assigned to specific applications or services.
- Ephemeral port numbers (49152-65535) are used for temporary connections initiated by clients.

# TCP/UDP Header

- The TCP and UDP headers contain essential information for data transfer, including source and destination port numbers, sequence numbers (TCP), checksum, and other control fields.

The transport layer plays a crucial role in enabling reliable and efficient communication between applications running on different hosts, ensuring that data is transferred correctly and in a controlled manner.

References for Transport layer:
- [Scaler-topics](https://www.scaler.com/topics/computer-network/transport-layer-protocols/)