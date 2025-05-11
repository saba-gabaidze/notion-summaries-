# Networking Fundamentals 24%

# 1.1 Flags

1. **SYN (Synchronize)**:
    - **Purpose**: Used to initiate a TCP connection.
    - **Role**: The first step in establishing a TCP connection in the **three-way handshake** (SYN, SYN-ACK, ACK).
2. **ACK (Acknowledgment)**:
    - **Purpose**: Acknowledges the receipt of data.
    - **Role**: Ensures reliable data delivery. Every packet sent by the sender has an acknowledgment flag, confirming receipt.
3. **FIN (Finish)**:
    - **Purpose**: Used to gracefully terminate a TCP connection.
    - **Role**: When either side of a connection is done sending data, it sends a FIN flag to indicate it’s finished.
4. **RST (Reset)**:
    - **Purpose**: Resets a TCP connection.
    - **Role**: Can be used when there’s an error, or the connection needs to be aborted unexpectedly. It forces the termination of a connection.
5. **PSH (Push)**:
    - **Purpose**: Tells the receiver to push the data to the application immediately.
    - **Role**: Ensures that data is sent to the receiving application without delay, even if the buffer isn’t full.
6. **URG (Urgent)**:
    - **Purpose**: Indicates that the data in the packet is urgent.
    - **Role**: Signals that the receiver should prioritize this packet before others.
7. **ECE (ECN Echo)**:
    - **Purpose**: Used for **Explicit Congestion Notification (ECN)**.
    - **Role**: Part of congestion control to notify the sender of network congestion.
8. **CWR (Congestion Window Reduced)**:
    - **Purpose**: Used in response to the ECE flag.
    - **Role**: Informs the sender that congestion has been reduced, and the sender should lower its transmission rate.

**Summary of TCP Flags:**

- **SYN**: Initiates the connection.
- **ACK**: Confirms data receipt.
- **FIN**: Closes the connection.
- **RST**: Resets the connection.
- **PSH**: Pushes data immediately.
- **URG**: Marks urgent data.
- **ECE**: Indicates network congestion.
- **CWR**: Signals congestion window reduction.

# 1.2

## WAN technology

### **MPLS**

**Multiprotocol Label Switching**  is a method used in networking to speed up and manage data traffic by directing data from one network node to another based on short path labels rather than long network addresses.

**Key Points:**

1. **Labeling the Data**: In MPLS, data packets are assigned a label when they enter the network. This label contains information about how the packet should be forwarded through the network, making routing decisions faster.
2. **Fast Routing**: Instead of looking at the entire packet header to make routing decisions, routers in an MPLS network simply look at the label to quickly forward the data to the next router along the path.
3. **Path Setup**: MPLS establishes a predetermined, efficient path for the data to travel through the network. This path is known as a **Label Switched Path (LSP)**.
4. **Protocol Independent**: MPLS can work with various types of network protocols, including IP (Internet Protocol), ATM (Asynchronous Transfer Mode), and Frame Relay, which is why it's called "Multiprotocol."
5. **Traffic Engineering**: MPLS allows better control over how data flows through the network, helping to avoid congestion and ensuring efficient use of network resources.

### mGre

Imagine you have a group of friends, and you want to send a special message to all of them at once. Instead of sending individual messages to each friend, you use one special "group message" that everyone can read. This is like **Multipoint Generic Routing Encapsulation (mGRE)**, but for data!

## **Smartjack**

- **Description:** A device installed at the demarcation point, providing a connection between the customer’s equipment and the service provider's network.
- **Characteristics:**
    - Provides a diagnostic point for service providers.
    - Allows for easier monitoring and troubleshooting of the network.

## **NF**

- **Network Function Virtualization**
    - **Description:** The virtualization of network functions (e.g., firewalls, load balancers) to run on commodity hardware rather than dedicated appliances.
    - **Characteristics:**
        - Reduces hardware dependency and costs.
        - Improves flexibility and scalability by running network functions as software.

## Provide Links

### **DSL**

**Digital Subscriber Line**

- **Description:** A broadband internet connection using existing telephone lines.
- **Characteristics:**
    - Relatively low-speed compared to fiber or cable.
    - Availability is limited to areas with DSL infrastructure.

### **Cable**

- **Description:** A broadband connection that uses coaxial cable to deliver internet services.
- **Characteristics:**
    - Higher speeds than DSL but shared bandwidth with neighbors.
    - Widely available in urban areas.

