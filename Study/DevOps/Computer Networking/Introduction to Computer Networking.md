## What is a Network?

- A collection of interconnected devices that can communicate with each other.
- Devices can be computers, printers, servers, etc.
- Nodes: Individual devices on the network.

![[featured.jpg]]

## Client-Server Architecture (In Short)

When a client pings a specific domain name, it sends a request to a DNS server (Domain Name System server) to translate the domain name into an IP address. The DNS server responds with the corresponding IP address. The client can then use this IP address to send a ping request directly to the target server. If the ping is successful, the target server sends a response message back to the client, indicating that it is reachable.

![[client-server-architecture.png]]

## Data Transmission

- Large messages are broken down into packets for efficient transfer.
- Packets contain data, header information (source & destination addresses), and error checking.

### The OSI Model

- A conceptual framework for network communication.
- Divides communication into 7 layers with specific functions.
    - Physical: Handles physical transmission of data bits (cables, wires).
    - Data Link: Ensures reliable data delivery at the link level (error detection/correction).
    - Network: Routes packets across the network (e.g., IP protocol).
    - Transport: Provides reliable data transfer between applications (e.g., TCP, UDP).
    - Session: Establishes, manages, and terminates sessions between applications.
    - Presentation: Deals with data format presentation and encryption/decryption.
    - Application: Provides network services to applications (e.g., HTTP, FTP). HTTP is used by W3 (World Wide Web).

# Ports

Ports are logical endpoints or communication channels used by network services and applications to communicate over a network. They are numerical identifiers assigned to specific processes running on a host, allowing the operating system to correctly route incoming and outgoing network traffic.

Example:
- HTTP (web browsing) commonly uses port 80.
- HTTPS (secure web browsing) commonly uses port 443.
- FTP (File Transfer Protocol) uses port 21 for control and port 20 for data transfer.
- Email protocols like SMTP (Simple Mail Transfer Protocol) use port 25, and POP3 (Post Office Protocol version 3) uses port 110.

**Guided and Unguided Waves**

- **Guided Waves**: These are transmission media that use physical guides (e.g., cables or wires) to confine and guide the propagation of electromagnetic waves.
  - Examples: Coaxial cables, twisted-pair cables, and optical fiber cables.

- **Unguided Waves**: These are transmission media that do not use physical guides to propagate electromagnetic waves. Instead, they rely on the propagation of waves through free space or the atmosphere.
  - Examples: Radio waves, microwave links, and infrared transmissions.

# Submarine Cables and Optical Fiber Cables

- **Submarine Cables**: These are cables laid on the seabed to transmit data across oceans and seas. They are used for long-distance communication and internet connectivity between continents and countries.

- **Optical Fiber Cables**: Optical fiber cables use thin strands of glass or plastic to transmit data in the form of light pulses. They offer high bandwidth, low signal loss, and immunity to electromagnetic interference, making them ideal for high-speed data transmission over long distances.

### LAN, MAN, and WAN

- **LAN (Local Area Network)**: A network that spans a relatively small geographic area, such as an office, building, or campus. LANs are used to interconnect computers and devices within a limited area.

- **MAN (Metropolitan Area Network)**: A network that spans a larger geographic area, typically a city or metropolitan region. MANs are often used to interconnect multiple LANs within a city or provide internet connectivity to a larger area.

- **WAN (Wide Area Network)**: A network that spans a vast geographic area, such as across countries or continents. WANs are used to interconnect LANs and MANs over long distances, often using leased lines, satellite links, or internet infrastructure.


![[1kny4.jpg]]

# Network Topologies

Network topologies refer to the physical or logical arrangement of devices and connections within a network. Common topologies include:

- **Bus Topology**: Devices are connected to a single cable or backbone, and data is transmitted along the entire length of the cable.

- **Ring Topology**: Devices are connected in a closed loop, and data is transmitted in one direction around the ring.

- **Star Topology**: Devices are connected to a central node or hub, and data is transmitted from the central node to the intended recipients.

- **Mesh Topology**: Devices are interconnected with one another, providing redundant connections and multiple paths for data transmission.

- **Tree Topology**: A hybrid topology that combines characteristics of bus and star topologies, where devices are connected in a hierarchical tree-like structure.

Network topologies influence factors such as cost, performance, scalability, and fault tolerance of a network.



# Modem
**Modem (Modulator-Demodulator)**

A modem (modulator-demodulator) is a device that facilitates communication between digital devices (e.g., computers, routers) and analog telecommunication networks (e.g., telephone lines, cable networks). It acts as an interface between these two different types of systems, converting digital signals into analog signals for transmission and analog signals into digital signals for reception.

Here's how modems work:

1. **Modulation**:
   - The digital data from a computer or digital device is converted into an analog signal suitable for transmission over an analog medium, such as a telephone line or cable network.
   - This process is called modulation, and it involves encoding the digital data onto an analog carrier signal using techniques like amplitude modulation, frequency modulation, or phase modulation.

2. **Transmission**:
   - The modulated analog signal is transmitted over the analog medium (e.g., telephone line, cable network) to the remote location.

3. **Reception**:
   - At the remote location, another modem receives the analog signal from the analog medium.

4. **Demodulation**:
   - The modem demodulates the received analog signal by extracting the original digital data from the modulated carrier signal.
   - This process is called demodulation, and it involves decoding the analog signal back into its original digital form.

5. **Digital Data**:
   - The demodulated digital data is then passed on to the receiving digital device (e.g., a computer or router) for further processing or display.

Modems can be classified into different types based on their technology and capabilities, such as:

- **Dial-up Modems**: Used to establish internet connections over traditional telephone lines. They modulate digital data into audible tones that can be transmitted over the analog telephone network.

- **Broadband Modems**: Used for high-speed internet connections over digital subscriber lines (DSL), cable networks, or fiber-optic networks. These modems operate at higher frequencies and data rates compared to dial-up modems.

- **Wireless Modems**: Allow communication between digital devices and wireless networks, such as cellular networks or Wi-Fi networks.

Modems play a crucial role in enabling communication between digital devices and analog or legacy telecommunication networks, facilitating data exchange and internet connectivity.