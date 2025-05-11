# Chapter 2 -The Open Systems
Interconnection
Specifications(OSI)

{x} = uses x

[x] = is included in x

## ***physical& [layer 1]***

transmission medium& —————

refers to the physical path through which data is transmitted between devices in a network. It can be wired or wireless, and it plays a crucial role in determining the speed, quality, and reliability of communication.

**signal encoding&** - is the method of converting data into signals (electrical, optical, or radio waves) that can be transmitted over a physical medium in a network. It defines how the data is represented for transmission.

**modulation& -**  is the process of varying a carrier signal's properties (such as amplitude, frequency, or phase) to encode data for transmission over a communication channel.

**transmission mode&** -  refers to the method of data transmission between devices in a network, which can be classified into three types:

1. **Simplex**: Data flows in one direction only (e.g., keyboard to computer).
2. **Half-Duplex**: Data can flow in both directions, but not simultaneously (e.g., walkie-talkies).
3. **Full-Duplex**: Data can flow in both directions simultaneously (e.g., telephone calls).

**bandwidth& -**  refers to the maximum rate at which data can be transmitted over a network connection or communication channel in a given amount of time. It is typically measured in bits per second (bps), such as **megabits per second (Mbps)** or **gigabits per second (Gbps)**.

**Hardware**:

- hubs&
- network interface cards (NICs)&
- repeaters&

**Physical Layer Standards**:

- IEEE 802.3 (Ethernet)
- IEEE 802.11 (Wi-Fi)

Devices

- **Repeaters**
- **Hubs**
- **Network Cables (Ethernet, Fiber Optic)**
- **Modems**
- **Transceivers**
- **Wireless Access Points**

## data link& [layer 2]

- Framing: How data is packaged into frames for transmission
- Physical Addressing: MAC addresses and their role in identifying devices on the same local network
- Error Detection and Correction: Techniques like checksums, CRC (Cyclic Redundancy Check), and retransmission strategies

**node to node& data transfer**

**Node-to-Node Transfer** refers to the direct transmission of data between two network devices (nodes) without intermediate storage..

**media access control& (mac&)**

refers to a unique identifier assigned to a network interface card (NIC) for communication on a physical network segment. It operates at the Data Link Layer and helps in managing access to the network medium.

**frame creation and handling   {mac}**

- **Frame Creation**: Data packets are wrapped in frames that include a header (with source and destination MAC addresses, type, and error-checking information) and a trailer. This prepares the data for transmission on the Data Link Layer.
- **Frame Handling**: This refers to how frames are processed by network devices (like switches and routers). It includes receiving frames, checking for errors, removing the header and trailer, and then forwarding the data to the appropriate destination based on the MAC address.

flow control layer 2&

DEVICES

- **Bridges**
- **Network Interface Cards (NICs)**
- **Access Points (APs)**
- **Repeaters**
- **Load Balancers**
- **Wireless LAN Controllers**

network& [layer 3]      Responsibilities (packet forwarding, routing, logical addressing)

## n

**logical addressing&** - is the process of assigning unique identifiers (such as IP addresses) to devices on a network to enable routing and communication across different networks. Unlike physical addresses (MAC addresses), which are fixed and hardware-specific, logical addresses can change and are used to identify devices at the Network Layer (Layer 3) of the OSI model. This allows data to be routed correctly from the source to the destination across interconnected networks.

routing protocols& - standardized methods used by routers to determine the best paths for data packets to travel across networks. They enable routers to communicate with each other, share information about network topology, and make routing decisions.

***packet& [TCP]*** 

A packet is a unit of data sent over a network, consisting of a header and the actual data.

fragmentation& {MTU}

Fragments are smaller pieces of a packet created when the packet is too large to send over a network. They are sent separately and reassembled at the destination.

**Network Layer Devices**:

- Routers
- Layer 3 switches

**Network Layer Standards**:

- Internet Protocol Suite (TCP/IP)
- ISO/OSI Model (Layer 3)

**Internet Protocol (IP) -** is a set of rules governing the format of data sent over the internet or local network. It assigns unique addresses (IP addresses) to devices, enabling them to send and receive data packets. IP operates at the Network Layer (Layer 3) of the OSI model and ensures data is routed correctly between devices.

**inter-networking& -** is the process of connecting multiple networks to enable communication and data exchange between them.

Devices

- **Routers**
- **Layer 3 Switches**
- **Gateways**
- **Firewalls** (with routing capabilities)
- **IPsec Devices**
- **Multicast Routers**

## ***transport& [layer 4]***

- Ensures reliable data transfer between hosts
- Provides error detection and recovery
- Flow control and congestion control

**window**

Window refers to the amount of data that can be sent before receiving an acknowledgment in TCP. It helps manage the flow of data and control congestion in the network. The quantity of data segments (measured in bytes) that the transmitting machine is allowed to send without receiving an acknowledgment for 

segmentation

Segmentation is the process of dividing a large message into smaller, manageable pieces called segments for easier transmission over a network.

***tcp& (transmission control protocol&)  {flow control}***

TCP (Transmission Control Protocol) is a communication protocol that ensures reliable, ordered, and error-checked delivery of data packets between applications over a network.

***sequencing&*** 

Sequencing is the process of arranging packets in the correct order for reassembly at the destination, ensuring that data is received in the same order it was sent.

***congestion control&***

**flow control& [tcp]** 
Flow control is a technique used in networking to manage the rate of data transmission between sender and receiver, preventing the sender from overwhelming the receiver with too much data at once.