### **Leased Line**

- **Description:** A dedicated

### **Metro-optical**

refers to high-speed fiber optic networks used to connect various locations within a metropolitan area. They offer fast, reliable, and low-latency connections, typically used by service providers for high-bandwidth services like internet and data transfer. These networks are scalable and ideal for connecting data centers, businesses, and homes in urban areas.

# 1.3

## **Twisted Pair Cables**

 These cables consist of pairs of wires twisted together to reduce electromagnetic interference.

- **Cat 5**: Standard for 100Mbps Ethernet.
- **Cat 5e**: Improved version of Cat 5, supports up to 1Gbps Ethernet.
- **Cat 6**: Higher performance, supports 10Gbps for shorter distances.
- **Cat 6a**: Enhanced Cat 6, supports 10Gbps for longer distances.
- **Cat 7**: Provides shielding for each pair, supports 10Gbps over longer distances.
- **Cat 8**: Designed for data centers, supports 25-40Gbps Ethernet.

## **Connector Types**

- **Local Connector (LC), Straight Tip (ST), Subscriber Connector (SC), Mechanical Transfer (MT), RJ**: Various connectors used for fiber optic and copper cables.
- **Angled Physical Contact (APC)** and **Ultra-Physical Contact (UPC)**: Types of fiber connectors for reducing reflection and improving signal quality.
- **RJ11**: Used for phone lines.
- **RJ45**: Standard for Ethernet connections.
- **F-type Connector**: Used for coaxial cables in cable TV and broadband.
- **Transceivers/Media Converters**: Devices used to convert between fiber and copper.
    - **SFP (Small Form-Factor Pluggable)**, **SFP+**, **QSFP**, **QSFP+**: Different types of transceivers for connecting fiber optics with networking equipment.

## **Fiber Optic Connectors**

- **LC**: Small, high-density, push-pull latch, used in data centers and telecom.
- **ST**: Bayonet-style lock, mostly used for multi-mode fiber, older technology.
- **SC**: Robust, push-pull, common in high-density applications and telecom.
- **MT**: High-density multi-fiber, used for advanced networks and multi-fiber cables.
- **Copper Connectors (RJ)**:
    - **RJ45**: Common for **Ethernet** (8 pins).
    - **RJ11**: Smaller, used for **telephone lines** (4-6 pins).
    - **RJ48**: Used for **T1/E1** lines (telecommunications).
    

## **Fiber Optic Contact Types**

- **APC (Angled Physical Contact)**:
    - **Description**: **Fiber optic** connectors with an **angled** end-face.
    - **Features**:
        - The fiber ends are polished at an **8-degree angle**.
        - Reduces **back reflection** of light signals, improving performance.
        - Typically used in **single-mode fiber**.
    - **Usage**: Common in **telecommunications** and **high-performance networks**, where minimizing back reflection is important.
- **UPC (Ultra-Physical Contact)**:
    - **Description**: A **fiber optic** connector with a **flat** end-face that is polished to a higher standard than standard connectors.
    - **Features**:
        - Provides **better contact** between the fiber cores than the standard connector, resulting in lower insertion loss.
        - Slightly **better than SC** or **ST** in terms of **signal quality**.
        - Common for both **single-mode** and **multi-mode** fibers.
    - **Usage**: Used in **high-speed networks**, **data centers**, and **telecom** connections where low insertion loss is critical.

## **Cable Management**

- **Patch Panel/Patch Bay**: Organizes and connects different network cables.
- **Fiber Distribution Panel**: Organizes fiber optic cables.
- **Punchdown Block**: Used for terminating cables into a panel.
    - **66, 110, Krone, Bix**: Types of punchdown blocks.

## **Fiber**

- **100BASE-FX, 100BASE-SX, 1000BASE-SX**: Fiber Ethernet for shorter distances.
- **1000BASE-LX**: Fiber Ethernet for longer distances.
- **10GBASE-SR, 10GBASE-LR**: 10Gbps fiber Ethernet for short and long distances.
- **CWDM, DWDM, WDM**: Advanced fiber technologies for increasing bandwidth through wavelength division multiplexing.

## In practice

# 1.4

## **Choosing the IP Addressing Scheme**

Depending on the needs of the network, you will need to select an appropriate range of IP addresses (IPv4 or IPv6). For private networks, **RFC 1918** provides reserved address ranges:

