# Chapter 5 Networking Devices

# Hub&

A **hub** is a basic network device that connects multiple devices in a LAN and broadcasts data to all connected devices, creating one large collision domain.

A hub connects all devices in a star topology by sending any data it receives to all connected devices. It doesn’t manage traffic or recognize data, so every device receives the same broadcast, which can lead to collisions when multiple devices send data at the same time. Hubs are outdated and not recommended for modern networks due to their inefficiency and high collision rates.

# repeater&

A **repeater** is a network device that boosts and extends the signal over long distances by receiving, amplifying, and retransmitting it to prevent signal loss.

Repeaters were commonly used in old networks to extend signal range, but today they’re mainly found as part of hubs. They can still extend an Ethernet segment by 100 meters, but due to added latency, they aren’t recommended. Instead, a wireless network is a better option for long-distance connections, providing better performance without the downsides of repeaters. In modern networks, repeaters and hubs are outdated and should be avoided.

# Modem&

A **modem** (short for modulator-demodulator) is a device that converts digital data from a computer into analog signals for transmission over phone lines, and vice versa, allowing internet access.

## POTS

**Traditional modems** (POTS modems) are commonly found in computers and convert digital signals from your computer into signals that can travel over standard telephone lines. Most modern computers come with these modems built into the motherboard.

## DSL

**(Digital Subscriber Line)** is a high-speed internet technology that transmits digital data over existing telephone lines, allowing simultaneous voice and data services without interruption

**DSL (Digital Subscriber Line)** has largely replaced traditional modems due to its higher data speeds and the ability to use a phone line for both internet and voice calls simultaneously. It operates on higher frequencies (above 3200Hz), allowing for greater bandwidth—up to several megabits per second—while still being compatible with regular phones.

When you sign up for DSL, the provider typically sends you a DSL modem, which connects to a phone line and has an Ethernet port for your computer. This setup often includes a phone line splitter and filters to manage voice and data signals effectively. You may also connect a router, hub, or switch to the modem's Ethernet port for expanded network options.

## Cable Modems

**Cable modems** connect to the internet using your television cable, utilizing unused frequency bands from the cable TV infrastructure. They have a coaxial connector for the cable and an Ethernet port for connecting to computers or networks.

**Cable modems** provide high-speed internet access by connecting to the existing cable TV infrastructure. They use unused frequency bands on the cable lines to deliver data services.

A cable modem typically has a coaxial connector for the TV cable and an Ethernet port for connecting to a computer. You can connect a single PC directly or link the modem to multiple PCs through a hub or switch. Additionally, using a router can enhance your network's capabilities.

# Network Interface Card (NIC)

A **Network Interface Card (NIC)** is a hardware component that allows a computer or device to connect to a network. It facilitates communication over wired (Ethernet) or wireless (Wi-Fi) connections, enabling data exchange with other devices on the network.

Here’s a simplified version of your text about Network Interface Cards (NICs):

---

A Network Interface Card (NIC) connects your computer to a network. It provides the physical and electrical connections needed for communication.

NICs can be either:

- **Expansion cards**: Installed in slots on the motherboard.
- **Integrated**: Built into the motherboard itself.

Most modern PCs and laptops have an Ethernet connector and a wireless network card built in. However, you can still find external wireless cards for older devices.

NICs usually have one or two light-emitting diodes (LEDs) for diagnostics:

- **Link LED**: Lights up when a proper connection to the network is detected.
- **Activity LED**: Flickers to indicate data transmission and reception.

In summary, NICs are essential for networking and come with indicators to help diagnose issues

# Transciver

![image.png](Chapter%205%20Networking%20Devices%2011b9c4fd261480e5966eef33f808f806/image.png)

A transceiver, often referred to as a media converter, is a device that enables communication between different types of media in a network. It converts signals from one medium to another, such as from copper cabling (like Ethernet) to fiber optic cables, allowing data to be transmitted over various distances and formats. Transceivers are essential in networking for extending connectivity, improving signal quality, and integrating different network technologies

An external transceiver, also known as a media converter, is a small device that enables a network interface card (NIC) or other networking devices to connect to different types of media, such as converting electrical signals from copper cabling to fiber-optic signals.

For example, if you have a 100Base-TX switch and want to connect it to another switch using fiber optics, you would connect a fiber transceiver to each switch's transceiver port and link them with fiber-optic cabling.

While many Ethernet devices have built-in transceivers for digital data, an external transceiver is necessary when connecting to different media types. Although they are less common today, they can still be useful in certain networking situations.