***buffer& ~~~~*-** refers to a temporary storage area used to hold data while it's being transferred from one place to another. Buffers are essential to handle differences in speed between sending and receiving devices.

Devices

- **Gateways** (for Transport Layer functions)
- **Load Balancers** (operating at the Transport Layer)
- **Firewalls** (with Transport Layer capabilities)

## **session layer& *[layer 5]***

session establishment (everything) -  is the process of initiating and setting up a connection between two devices or applications for communication.

**Session Layer Protocols**:

- PPTP (Point-to-Point Tunneling Protocol)
- RPC (Remote Procedure Call)
- NetBIOS (Network Basic Input/Output System)
- SOCKS (Socket Secure

Devices

- **Session Border Controllers (SBCs)**
- **Gateways** (for session management)
- **Application Layer Gateways**

## presentation layer& [layer 6]

**data translation**:

- Converting data between application formats and network formats (e.g., from a file format like .jpeg to a format suitable for transmission).

data encryption& /Decryption - **Data Encryption** is the process of converting plain text into unreadable code (ciphertext) to protect data from unauthorized access.

**Data Decryption** is the reverse process, converting the encrypted data back into its original readable form. These processes ensure secure communication and data protection.

**data compression& -** is the process of reducing the size of data to save storage space or speed up transmission over a network. It makes data more efficient to store and transfer.

**character encoding&** - is the process of converting characters (letters, numbers, symbols) into a format (usually binary) that computers can understand and process, such as ASCII or UTF-8.

**data serialization& -** is the process of converting structured data into a format (such as JSON, XML, or binary) that can be easily stored or transmitted and later reconstructed.

s**yntax negotiation& -** is the process by which two devices or applications agree on a common format or syntax for data exchange during communication. This ensures that both parties can correctly interpret the data being transmitted

d**ata formatting** - is the process of organizing and structuring data in a specific way to ensure it is easily readable and usable by software applications or users. This can include defining data types, layouts, and encoding standards.

- **Protocol Converters**
- **Encryption Devices**
- **Data Compression Devices**

## ***application layer  [layer 7]***

- **Definition of the Application Layer**:
    - The topmost layer in the OSI model, providing network services directly to end-user applications.
- **Functions of the Application Layer**:
    - Facilitates user interface
    - Supports application services
    - Enables communication between software applications
- **Common Application Layer Protocols**:
    - **HTTP** (Hypertext Transfer Protocol)
    - **FTP** (File Transfer Protocol)
    - **SMTP** (Simple Mail Transfer Protocol)
    - **POP3** (Post Office Protocol 3)
    - **IMAP** (Internet Message Access Protocol)
    - **DNS** (Domain Name System)
    - **DHCP** (Dynamic Host Configuration Protocol)
    - **SNMP** (Simple Network Management Protocol)
- **Application Layer Services**:
    - File transfer
    - Email services
    - Web browsing
    - Remote login
    - Directory services
- **User-Agent and Server Applications**:
    - Browsers, email clients, FTP clients, etc.
    - Corresponding server applications like web servers, mail servers, etc.
- **Characteristics of Application Layer Protocols**:
    - Connection-oriented vs. connectionless
    - Statefulness vs. statelessness
- **Interoperability and APIs**:
    - Application Programming Interfaces (APIs) for enabling communication between different applications.
- 
- **Web Servers**
- **Mail Servers**
- **DNS Servers**
- **Application Gateways**
- **Database Servers**
- **Proxy Servers**

**`*Collision*`** - occurs when two or more devices attempt to send data over the same network channel simultaneously.

**`*Broadcast*` -** refers to a method of communication where a message is sent from one device to all other devices on a network segment.

**`*Domain*`** - can refer to a logical grouping of network resources for management and security, a network segment for broadcast communications, a structured naming convention for websites in the DNS, or a unique address for web services. The specific meaning depends on the context in which it is used.

**`*Media*`** - In networking, "media" refers to the **physical materials or methods** used to transmit data between devices. It can include any medium that enables communication over a network. The type of media used determines how data is transmitted, including its speed, range, and reliability.

**`*Interface*`** - an **interface** refers to a point of interaction between two systems or devices, typically where communication occurs. It can take several forms depending on the context

**`*Node*`** - nodes can be any device that can send, receive, or process data, such as routers, servers, computers, or other networking devices.

# IMPORTANTTT

### Protocol Data Units (PDUs) in the OSI Model

| **OSI Layer** | **PDU** | **Explanation** |
| --- | --- | --- |
| **Layer 1: Physical** | **Bit** | The smallest unit of data, representing a binary digit (0 or 1). It refers to the physical transmission of data over a medium (e.g., electrical signals, light pulses). |
| **Layer 2: Data Link** | **Frame** | A data unit that includes not only the raw data but also control information like MAC addresses and error checking to ensure reliable transmission over the physical layer. |
| **Layer 3: Network** | **Packet** | A formatted unit of data that contains the source and destination IP addresses. It enables routing of data between different networks. |
| **Layer 4: TransportUDP (User Datagram Protocol)** | **Segment, datagram** | A unit of data that includes the transport layer protocol headers, providing information necessary for establishing and maintaining end-to-end connections (e.g., TCP or UDP headers). |
| **Layer 5: Session** | **Message** | Data that includes session management information, ensuring that sessions are established, maintained, and terminated correctly. |
| **Layer 6: Presentation** | **Message** | Data formatted for presentation, which may include encryption, compression, or translation between different data formats. |
| **Layer 7: Application** | **Message** | The data that applications send and receive. It includes the application-specific protocols (e.g., HTTP, FTP) used for user communication. |