- **IPv4 Private Address Ranges**:
    - **Class A**: 10.0.0.0 to 10.255.255.255
    - **Class B**: 172.16.0.0 to 172.31.255.255
    - **Class C**: 192.168.0.0 to 192.168.255.255
- **IPv6** uses unique local addresses (ULA) starting with `fc00::/7`.

## **Classful Subnetting**

- **Class A** (0.0.0.0 to 127.255.255.255): Uses a default subnet mask of 255.0.0.0 (or `/8` CIDR), suitable for large networks.
- **Class B** (128.0.0.0 to 191.255.255.255): Uses a default subnet mask of 255.255.0.0 (or `/16` CIDR), suitable for medium networks.
- **Class C** (192.0.0.0 to 223.255.255.255): Uses a default subnet mask of 255.255.255.0 (or `/24` CIDR), suitable for smaller networks.

## **Virtual IP (VIP)**

A **Virtual IP** is an IP address that is shared among multiple devices (often used for load balancing or failover setups).
Let's say you have 3 computers in a room, but instead of giving out 3 different IP addresses (like phone numbers), you give out just **one IP address**. When someone calls, the system decides which computer to send the call to, and it can switch to another computer if the first one is busy or turned off.

## **subinterface**

 is a virtual interface created within a physical network interface. It allows a single physical connection (like a network port or network card) to be used for multiple logical networks.

**Key points:**

- A **subinterface** is like dividing one physical connection into several smaller virtual connections.
- Each subinterface can have its own **IP address** and be assigned to a **different network or VLAN**.
- Subinterfaces are used to support multiple **VLANs** (Virtual Local Area Networks) on the same physical interface, allowing you to manage traffic for different networks separately.

**Example:**

- If a router has a physical interface **eth0**, you can create subinterfaces like **eth0.10**, **eth0.20**, etc., where each subinterface can be assigned to a different VLAN (e.g., **eth0.10** for Sales, **eth0.20** for HR).

## **SLAAC**

**Stateless Address Autoconfiguration** 

**SLAAC** is a mechanism in IPv6 that allows devices to automatically configure their own IPv6 addresses without the need for a DHCPv6 server. SLAAC is part of the IPv6 Neighbor Discovery Protocol (NDP), and it works by utilizing **Router Advertisements** 

# 1.5!

## DHCP  -  67/68

## IMAP - 143

## SNMP - 161/162

## LDAP - 389

## SMB - 445

## SMTP TLS - 587

## LDAPS - 63

## IMAPS - 993

## POP3S - 995

Structured Query Language (SQL) Server 1433
• SQLnet 1521
• MySQL 3306

## • Remote Desktop Protocol (RDP) 3389

• Session Initiation Protocol (SIP) 5060/5061
• IP protocol types

## Ipsec

# 1.6!

### **DHCP**

**(Dynamic Host Configuration Protocol)**

- **Scope**: Defines the range of IP addresses that the DHCP server can allocate to clients. The scope is typically set to match the network subnet and determines the available IP addresses for devices within the network.
- **Exclusion Ranges**: These are specific IP address ranges within the scope that the DHCP server will not assign to devices. This is useful for reserving IP addresses for specific devices or ensuring that certain IPs are not assigned dynamically.
- **Reservation**: A feature that allows the DHCP server to always assign a specific IP address to a specific device (based on the MAC address of the device). This is used for critical devices that need a fixed IP but still need to be managed by DHCP.
- **Lease Time**: The lease time defines how long a device can use a given IP address before it must request a new one from the DHCP server. The lease time can be adjusted depending on the network's needs (e.g., short for devices that frequently join and leave the network, or long for devices that remain connected permanently).
- **Scope Options**: These are additional network configuration settings that DHCP can provide along with the IP address, such as the default gateway, DNS servers, domain name, etc. This helps devices configure their network settings automatically.
- **Available Leases**: The number of IP addresses currently assigned to devices in the network. A DHCP server will track which addresses are in use and which are available for assignment.
- **DHCP Relay**: When a DHCP server is located on a different network, a relay agent is used to forward DHCP requests from clients to the server. This allows a network with multiple subnets to centralize DHCP management.
- **IP Helper/UDP Forwarding**: This is the process of forwarding DHCP requests to the appropriate DHCP server across network boundaries, typically using the IP Helper address on routers.