# Bridge

A **bridge** is a network device that connects and filters traffic between two or more network segments, allowing them to communicate as a single network. It operates at the data link layer (Layer 2) of the OSI model and helps reduce network collisions by dividing traffic, improving overall network performance.

A transparent bridge is a network device that connects two similar network segments. Its main function is to keep traffic separate on either side of the bridge, effectively breaking up collision domains, which helps reduce network congestion.

Traffic is only allowed to pass through the bridge if it's intended for a device on the other side. This makes bridges useful for connecting segments or dividing a busy network into two parts.

Bridges are software-based, while switches can be seen as hardware-based, multiport versions of bridges. Because they use similar technologies, the terms "bridge" and "switch" are often used interchangeably. However, bridges are now less common in modern networking.

# Switch

A **switch** is a network device that connects multiple devices on a local area network (LAN). It uses MAC addresses to forward data only to the intended recipient, improving network efficiency and reducing collisions compared to hubs. Switches operate at the data link layer (Layer 2) of the OSI model, enabling devices to communicate effectively within a network.

Switches connect multiple segments of a network, similar to hubs, but with three key differences. Unlike hubs, which send all incoming data to every port, switches recognize frames and consider the source and destination MAC addresses, as well as the port on which the frame was received.

When a switch receives a frame, it checks where the frame's destination is located. If the destination is on a different port, the switch forwards the frame only to that specific port. If it can't determine the destination, it floods the frame to all ports except the one it was received on.

While a typical Ethernet switch may look like a hub, switches can vary greatly in size and cost. For now, you can think of a switch as a faster, smarter bridge with more ports, and more details will be covered later in the chapter

# wireless access point(AP)

![image.png](Chapter%205%20Networking%20Devices%2011b9c4fd261480e5966eef33f808f806/image%201.png)

A **wireless access point (WAP)** is a device that allows wireless devices to connect to a wired network using Wi-Fi. It acts as a bridge between the wired network (like a router) and wireless devices, enabling them to access the network and communicate with each other. WAPs are commonly used to extend Wi-Fi coverage in homes, offices, and public areas.

A wireless access point (AP) allows mobile users to connect to a wired network wirelessly using radio frequency technology. APs serve a similar purpose to hubs or switches by connecting multiple wireless (and sometimes wired) devices to form a network.

APs are commonly used to provide Internet access in public spaces like libraries, coffee shops, hotels, and airports. Setting up a wireless access point is straightforward: simply plug it into a wired network, power it on, and it's ready to go! Additionally, WAPs reduce cable clutter and are cost-effective, making them ideal for small business networks.

# Router

A **router** is a networking device that connects multiple devices to the internet and directs data traffic between them. It determines the best path for data to travel across networks, allowing different devices to communicate with each other and access external networks like the internet. Routers often include built-in features like firewalls and Wi-Fi capabilities for wireless connectivity.

A router is a network device that connects different network segments, creating an internetwork. A well-configured router can intelligently determine the best path for data to reach its destination by analyzing network performance data.

For instance, a Small Office, Home Office (SOHO) router provides both wired and wireless access for devices, connecting them to the Internet without requiring additional setup. However, it’s important not to leave the router with its default settings, as this can pose security risks. The configuration process will be discussed in Chapter 12.

Routers can be complex devices with their own operating systems, like Cisco's IOS. You can think of them as dedicated CPUs for routing packets. Their flexibility allows you to configure them to perform functions typically associated with other network devices, such as firewalls, by enabling specific software features.

# Firewall

A **firewall** is a security device or software that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts as a barrier between a trusted internal network and untrusted external networks, helping to prevent unauthorized access and attacks.
A firewall acts as a security guard for your network and is one of the most crucial components to implement, especially since most networks are connected to the Internet. It protects your local area network (LAN) from external threats by blocking unauthorized access and controlling which services your LAN can access online.

Firewalls can filter data packets based on rules set by you or the network administrator, determining what information is allowed to enter or exit the network.

They can be either standalone devices or software installed on a server or router, and they typically have at least two network connections: one to the Internet (the public side) and one to the internal network (the private side). Sometimes, a second firewall is used to create a demilitarized zone (DMZ), which separates servers that handle both public and private data, like web and email servers.

In summary, firewalls are the first line of defense for any network connected to the Internet. Without them, your network is vulnerable to exploitation by anyone with technical knowledge who seeks to access sensitive information or resources.

