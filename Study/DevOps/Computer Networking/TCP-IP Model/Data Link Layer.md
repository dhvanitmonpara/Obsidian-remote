**Data Link Layer**

The data link layer is the second layer of the OSI (Open Systems Interconnection) model, sitting between the physical layer and the network layer. where data passes in form of packets. It plays a crucial role in ensuring reliable data transfer between directly connected devices on a local area network (LAN). Here are the key points about the data link layer:

![[diagram-export-10-6-2024-11_29_02-am.png]]

- Your new devices will be connected to DHCP server.
- Data Link layer works with MAC address (DLLA: Data Link Layer Address) at the router level (LAN).
- MAC address is not device's, It is your components let's say your wifi has its own MAC address. Your blue-tooth has its own etc.
- MAC address is assigned to devices corresponding to private IPs.

1. **Framing**:
   - The data link layer takes the raw data from the network layer and divides it into smaller units called frames.
   - It adds a header and a trailer to the data, creating a structured frame.
   - The header and trailer contain control information, such as source and destination addresses, error checking codes, and frame synchronization patterns.

2. **Addressing**:
   - The data link layer uses physical addresses (MAC addresses) to identify the source and destination devices on the local network.
   - MAC addresses are unique identifiers assigned to network interfaces by the manufacturer.
   - The data link layer ensures that frames are delivered to the correct destination device on the local network.

3. **Error Detection and Handling**:
   - The data link layer implements error detection mechanisms, such as checksums or cyclic redundancy checks (CRCs), to detect corrupted or damaged frames.
   - If errors are detected, the data link layer can request retransmission of the damaged frames to ensure data integrity.

4. **Access Control**:
   - In shared media environments (e.g., Ethernet), the data link layer coordinates access to the physical medium to prevent collisions and manage data transmission.
   - Access control methods like CSMA/CD (Carrier Sense Multiple Access with Collision Detection) are used to determine when devices can transmit data.

5. **Data Link Layer Protocols**:
   - Different data link layer protocols are used for different types of networks and media.
   - Examples include Ethernet (for wired LANs), Wi-Fi (for wireless LANs), Point-to-Point Protocol (PPP) for point-to-point links, and others.

6. **Services Provided to the Network Layer**:
   - The data link layer provides services to the network layer, such as framing, addressing, error detection and recovery, and access control.
   - It ensures reliable data transfer between directly connected devices on the local network.

7. **Sublayers**:
   - The data link layer is often divided into two sublayers:
     - **Logical Link Control (LLC)**: Responsible for framing, addressing, and error checking.
     - **Media Access Control (MAC)**: Responsible for media access control and physical addressing.

The data link layer plays a critical role in enabling reliable and efficient data transfer on local area networks by framing data, addressing devices, detecting and handling errors, and controlling access to the shared physical medium. It ensures that data is delivered correctly between directly connected devices before being passed to higher layers for further processing or routing.

Refer to [Tutotial point](https://www.tutorialspoint.com/dynamic-host-configuration-protocol-dhcp) or [GeeksForGeeks](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) for detailed information.