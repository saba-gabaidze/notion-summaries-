# Chapter 6 Introduction to Internet Protocol (IP)

# DoD Model

![image.png](Chapter%206%20Introduction%20to%20Internet%20Protocol%20(IP)%2011f9c4fd261480d7bee6fb5520f488e3/image.png)

![image.png](Chapter%206%20Introduction%20to%20Internet%20Protocol%20(IP)%2011f9c4fd261480d7bee6fb5520f488e3/image%201.png)

## Process/Application

 top layer of the OSI model. It provides network services directly to end-user applications, enabling them to communicate over a network

- **Data Representation:** Ensures data is in a usable format (e.g., encoding, compression).
- **Session Management:** Establishes, maintains, and terminates connections between applications.
- **User Interface:** Provides a way for users to interact with applications.

![image.png](Chapter%206%20Introduction%20to%20Internet%20Protocol%20(IP)%2011f9c4fd261480d7bee6fb5520f488e3/image%202.png)

### SSH - 22

Secure Shell (SSH) is a protocol that establishes a secure connection over a standard TCP/IP network, replacing Telnet and older protocols like rsh and rlogin. It allows users to log into remote systems, run programs, and transfer files, all while maintaining a strong, encrypted connection for security.

### Telnet - 23

Telnet is a network protocol used to provide a command-line interface for communicating with a remote device over a TCP/IP network. It allows users to log into another computer or server remotely, enabling them to execute commands as if they were physically present at that machine. Telnet transmits data in plaintext, which means it's not secure

### FTP - 20,21

 to transfer files between a client and a server over a TCP/IP network. It allows users to upload, download, delete, and manage files on a remote server. FTP operates in two modes: active and passive, which determine how the connection is established between the client and server. While FTP is widely used, it transmits data in plaintext, making it less secure than alternatives like SFTP (SSH File Transfer Protocol) and FTPS (FTP Secure), which encrypt data during transmission.

File Transfer Protocol (FTP) is a protocol that enables file transfers between two machines over an IP network. It serves dual purposes: as a protocol for applications and as a program that users can run to manage file tasks manually.

With FTP, users can access both files and directories and perform operations such as moving files between directories. It can also work with Telnet to log into an FTP server, facilitating file transfers.

To access a host via FTP, users must go through an authentication process that usually requires a username and password set by system administrators. However, users can log in as "anonymous," which allows limited access.

When used manually, FTP lets users list directories, view file contents, and copy files between hosts, but its functionalities are relatively basic.

### SFTP

network protocol used to securely transfer files over a secure connection. It operates over SSH (Secure Shell), providing both authentication and encryption to protect data during transit. SFTP allows users to upload, download, and manage files on a remote server securely, ensuring data confidentiality and integrity

### DNS - 53=