# DHCP

 (Dynamic Host Configuration Protocol) automatically assigns IP addresses and network settings to devices on a network, making it easier to connect without manually configuring them.

When a device (DHCP client) needs an IP, it sends a broadcast request to the DHCP server. However, if the server is on a different network segment, routers don’t forward these broadcasts by default. To solve this, routers can be configured with an IP helper address to forward the DHCP request as a unicast (direct message) to the DHCP server. This setup can also involve multiple DHCP servers for redundancy.

1. **DHCP Process Overview**:
    ◦ A DHCP client asks for an IP address and other network settings from a DHCP server. This communication happens using the **Bootstrap Protocol (bootP)**, where the client sends a request from port 68, and the server responds from port 67.
    ◦ Initially, the client doesn’t know its own IP or the server’s, so it broadcasts a message to all devices in the network (255.255.255.255).
2. **Client Request (Fig 5.15)**:
    ◦ The client includes its MAC address in the request and asks for several network settings using a **Parameter Request List**. These settings include things like a **subnet mask**, **router**, **DNS server**, and **domain name**.
    ◦ The client also requests a specific IP it had used before.
3. **Server Response (Fig 5.17)**:
    ◦ The server responds with the requested IP address (10.100.36.38), subnet mask, lease time (how long the IP is valid), gateway (router), DNS server(s), and some NetBIOS settings (for name resolution).
4. **Lease Time Importance**:
    ◦ The lease time determines how long a client can use the IP before requesting a renewal. If devices are failing to connect after their lease time expires, it could indicate a DHCP issue.
5. **DHCP Reservations**:
    ◦ The server can reserve specific IPs for important devices (like routers or servers) to ensure they always get the same address without having to assign them manually.

**DHCP Process Overview**:

- ◦ A DHCP client asks for an IP address and other network settings from a DHCP server. This communication happens using the **Bootstrap Protocol (bootP)**, where the client sends a request from port 68, and the server responds from port 67.
- ◦ Initially, the client doesn’t know its own IP or the server’s, so it broadcasts a message to all devices in the network (255.255.255.255).

**Client Request (Fig 5.15)**:

- ◦ The client includes its MAC address in the request and asks for several network settings using a **Parameter Request List**. These settings include things like a **subnet mask**, **router**, **DNS server**, and **domain name**.
- ◦ The client also requests a specific IP it had used before

**Server Response (Fig 5.17)**:

- ◦ The server responds with the requested IP address (10.100.36.38), subnet mask, lease time (how long the IP is valid), gateway (router), DNS server(s), and some NetBIOS settings (for name resolution).

**Lease Time Importance**:

- ◦ The lease time determines how long a client can use the IP before requesting a renewal. If devices are failing to connect after their lease time expires, it could indicate a DHCP issue.

**DHCP Reservations**:

- ◦ The server can reserve specific IPs for important devices (like routers or servers) to ensure they always get the same address without having to assign them manually.

# Multilayer Switch(MLS)

A **multilayer switch** is a network device that operates at both Layer 2 (switching) and Layer 3 (routing) of the OSI model. It can handle traditional switching tasks while also performing routing functions, improving network efficiency by forwarding traffic based on IP addresses in addition to MAC addresses.

# Content Switches

A **content switch** is a network device that directs data traffic based on application-level content, such as web requests or specific data types. It ensures efficient delivery of services like load balancing, improving performance and resource use in a network.

Switches that operate up to OSI Layer 7 are used for advanced tasks, such as load balancing across multiple servers. These devices include:

- Layer 4–7 switches
- Content switches
- Web switches
- Application switches

They handle tasks like managing application data (e.g., HTTP, HTTPS, VPNs), often using Network Address Translation (NAT) to balance traffic. This ensures clients are unaware of which server is responding, and the switches operate with extremely low latency. These switches can also manage encryption, decryption, and digital certificates, reducing the load on servers and boosting network performance.

# IDS/IPS

**IDS (Intrusion Detection System)** and **IPS (Intrusion Prevention System)** are security technologies used to monitor network traffic for suspicious activities.

- **IDS** detects and alerts on potential threats or intrusions but does not take action to block them.
- **IPS** not only detects threats but also actively prevents them by blocking malicious traffic in real-time.

Both systems are essential for maintaining network security and protecting against unauthorized access

An **Intrusion Detection System (IDS)** is a security tool that detects unauthorized activities and attacks on a network, such as unauthorized logins, privilege escalations, viruses, worms, and trojans. While IDS can identify and report suspicious activities, it cannot stop them.