## **DNS**

 **(Domain Name System)**

**Purpose**: DNS translates human-readable domain names (like [www.example.com](http://www.example.com/)) into IP addresses that computers can understand. It acts as a directory service for the internet or private networks.

- **Record Types**:
    - **Address (A vs. AAAA)**: These records map domain names to IP addresses. An "A" record maps to an IPv4 address, while an "AAAA" record maps to an IPv6 address.
    - **Canonical Name (CNAME)**: This record aliases one domain name to another. For example, `www.example.com` might be a CNAME pointing to `example.com`.
    - **Mail Exchange (MX)**: Specifies the mail server responsible for receiving email for a domain. It includes the priority of the mail server, with lower numbers indicating higher priority.
    - **Start of Authority (SOA)**: Contains authoritative information about a domain, including the primary name server, contact email, and other settings.
    - **Pointer (PTR)**: Used in reverse DNS lookups to map an IP address to a domain name, helping to resolve an IP address to a hostname.
    - **Text (TXT)**: Allows text-based information to be stored in the DNS record. It is often used for things like SPF (Sender Policy Framework) records or domain ownership verification.
    - **Service (SRV)**: Specifies information about available services on a domain, including the port number and protocol.
    - **Name Server (NS)**: Identifies the authoritative DNS servers for a domain.
- **Global Hierarchy**:
    - DNS operates on a hierarchical structure with the **Root DNS servers** at the top level, followed by **Top-Level Domains (TLDs)** like `.com`, `.org`, etc., and then domain-specific servers (e.g., `example.com`).
- **Internal vs. External**:
    - **Internal DNS** refers to DNS services used within a private network, while **External DNS** refers to public DNS services that resolve domain names for websites and services on the internet.
- **Zone Transfers**: A mechanism by which DNS information is shared between DNS servers. A primary DNS server can transfer its records to a secondary DNS server, ensuring redundancy and availability.
- **Authoritative Name Servers**: These are DNS servers that hold the definitive records for a domain. They provide the authoritative answers to queries about that domain.
- **Time to Live (TTL)**: TTL is the duration for which a DNS record is cached by other DNS servers or clients. Once the TTL expires, the cached record is discarded, and a fresh query is made to the authoritative server.
- **DNS Caching**: This process involves storing DNS query results locally to speed up future lookups. It reduces latency and traffic on DNS servers.
- **Reverse DNS/Reverse Lookup/Forward Lookup**:
    - **Forward Lookup**: Translating a domain name (e.g., `www.example.com`) into an IP address.
    - **Reverse Lookup**: Translating an IP address back into a domain name (using PTR records).
- **Recursive Lookup/Iterative Lookup**:
    - **Recursive Lookup**: A type of DNS query where the client requests a complete answer, and the DNS server will fully resolve the domain name or return an error.
    - **Iterative Lookup**: In this approach, the DNS server returns the best answer it can (often a referral to another server) and allows the client to continue resolving it.

## **NTP**

**(Network Time Protocol)**

**Purpose**: NTP is used to synchronize the clocks of computers and devices over a network to ensure consistent timekeeping. Accurate time is crucial for many network services, such as logging, security certificates, and coordination of time-sensitive processes.

- **Stratum**: NTP servers are organized into strata (or levels), where **Stratum 0** devices are highly accurate time sources, such as atomic clocks or GPS systems. **Stratum 1** servers directly connect to Stratum 0 devices, and so on. The higher the stratum number, the further removed the server is from the accurate time source.
- **Clients**: These are devices or systems that synchronize their clocks with an NTP server. Clients send requests to NTP servers and adjust their internal clocks based on the server's time.
- **Servers**: NTP servers provide time synchronization services. They can be Stratum 1 (directly connected to an accurate time source) or higher.

# 1.7!!!!!!!!!!!!!!!!!!

## **Three-Tiered Network Architecture**

The **three-tiered architecture** is one of the most common designs used in large corporate networks and data centers. It divides the network into three layers: **Core**, **Distribution**, and **Access**. Each layer has a distinct role in ensuring efficient data flow and scalability.

- **Core Layer**:
    - This is the backbone of the network and is responsible for high-speed, high-capacity data transmission.
    - It connects various parts of the network, such as the distribution and access layers, and ensures efficient routing and redundancy. The core layer typically uses high-performance switches and routers.
    - The core layer is designed for reliability and fault tolerance, providing minimal downtime in the event of a failure.
- **Distribution/Aggregation Layer**:
    - The distribution layer acts as an intermediary between the core and access layers. It manages routing, filtering, and policy enforcement, and also handles traffic between different VLANs (Virtual Local Area Networks).
    - This layer can aggregate traffic from the access layer and route it to the core layer, providing quality of service (QoS), access control, and security policies.
- **Access/Edge Layer**:
    - The access layer connects end-user devices (like computers, printers, and IP phones) to the network.
    - It is where devices access network resources and services, and it can also include network switches, wireless access points, and other edge devices.
    - This layer provides access control, including user authentication and device connectivity, and connects the end devices to the distribution layer.

### **SDN**

**Software-Defined Networking**

**Software-Defined Networking (SDN)** is an approach that centralizes network management, making it more flexible, programmable, and efficient. SDN separates the control plane (which makes decisions about traffic) from the data plane (which forwards traffic). Here’s a breakdown of SDN layers:

- **Application Layer**:
    - This layer contains applications that use network resources, such as network management tools or network security applications. It interacts with the SDN controller to send networking policies and demands.
    - Examples: Cloud computing applications, load balancers, and virtual private network (VPN) services.
- **Control Layer**:
    - The control layer consists of the SDN controller, which is the central brain of the SDN architecture. It manages the network’s policies, traffic flows, and network configurations.
    - It receives requests from the application layer and translates them into forwarding rules to be sent to the infrastructure layer.
- **Infrastructure Layer**:
    - This layer consists of physical network hardware (e.g., switches, routers) that forwards traffic according to the rules set by the controller.
    - The infrastructure layer is essentially the "hardware" of the network that SDN controls programmatically through the controller.
- **Management Plane**:
    - This plane is responsible for network monitoring, management, and configuration. It provides the tools for administrators to monitor network performance, detect issues, and enforce policies.
    - The management plane may integrate with the application layer for automation and orchestration tasks.

SDN makes networks more agile by allowing administrators to easily reconfigure the network through software, providing dynamic management and enhanced network security.

# 1.8

## **IaC**

**Infrastructure as Code**

is a way to manage and set up computer systems (like servers, networks, and databases) using code instead of doing everything manually. It allows you to automate the process of creating, configuring, and managing virtual resources in a network or cloud environment.

With IaC, you write instructions (code) that describe the exact setup you want. This code can create and configure servers, install software, and manage networks automatically, saving time and reducing mistakes. It’s like giving the computer a recipe to follow instead of setting everything up by hand.

IaC helps to:

- Automate the setup of computer systems.
- Quickly change or update configurations by modifying the code.
- Reduce human errors and improve consistency.

IaC is used for managing **virtual infrastructure** (servers, networks) rather than physical hardware. Tools like **Terraform** and **Ansible** are often used to implement IaC in real-world environments.

## **Private-Direct Connection to Cloud Provider**

- A dedicated, private connection from an organization’s infrastructure to a cloud service provider (e.g., AWS Direct Connect, Azure ExpressRoute).
- **Benefits**: Provides more reliable, secure, and lower-latency connections than the public internet, useful for sensitive applications.

## **Cloud Characteristics and Key Concepts**

1. **Multitenancy**:
    - A cloud architecture where a single instance of a software application serves multiple tenants (clients or organizations).
    - **Benefits**: Cost-efficient, as resources are shared, but each tenant’s data remains isolated and secure.
2. **Elasticity**:
    - The ability of cloud resources to automatically scale up or down based on demand. This ensures that computing resources are efficiently used without over-provisioning.
    - **Benefits**: Cost savings, high availability, and performance optimization.
3. **Scalability**:
    - The ability to increase or decrease cloud resources as needed, either vertically (adding resources to a single instance) or horizontally (adding more instances).
    - **Benefits**: Ensures that cloud infrastructure can grow with demand, improving performance and reducing costs during low-demand periods.
4. **Security Implications**:
    - Cloud security is shared between the cloud provider and the user, with the provider responsible for securing the infrastructure, and the user responsible for securing the applications, data, and access controls.
    - **Risks**: Data breaches, misconfigurations, lack of visibility into cloud resources, and dependency on the provider's security practices.
    - **Best Practices**: Use encryption, secure access controls (e.g., multi-factor authentication), and regular security audits to protect cloud environments.