Domain Name Service (DNS) translates Internet hostnames, like [www.lammle.com](http://www.lammle.com/), into their corresponding IP addresses. While you can directly use an IP address to connect to a device, DNS simplifies the process by allowing you to use easy-to-remember domain names.

For instance, if you change your web hosting provider and your IP address changes, you can simply update the DNS record without affecting users.

DNS resolves fully qualified domain names (FQDNs), such as [www.lammle.com](http://www.lammle.com/) or todd.lammle.com, which helps identify systems based on their domain. If you want to resolve the name "todd," you need to input the FQDN (todd.lammle.com) or configure your device (like a router) to append the domain automatically. For example, on a Cisco router, the command `ip domain-name lammle.com` can be used to add the domain suffix to requests. Without this setup, you'll need to enter the full FQDN to get the DNS resolution

### TFTP - 69

Trivial File Transfer Protocol (TFTP) is a simplified version of FTP designed for quick and easy file transfers. It’s fast and straightforward to use but lacks many of the features of FTP, such as directory browsing. TFTP can only send and receive files, and it transfers smaller data blocks than FTP. Additionally, it does not have authentication, making it insecure. Due to these security risks, few sites support TFTP.

### NTP - 123

Network Time Protocol (NTP), created by Professor David Mills, synchronizes computer clocks to a single standard time source, typically an atomic clock. This ensures all computers on a network have the same time, which is crucial for time-stamped transactions. Even small time differences can cause issues, so NTP helps keep everything in sync and prevents problems like data mismatches or system crashes.

### SNMP - 161——————-

Simple Network Management Protocol (SNMP) collects and manages network data by polling devices at regular intervals to gather information. It establishes a baseline of normal network behavior and acts as a watchdog, notifying network managers of issues through alerts called traps. SNMP also simplifies network setup and administration.

### NFS —- 2049

Network File System (NFS) is a protocol designed for file sharing between different types of operating systems. It enables interoperability between systems, such as an NT server running NFS server software and a UNIX host running NFS client software.

With NFS, a portion of the RAM on the NT server can transparently store UNIX files, allowing UNIX users to access these files as if they were on their own system. Despite differences in file systems—such as case sensitivity, filename lengths, and security—both UNIX and NT users can access the same files using their standard file management methods.

### Dynamic Host Configuration Protocol (DHCP)/Bootstrap
Protocol (BootP) - 67

Dynamic Host Configuration Protocol (DHCP) automatically assigns IP addresses to devices on a network using information from a server, making it easy to manage networks of any size. Various hardware, including routers, can serve as DHCP servers.

DHCP differs from Bootstrap Protocol (BootP) in that while BootP requires manual entry of a host's hardware address in a BootP table to assign an IP address, DHCP automates this process. You can think of DHCP as an advanced, dynamic version of BootP. However, unlike BootP, DHCP does not have the capability to send an operating system for a host to boot from.

### SMTP - 25

 standard communication protocol used for sending and receiving email messages over the Internet. It operates over TCP

Simple Mail Transfer Protocol (SMTP) is used for sending emails using a spooled method of delivery. When a message is sent, it is temporarily stored on a device, usually a disk, until it can be delivered. The server at the destination regularly checks this queue for incoming messages and delivers them to their final destination. SMTP is specifically for sending mail, while POP3 is used for receiving mail.

### POP - 110

standard protocol used by email clients to retrieve emails from a mail server. It allows users to download their emails from the server to their local device, enabling offline access.

Post Office Protocol (POP), specifically its latest version POP3, provides a way to store incoming emails. When a client device connects to a POP3 server, it downloads all messages addressed to that client. POP3 does not allow selective downloading of messages; once downloaded, the client-server connection ends, and users can manage their emails locally as they wish. Recently, the newer IMAP standard has become more popular as an alternative to POP3.

### IMAP4 - 143

Internet Message Access Protocol (IMAP) offers greater control over how you download your emails, enhancing security in the process. With IMAP, you can preview message headers or download only part of a message, allowing you to manage your emails without fully downloading them first.

IMAP lets you organize messages on the email server in a hierarchical manner and provides links to documents and user groups. It also includes search commands to find messages based on their subject, header, or content. IMAP has strong authentication features, including support for the Kerberos authentication scheme developed by MIT. The current version is IMAP4.

### TLS —- 443

Transport Layer Security (TLS) and its predecessor, Secure Sockets Layer (SSL), are cryptographic protocols used to secure online data transfers, such as web browsing, instant messaging, and internet faxing. They are quite similar,

### SIP (VoIP) - 5060

Session Initiation Protocol (SIP) is a widely used signaling protocol that sets up and manages multimedia communication sessions. It supports various activities, including voice and video calls, video conferencing, streaming multimedia, instant messaging, presence information, and online gaming over the Internet.

### SCP

Secure Copy Protocol (SCP) solves this problem by using SSH to create an encrypted connection between hosts, keeping your files safe during transfer. However, SFTP is now more commonly used than SCP for secure file transfers.

### RTP (VoIP) - 5004

Real-time Transport Protocol (RTP) is a packet-formatting standard for delivering audio and video over the Internet. Originally designed for multicast applications, it is now also used for unicast. RTP is commonly used in streaming media, video conferencing, and push-to-talk systems, making it a de facto standard in the Voice over IP industry.

### LDAP

As a system administrator of a large network, you likely use a directory to manage resources like devices and users. To access these directories, you use the Lightweight Directory Access Protocol (LDAP), which standardizes the process. Earlier versions of LDAP had some issues, but the commonly used third version, described in RFC 3377, resolved them.

### LPD

The Line Printer Daemon (LPD) protocol is used for printer sharing over a network. Along with the Line Printer (LPR) program, it allows print jobs to be queued and sent to network printers using TCP/IP.

### X Window

X Window is a protocol designed for client/server operations using a graphical user interface (GUI). It allows a program (the client) to run on one computer while displaying its interface through a window server on another computer.

### NNTP

Network News Transfer Protocol (NNTP) is used to access Usenet news servers that host message boards called newsgroups. These newsgroups cover a wide range of topics, from classic cars to WWII aircraft. NNTP is defined in RFC 977, but since configuring a news reader can be complex, many people use websites or search engines to access these resources.

### HTTPS - 443

Hypertext Transfer Protocol Secure (HTTPS) is the secure version of HTTP, providing security for transactions between a web browser and server. It encrypts data, helping protect actions like filling out forms, signing in, and making online purchases.

### HTTP - 80

All those snappy websites comprising a mélange of graphics, text, links, and so on—the
Hypertext Transfer Protocol (HTTP) is making it all possible. It’s used to manage communications between web browsers and web servers and opens the right resource when you click a
link, wherever that resource may actually reside.

### IGMP

The Internet Group Management Protocol (IGMP) is used in TCP/IP networks to manage IP multicast sessions. It sends special messages across the network to identify multicast groups and determine which hosts belong to each group. Hosts use IGMP messages to join or leave groups, making it useful for tracking group memberships and active multicast streams.

### LPR

In a pure TCP/IP environment, printing usually involves a combination of Line Printer remote(LPR) and Line Printer Daemon (LPD). LPD, installed on printing devices, manages printers and print jobs. LPR, on the client machine, sends the data from the host to the network printer, resulting in printed output.

# The Host-to-Host Layer Protocols

## TCP

![image.png](Chapter%206%20Introduction%20to%20Internet%20Protocol%20(IP)%2011f9c4fd261480d7bee6fb5520f488e3/image%203.png)

**What is TCP?**

- TCP is a transport layer protocol used to ensure reliable communication between applications over a network. It breaks down large blocks of data from applications into smaller segments for transmission.

**How Does TCP Work?**

1. **Segmentation**:
    - TCP divides application data into smaller segments.
    - Each segment is numbered and sequenced so that the receiving end can reassemble them in the correct order.
2. **Acknowledgment**:
    - After sending segments, TCP waits for the receiving device to acknowledge their receipt.
    - If any segments are not acknowledged, TCP retransmits them.
3. **Connection-Oriented Communication**:
    - TCP establishes a connection between the sender and receiver using a **three-way handshake**:
        - **Step 1**: The sender sends a request to establish a connection.
        - **Step 2**: The receiver acknowledges the request.
        - **Step 3**: The sender confirms the acknowledgment, completing the connection setup.
    - After the data transfer is finished, the connection is terminated.

**Key Characteristics of TCP**:

- **Full-Duplex**: Allows simultaneous sending and receiving of data.
- **Reliable**: Ensures that data is delivered accurately and in order.
- **Error Checking**: TCP includes mechanisms to detect and correct errors.

**Complexity and Overhead**:

- Due to its reliability features, TCP is more complicated and can create more overhead in the network.
- This complexity might be unnecessary in modern networks, which are generally more reliable.

**Data Handling**:

- TCP segments are prepared for the Internet layer, where they are routed as packets.
- Upon reaching the destination, the receiving TCP process reconstructs the original data stream for the application.

## UDP

![image.png](Chapter%206%20Introduction%20to%20Internet%20Protocol%20(IP)%2011f9c4fd261480d7bee6fb5520f488e3/image%204.png)

**User Datagram Protocol (UDP)** is a communication protocol in the Internet Protocol Suite used for transmitting data packets over a network. It is characterized by the following features:

- **Connectionless:** UDP does not establish a connection before data transmission, allowing for faster data transfer.
- **No Guaranteed Delivery:** Unlike TCP, UDP does not ensure that packets arrive at their destination, nor does it guarantee the order of delivery.
- **Lightweight:** UDP has minimal overhead, making it suitable for applications where speed is crucial and occasional data loss is acceptable, such as streaming video, online gaming, and voice over IP (VoIP).
- **Message-Based:** Data is sent in discrete packets, called datagrams, which can vary in size.

Overall, UDP is ideal for applications that prioritize speed and efficiency over reliability.

## Port numbers

A **port number** is a numerical identifier in networking that specifies a particular process or service on a device. It helps direct incoming and outgoing traffic to the appropriate application. Key points include:

- **Range:** Port numbers range from 0 to 65535, with the lower range (0-1023) reserved for well-known services (e.g., HTTP uses port 80, HTTPS uses port 443).
- **Transport Protocols:** Used primarily in TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) communications.
- **Multiplexing:** Allows multiple services to run on a single IP address, enabling efficient data handling and communication.

In summary, port numbers are essential for identifying specific services and managing network traffic.

# Internet Layer

## IP

![image.png](Chapter%206%20Introduction%20to%20Internet%20Protocol%20(IP)%2011f9c4fd261480d7bee6fb5520f488e3/image%205.png)

The **Internet Protocol (IP)** is a fundamental protocol in the Internet Protocol Suite used for routing and delivering data packets across networks. It provides the addressing system that allows devices to identify and communicate with each other over the Internet. Key features include:

- **Addressing:** Each device on a network is assigned a unique IP address, which can be either IPv4 (32-bit) or IPv6 (128-bit).
- **Packet Delivery:** IP handles the forwarding of packets from the source to the destination based on the IP address.
- **Connectionless:** IP is a connectionless protocol, meaning it does not establish a direct connection before sending data, allowing for more efficient use of network resources.

Overall, IP is essential for enabling communication between devices on the Internet.

## ICMP

The Internet Control Message Protocol (ICMP) is a network layer protocol used primarily for diagnostic and error-reporting purposes in IP networks. It facilitates communication between network devices by sending control messages, 

**Internet Control Message Protocol (ICMP)**

ICMP operates at the Network layer and serves as a management and messaging protocol for IP. It communicates various network-related information through IP packets.

**Key Characteristics of ICMP:**

- ICMP messages help identify network problems.
- ICMP packets are encapsulated within IP datagrams.

**Common ICMP Messages and Events:**

1. **Destination Unreachable**: If a router cannot forward an IP datagram, it sends an ICMP message back to the sender to inform them. For example, if a router’s interface is down, it will notify the originating device.
    
    *Example*: When Host A sends a packet to Host B, if the Lab_B router is down, it will return an ICMP **Destination Unreachable** message to Host A.
    
2. **Buffer Full**: If a router's memory buffer for incoming datagrams is full, it uses ICMP to inform the sender until the congestion clears.
3. **Hops**: Each IP datagram has a limit on the number of routers (hops) it can pass through. If it reaches this limit before reaching its destination, the last router discards the datagram and sends an ICMP message back to the sender indicating the datagram was deleted.
4. **Ping**: This utility uses ICMP echo request and reply messages to check the connectivity between devices on a network.
5. **Traceroute**: This tool uses the Time-to-Live (TTL) value in IP packets to discover the route a packet takes across the network.

## ARP

The Address Resolution Protocol (ARP) is a network layer protocol used to map an IP address to a physical MAC (Media Access Control) address in a local area network (LAN).

ARP is used to find the hardware address (also known as the MAC address) of a host when its IP address is known. Here’s how ARP works:

1. **Sending a Datagram**: When the IP layer has a datagram to send, it needs to determine the hardware address of the destination host on the local network. It already knows the destination's IP address from upper-layer protocols.
2. **Checking the ARP Cache**: If the destination's hardware address is not found in the ARP cache (a temporary storage of recently resolved addresses), ARP is used to find it.
3. **Broadcasting a Request**: ARP sends out a broadcast message to the local network, asking the device with the specified IP address to respond with its hardware address. This is essentially translating the IP address into a hardware address (e.g., an Ethernet address).
4. **Receiving the Response**: The device that recognizes the IP address replies with its hardware address, allowing the original sender to complete the communication.

**Example ARP Broadcast**:

- An example ARP broadcast might look like this:
    - **IP Address**: 10.1.1.2
    - **Ethernet Address**: 45:23:79:85:77:34
    - The broadcast message would ask, "I need the Ethernet address of 10.1.1.2."

**ARP Packet Characteristics**:

- An ARP request is sent with a destination hardware address set to all zeros in the ARP header.
- The Ethernet header uses a destination of `FF:FF:FF:FF:FF:FF` to ensure that all devices on the local link receive the ARP request.

**Example ARP Request Packet**:

- **Ethernet Header**:
    - **Destination**: FF:FF:FF:FF:FF(Broadcast)
    - **Source**: 00:A0:24:48:60
    - **Protocol Type**: 0x0806 (ARP)
- **ARP Header**:
    - **Operation**: 1 (ARP Request)
    - **Sender Hardware Address**: 00:A0:24:48:60
    - **Sender IP Address**: 172.16.10.3
    - **Target Hardware Address**: 00:00:00:00:00:00 (not used in request)
    - **Target IP Address**: 172.16.10.10

## RARP

The Reverse Address Resolution Protocol (RARP) is a network layer protocol used to map a physical (MAC) address to an IP address. It is essentially the reverse of the Address Resolution Protocol (ARP), which maps IP addresses to MAC addresses (same as ARP but finds mac with ip)

## Proxy ARP

Proxy ARP allows devices on a subnet to communicate with devices on different subnets without needing to configure routing or a default gateway on each host.

1. **Single Default Gateway Limitation**: Typically, hosts can only have one default gateway. If that gateway fails, the host cannot automatically switch to another router.
2. **Functionality of Proxy ARP**:
    - Proxy ARP allows a router to respond to ARP requests on behalf of another device located on a different subnet.
    - This helps devices think they are on the same subnet, enabling communication without additional configuration.
3. **Advantages**:
    - **Simplicity**: Can be added to a single router without modifying the routing tables of other routers in the network.
    - **Accessibility**: Helps hosts reach remote subnets easily.
4. **Disadvantages**:
    - **Increased Traffic**: Can lead to more network traffic, as ARP requests will be handled by the router.
    - **Larger ARP Tables**: Hosts will maintain more IP-to-MAC address mappings than usual.
5. **Configuration**:
    - Proxy ARP is enabled by default on Cisco routers. If it’s not needed, it’s advisable to disable it.
6. **Nature of Proxy ARP**:
    - It is not a separate protocol but a service that routers provide for devices that cannot directly communicate with remote devices due to subnet separation.

# Data Encapsulation

**Overview**: Data encapsulation is the process of wrapping data with protocol information at each layer of the OSI model as it travels from one device to another. Each layer only communicates with its corresponding layer on the receiving device.

### Key Points:

1. **Protocol Data Units (PDUs)**:
    - Each layer of the OSI model uses PDUs to hold control information.
    - PDUs typically include a header in front of the data and can also include a trailer at the end.
    - Only the peer layer on the receiving device reads the PDU information, which is then stripped away as the data moves up the layers.
2. **Encapsulation Process**:
    - When data is transmitted:
        1. **Application Data**: User information is converted to data for transmission.
        2. **Transport Layer**: Data is divided into segments, and a Transport layer header (PDU) is added. Each segment is sequenced for proper reassembly at the receiving end.
        3. **Network Layer**: Segments are turned into packets by adding a Network layer header with logical addressing (e.g., IP).
        4. **Data Link Layer**: Packets are encapsulated into frames, with headers containing hardware addresses (MAC).
        5. **Physical Layer**: Frames are converted into bits (1s and 0s) for transmission over the network medium.
3. **Decapsulation**:
    - On the receiving device:
        - The Physical layer reads the bits and reconstructs the frame.
        - The Data Link layer checks the frame for errors using a Frame Check Sequence (FCS) and extracts the packet.
        - The Network layer checks the destination address, pulls the segment from the packet, and forwards it to the Transport layer.
        - The Transport layer reassembles the data stream and hands it to the application layer.
4. **Role of Port Numbers**:
    - The Transport layer uses port numbers to define virtual circuits and identify upper-layer processes.
    - Source port numbers start at 1024 for new connections, while destination port numbers identify the specific application receiving the data.
5. **Address Resolution Protocol (ARP)**:
    - The Network layer uses ARP to find the hardware address for local packets or the default gateway address for remote packets.

### Summary of the Encapsulation Steps:

- **User Data** → **Segments (Transport Layer)** → **Packets (Network Layer)** → **Frames (Data Link Layer)** → **Bits (Physical Layer)**.