In contrast, an **Intrusion Prevention System (IPS)** actively monitors network traffic in real time to prevent attacks. It can drop malicious packets and shut down ports to stop attacks as they happen. Essentially, IDS detects and alerts, while IPS detects and prevents.

# Load Balancer

A **load balancer** is a device or software that distributes network traffic across multiple servers to ensure no single server becomes overwhelmed. This enhances performance, improves reliability, and provides redundancy, allowing for seamless service delivery and better resource utilization.

A typical router directs incoming packets to their specific IP addresses. However, a **load balancer** can distribute incoming packets across multiple machines that share a single IP address.

Load-balancing routers use various rules to manage network traffic, such as sending data to the least busy machine, ensuring fault tolerance, or choosing the server with the fastest response times. This redundancy and scalability are essential for large networks and e-commerce sites.

For example, if you run a website where customers place orders, a load balancer prevents server overloads by spreading the traffic across several servers. This way, even if one server crashes, your customers can still access the site and place orders, avoiding potential losses.

# Multifunction Network Devices

**Multifunction Network Devices** are equipment that combine multiple networking functions into a single device, enhancing efficiency and reducing space. Examples include routers that also serve as firewalls, switches with integrated wireless access points, and devices that provide both network security and performance monitoring. These devices simplify network management and can lower costs by consolidating hardware.

# DNS

**DNS (Domain Name System)** is a system that translates human-readable domain names (like [www.example.com](http://www.example.com/)) into IP addresses (like 192.0.2.1) that computers use to identify each other on the network. It acts like a phonebook for the internet, allowing users to access websites using easy-to-remember names instead of numerical addresses.

Key Points:

- **Host Name:** This is the name of a device linked to a specific IP address. On the Internet, it forms part of a **Fully Qualified Domain Name (FQDN)**, which combines the host name and the domain name.
- **Name Resolution:** This process finds the IP address associated with a host name. It can be done in several ways:
    - **HOSTS File:** A manually created list of names and IP addresses.
    - **Broadcast Requests:** Asking all devices on the local network for information.
    - **DNS:** The most popular and efficient method today.
    - **Windows Internet Naming Service (WINS):** Used mainly in Windows networks.

### Domain Structure:

- Domains are organized in a hierarchical tree. Here are some top-level domains:
    - **.com:** Commercial organizations.
    - **.edu:** Educational institutions.
    - **.gov:** U.S. government branches.
    - **.mil:** U.S. military branches.
    - **.net:** Network organizations.
    - **.org:** Nonprofit organizations.

### Country-Specific Domains:

Each country has its own domain endings, like:

- **.ca** for Canada
- **.jp** for Japan
- **.uk** for Great Britain
- **.ru** for Russia

The **.com** domain is the largest, followed by **.edu**. Newer domains like **.firm**, **.store**, **.arts**, and **.info** are also gaining popularity due to high demand.

### 

1. **DNS Records**:
    - **A Record**: Links a hostname to an IP address (e.g., `www.company.com IN A 204.176.47.2`).
    - **AAAA Record**: Links a hostname to an IPv6 address.
    - **PTR Record**: Translates an IP address back to a hostname.
    - **MX Record**: Defines mail exchange servers for a domain, allowing for multiple mail servers with priority (e.g., `hostname.company.com IN MX 10 mail.company.com`).
    - **CNAME Record**: Allows a domain to have multiple names (aliases), pointing to an existing hostname (e.g., `ftp.company.com IN CNAME www.company.com`).
2. **DNS Queries**:
    - When you enter a web address, your device sends a DNS query using UDP to port 53 on the DNS server to find out the corresponding IP address.
    - The server responds with the IP address, allowing your device to connect to the web server and request web pages.

### Conclusion

DNS is crucial for navigating the internet, translating user-friendly domain names into machine-readable IP addresses, and managing various record types that enhance email delivery and website access.

# Bandwidth shaper

**Bandwidth Shaper** is a network management technique that regulates data transmission by prioritizing certain traffic types, like streaming and gaming. It ensures these applications have sufficient bandwidth while limiting less critical traffic to prevent congestion. This optimizes network performance, reduces latency, and enhances the user experience for prioritized applications.

- Also known as packet shaping or traffic shaping, bandwidth shaping is a technique used to optimize network performance.
- It controls network traffic by delaying specific packets, which helps lower response times and maximize available bandwidth.

**How It Works**:

- Bandwidth shaping involves setting parameters on certain data streams, delaying the flow of designated packets through the network.
- This allows critical data to be prioritized over less important traffic.

**Importance of Bandwidth Shaping**:

- While it can be beneficial for managing network traffic effectively, implementing a bandwidth shaper can be costly.
- If budget constraints prevent the use of a bandwidth shaper, blocking access to non-work-related sites (like social media and video streaming) can help maintain network efficiency.

# Proxy

A proxy server acts as an intermediary between a client and a destination server. When you send a request to access a website, the request goes to the proxy first. The proxy then forwards your request to the website, retrieves the response, and sends it back to you. This helps with privacy (hiding your IP address), security (filtering harmful content), and performance (caching frequently accessed content).

- A proxy server acts as an intermediary between client machines and other servers, handling client requests and controlling traffic between the local network and the Internet.
- When a client makes a request, the proxy connects to the appropriate server to fulfill that request. It may also modify the request or response or handle the request itself.

**Benefits of Proxy Servers**:

- **Caching**: Proxy servers can store copies of previously requested data, allowing for faster access the next time that data is needed. This speeds up network performance.
- **Traffic Control**: They can limit access to certain websites, helping administrators manage bandwidth and keep users focused on work-related tasks.

**Types of Proxy Servers**:

1. **Caching Proxy Server**:
    - Stores local copies of frequently requested resources.
    - Reduces the amount of bandwidth used and speeds up service requests.
2. **Web Proxy Server**:
    - Creates a web cache, remembering sites you've visited.
    - Makes pages load faster and can automatically fill in your personal information during online transactions.

# CSU/DSU

A **CSU/DSU (Channel Service Unit/Data Service Unit)** is a device used in digital telecommunications to connect end-user equipment, like routers, to a digital circuit, typically provided by a telecom company. It serves two main functions:

1. **CSU**: Provides electrical isolation and protection to the network from the telecommunications carrier. It also ensures the signal quality is maintained and can perform diagnostics on the line.
2. **DSU**: Converts digital data from the end-user equipment into a format suitable for transmission over the digital circuit and vice versa.

In essence, a CSU/DSU acts as an interface between a local area network (LAN) and a wide area network (WAN), allowing data communication over digital lines.

**What is a CSU/DSU?**

- A CSU/DSU (Channel Service Unit/Data Service Unit) is a device commonly used in network equipment rooms for connections like T1 lines or Digital Data Services (DDS).
- It combines two functions:
    - **CSU**: Terminates the line at the customer’s location and provides diagnostics and remote testing.
    - **DSU**: Manages the actual transmission of signals and offers buffering and data flow control.

**Typical Use**:

- The CSU/DSU connects to a router on one end and to a demarcation point on the other, linking your network to the provider’s Wide Area Network (WAN).

**Installation**:

- Both the CSU and DSU are necessary to connect to a digital transmission medium such as a T1 line. Sometimes, these components may be integrated into a router, allowing you to plug the T1 line directly into it.
- If they are separate, you'll need a specific physical layer cable, like V.35, to connect the router to the external CSU/DSU.

# Network Segmentation

**Network segmentation** is the practice of dividing a computer network into smaller, distinct segments or sub-networks. This improves performance, security, and management

When a local area network (LAN) grows too large, it can lead to significant traffic congestion, resulting in slow response times. This congestion is often caused by:

- Too many hosts in a broadcast domain
- Broadcast storms
- Multicasting
- Low bandwidth
- Using hubs for connectivity

To resolve this issue, **network segmentation** is used. This involves breaking up the large network into smaller, more manageable segments using devices like **routers** and **switches**. Here’s a breakdown of how they function:

### Segmentation Devices

1. **Switches**:
    - Break up collision domains, meaning that each port on a switch creates its own collision domain.
    - However, they do not break up broadcast domains, meaning all devices on a switch still hear all broadcasts sent on that segment.
2. **Routers**:
    - Break up both collision and broadcast domains by default.
    - They connect different networks and route packets of data between them.
    - Routers also prevent broadcasts from being forwarded to other networks.

### Network Structure

In a segmented network:

- **Collision Domains**: Each device or segment that can collide with others (such as devices connected to a switch) represents a separate collision domain.
- **Broadcast Domains**: Only routers break up broadcast domains; therefore, every network interface connected to a router forms a separate broadcast domain.

For instance:

- In a network with switches and hubs connected to a router, you may have multiple collision domains (e.g., one for each switch port) but a single broadcast domain if all devices are connected through a hub.

### Advantages of Routers

Routers provide several benefits:

- They don’t forward broadcast packets by default.
- They can filter packets based on Layer 3 (IP address) information.
- They perform functions like packet switching, filtering, internetwork communication, and path selection.

### Performance Considerations

In a well-structured network, using routers and switches efficiently can enhance performance significantly. The optimal design includes:

- Multiple switches to break up collision domains.
- Routers to connect different networks and manage broadcast domains.

### Conclusion

Switches improve network performance by breaking up collision domains, while routers are essential for managing broadcast domains and connecting different networks. Implementing the right devices in your network can lead to better functionality and user experience.

# Switches and Bridges at the Data Link Layer

### Switches:

- **Function**: Switches connect multiple devices in a network, using MAC addresses to forward data frames only to the intended recipient, which reduces network congestion and improves performance.
- **Capabilities**: They can manage multiple connections simultaneously and often support features like VLANs (Virtual Local Area Networks) for improved network organization.

### Bridges:

- **Function**: Bridges connect two or more network segments, filtering traffic and reducing collisions by separating collision domains. They also use MAC addresses to determine whether to forward or filter frames.
- **Capabilities**: Typically used to extend a network or connect different LANs, bridges help manage traffic between segments and can be simpler than switches.

**Layer 2 Switching Overview**

- **Hardware-Based Bridging**: Layer 2 switching is referred to as hardware-based bridging because it uses specialized hardware known as **ASICs** (Application-Specific Integrated Circuits). These can operate at gigabit speeds with low latency, which is the time it takes for a frame to enter and exit a port.
- **Frame Processing**: When a frame passes through a bridge or switch, the device reads the frame and records the **source hardware address** in a **filter table**. This table helps the switch track which port received the frame, allowing it to determine the location of the sending device.
- **Collision and Broadcast Domains**:
    - Each segment connected to a switch has its own **collision domain**, meaning collisions can only occur within that segment.
    - However, all segments connected to the switch are part of the same **broadcast domain**, where broadcast messages are sent to all devices.
- **Layer 2 vs. Layer 3**:
    - Layer 2 devices (switches and bridges) locate specific devices, while Layer 3 devices (routers) locate specific networks.
    - Routing tables for routers map networks, while filter tables for switches map individual devices.
- **Frame Forwarding**:
    - Once a filter table is established, the switch forwards frames only to the segment where the destination address is located. If the destination is on the same segment, the switch blocks the frame from going to other segments (this is called **transparent bridging**).
    - If the destination address isn’t in the filter table, the switch forwards the frame to all segments. If a device responds, the switch updates its filter table.
    - For broadcast addresses, the switch forwards the frame to all connected segments, potentially causing **broadcast storms**, which can slow down network performance. Routers are needed to prevent broadcast storms from spreading.
- **Advantages of Switches**:
    - Each switch port acts as its own collision domain, unlike hubs, which create one large collision domain.
    - Switches allow multiple devices on different ports to transmit simultaneously, while hubs limit communication to one device at a time.

# **Hubs at the Physical Layer**

Hubs are basic networking devices operating at the Physical Layer (Layer 1) of the OSI model. They function as multiport repeaters, connecting multiple devices in a network and facilitating communication between them.

- **Hubs as Repeaters**: A hub functions as a multiple-port repeater. It receives a digital signal, regenerates it, and then forwards it out to all active ports without analyzing the data.
- **Active Hubs**: Similar to basic hubs, active hubs reamplify and transmit received digital signals to all ports, meaning all devices connected to the hub are in the same **collision domain** and **broadcast domain**.
- **Network Characteristics**:
    - **Collision Domain**: All devices connected to a hub share the same collision domain, which means data collisions can occur when multiple devices transmit simultaneously.
    - **Broadcast Domain**: All devices are also in the same broadcast domain, receiving any broadcast messages sent through the hub.
    - **Bandwidth Sharing**: Devices connected to a hub share the same bandwidth, which can lead to network congestion.
- **Network Topology**: Hubs create a physical **star topology** where the hub is the central device, and cables extend outward to each device. However, Ethernet networks operate on a **logical bus topology**, meaning signals travel end-to-end through the network.
- **Limitations**: While hubs and repeaters can extend the coverage area of a LAN segment, they are not recommended for this purpose. Instead, LAN switches or wireless access points (APs) are more efficient and affordable options.

![image.png](Chapter%205%20Networking%20Devices%2011b9c4fd261480e5966eef33f808f806/image%202.png)

###