# 3.2 Given a scenario, apply security principles to secure enterprise
infrastructure.

# Infrastructure considerations!

Securing enterprise infrastructure requires a comprehensive approach, including:

- Assessing risk profile and aligning security with business objectives.
- Understanding evolving threats (cloud computing, remote work, IoT).
- Setting up security zones and organizing device placement.
- Implementing preventative and detective controls.
- Protecting access points and ensuring adaptability.

Adopt a defense-in-depth model with multiple security layers to make it harder for intruders to breach the system. Cultivate a culture of vigilance, continuous learning, and proactive defense.

# **Device Placement in Network Security**

Device placement determines the network’s security, connectivity, and traffic management. It defines how the network will defend, communicate, and operate, serving as the foundation for network design and cybersecurity.

- **LAN (Trusted Zone)**: Internal, secure zone with firewall protections.
- **Screened Subnet (DMZ)**: Boundary layer between trusted and untrusted zones, hosting resources accessible by both zones.
- **WAN (Untrusted Zone)**: Includes the internet, where threats exist; router and ACL filter incoming traffic.

# **Security Zones**

Security zones are distinct network segments with their own security policies, access controls, and trust levels, helping compartmentalize the network and reduce access privileges.

## **Segmentation**

- Divides the network into logical or physical segments (e.g., user roles, device types, data sensitivity).

## **Data Protection**

Sensitive data should be encrypted (FDE) and stored in separate zones (e.g., database servers and file servers). Use DLP and backup data in geographically dispersed cloud regions.

## **Access Control**

 Each zone enforces specific access policies (e.g., DMZ allows external web server access, LAN is limited to employees).

## **Monitoring and Logging**

 Real-time monitoring with SIEM and SOAR systems to maintain data integrity.

## **Isolation**

 Zones contain breaches, preventing lateral spread and reducing threats.

## **Compliance**

 Adheres to regulations (e.g., HIPAA, PCI DSS) for sensitive data protection.

## **Incident Containment**

 Limits lateral movement of attackers, containing breaches and facilitating incident response.

## **Operational Efficiency**

 Streamlines network management, enabling IT admins to focus on specific zones.

## **Defense in Depth**

 Adds security layers to make it harder for attackers to penetrate the network.

# **Attack Surface**

The attack surface encompasses all potential points through which attackers could gain unauthorized access, manipulate data, or disrupt network operations. These entry points are potential vulnerabilities.

## **Endpoints**

- Devices (computers, smartphones, IoT) that connect to the network are prime targets. Vulnerabilities in their OS, software, or configurations can be exploited.

## **Network Services**

Web servers, email servers, and VPN gateways exposed to the internet. Inadequate patching or outdated software creates vulnerabilities.

## **Ports and Protocols**

 Open ports and protocols can be exploited. Unused ports or services should be closed.

## **User Accounts and Credentials**

 Weak or compromised passwords are a significant risk. Brute-force attacks or phishing may be used to steal credentials.

## **Third-party Integrations**

External services or third-party apps can introduce vulnerabilities, requiring regular security assessments.

## **Cloud Services**

 Misconfigured cloud resources can expose sensitive data.

## **Human Factor**

Employees' lack of awareness or malicious intent can increase vulnerabilities. Security training is vital.

**Minimizing the Attack Surface!!!!**

## **Vulnerability Assessment**

- Regularly scan and patch network vulnerabilities.

## Access control

 Implement strict access controls and the
principle of least privilege. Limit user access and permissions to only what’s necessary.

## Network segmentation

Divide your network into segments to limit lateral movement for attackers. This isolates critical
assets from less secure areas.

## **Single Point of Failure**

 Avoid reliance on a single device that could disrupt the entire network.

## **Security Updates**

 Keep software, OS, and devices updated with security patches.

## **Strong Authentication**

 Enforce strong password policies and use Multi-Factor Authentication (MFA) for critical systems.

## Regular auditing

 Conduct regular security audits, penetration testing, and monitoring to detect and respond to suspicious activity. Ensure proper change management controls are in place

## **Security Awareness**

Educate employees on security best practices and how to recognize and report threats.

# **Connectivity**

Connectivity refers to the methods and technologies that enable devices, systems, and people to interact within a networked ecosystem. It includes wired and wireless connections, cloud integrations, remote access, and the pathways through which data flows. Several factors influence how connectivity is established, such as organizational growth, security needs, and the shift toward remote work.

## **Scalability**

As organizations expand, connectivity demands increase. Ensuring the network can scale efficiently while maintaining high performance is crucial.

## **Security**

Greater interconnectivity increases vulnerability to cyber threats. Integrating robust security measures within the connectivity framework is essential.

## **Redundancy**

Redundancy and failover mechanisms are critical to maintaining uninterrupted operations, avoiding disruptions caused by single points of failure.

## **Complexity**

Modern networks involve a variety of components and technologies. Managing this complexity ensures reliable and consistent connectivity.

## **Remote Work**

With the rise of remote work, connectivity plays a pivotal role in enabling seamless collaboration from any location. Reliable and secure remote access solutions are integral to supporting this shift.

# **Failure Modes**

Failure modes describe how a system or device behaves when it experiences a malfunction or failure. Understanding failure modes is essential in ensuring security and resilience in various systems. For example, in bank security, a malfunctioning electric door lock system may automatically lock the door in the event of power loss, preventing unauthorized access.

## **Fail-Closed**

In this mode, the system defaults to a closed or blocked state when a failure occurs. Fail-closed ensures that even during system malfunctions, security is maintained by preventing unauthorized access and minimizing risks such as data breaches or cyberattacks.

## **Fail-Open**

In contrast, a fail-open system defaults to an open state during a failure. This mode creates a security vulnerability by allowing unrestricted access, which could lead to data breaches or malicious exploitation of the failure to gain unauthorized entry.

# **Device Attributes**

Devices within a network play crucial roles in safeguarding and monitoring data flow. Each category of device has distinct functionalities and applications:

## **Active Devices**

Active devices are proactive components of network security, intervening in real-time when threats are detected. They block or mitigate threats to maintain the network's integrity and security. Examples include:

- **Firewalls**: Actively block unauthorized access attempts.
- **Intrusion Prevention Systems (IPSs)**: Detect and prevent known attack patterns in real time.

## **Passive Devices**

Passive devices focus on observation and analysis rather than immediate intervention. They monitor network traffic, analyze patterns, and provide insights into potential threats and vulnerabilities. For example:

- **Intrusion Detection Systems (IDSs)**: Use sensors and collectors to analyze network traffic for suspicious behavior without actively blocking it.

## **Inline Devices**

Inline devices are directly positioned in the data path, actively processing traffic and making real-time decisions to allow or block data packets. Examples include:

- **Firewalls**: Control inbound and outbound traffic.
- **Load Balancers**: Distribute network traffic across servers.
- **IPSs**: Analyze and act upon traffic to prevent threats.

# **Network Appliances**

Network appliances form the backbone of a network’s infrastructure. They are vital for establishing, maintaining, and securing network connectivity, ensuring the smooth and secure flow of data across various segments of an organization’s network. 

## **Jump Server**

- **Purpose**: Intermediary for remote administration and management of critical network components.
- **Function**: Allows IT administrators to securely connect via protocols like Secure Shell (SSH) or Remote Desktop Protocol (RDP) to manage servers, switches, routers, and other infrastructure elements.

## **Proxy Server**

- **Purpose**: Acts as an intermediary between clients and external resources.
- **Functions**:
    - **URL Filtering**: Blocks access to certain websites based on a predefined blocklist.
    - **Content Filtering**: Analyzes website content for inappropriate material based on security policies.
    - **Web Page Caching**: Stores frequently accessed web pages locally to reduce bandwidth usage and increase browsing speed.

**Forward Proxy**

Handles outgoing traffic from internal to external networks.

**Reverse Proxy**

Manages incoming traffic from external networks into a company’s internal network, performing authentication, decryption, and filtering.

## **Intrusion Prevention System (IPS)**

- **Purpose**: Actively identifies and blocks threats.
- **Placement**: Inline with network traffic, typically near firewalls.
- **Function**: Protects the network by detecting and mitigating threats in real time.

## **Intrusion Detection System (IDS)**

- **Purpose**: Passively monitors for suspicious activity.
- **Function**: Detects unauthorized activities using sensors and collectors but does not take action.
- **Variants**:
    - **Network-based (NIDS/NIPS)**: Protects the network.
    - **Host-based (HIDS/HIPS)**: Protects individual hosts.

## **Load Balancer**

- **Purpose**: Distributes network traffic efficiently across multiple servers.
- **Types**:
    - **Layer 4 Load Balancer**: Routes traffic based on packet headers (e.g., destination address or port number).
    - **Layer 7 Load Balancer**: Routes traffic based on application-level content, ideal for web applications and APIs.

## **methods:**

## **Least Utilized Host**

- Directs traffic to the server with the lowest workload.

## **Affinity (Sticky Session)**

- Sends requests from the same client to the same server for session consistency.

## **DNS Round Robin**

- Rotates requests across servers in numerical order, though it cannot detect server status.

## **Sensors**

- **Purpose**: Detect unusual network behavior and security threats.
- **Function**: Identify malware, intrusion attempts, and suspicious data patterns, acting as early warning systems.
- **Application**: Used by IDSs to enhance security monitoring.

# **Port Security**

Port security helps safeguard a network by controlling who can connect to it and what type of traffic is allowed through each port. By restricting access to network switches, port security protects against unauthorized users and potential vulnerabilities. 

## **Sticky MAC**

- **Purpose**: Simplifies port security by recording the MAC addresses of authorized devices.
- **Function**: When a device connects to a port, its MAC address is stored and associated with that port. If the same device reconnects, access is automatically granted. However, if a different device tries to connect, it will be denied since its MAC address does not match the stored "sticky" MAC address.

## **Disabling Ports**

- **Purpose**: A proactive approach to maintain network security.
- **Function**: Administrators review and disable ports or remove cables leading to unused areas to eliminate potential security risks.

## **802.1x Authentication**

- **Function**: Before a connection is established, authentication takes place via a RADIUS server. This process involves verifying the identity of the device or user seeking access using the concepts of:
    - **Supplicants**: Devices seeking access.
    - **Authenticators**: Network devices that grant or deny access.
    - **Authentication Server**: Verifies credentials of the supplicants.

## **Extensible Authentication Protocol (EAP)**

- **Purpose**: Enhances 802.1x security by standardizing authentication across devices.
- **Function**: EAP allows the use of various authentication methods, such as:
    - **EAP-TLS**: Uses Transport Layer Security.
    - **EAP-PEAP**: Protected Extensible Authentication Protocol.
    - **EAP-MD5**: Provides a hashing-based method.

# **Firewall Types**

## **Web Application Firewalls (WAFs)**

- Protect web servers and applications from threats like SQL injection, Cross-Site Scripting (XSS), and DDoS attacks. Operates at Layer 7 (Application Layer) of the OSI model.

## **Unified Threat Management (UTM)**

- An all-in-one security solution that includes malware inspection, Data Loss Prevention (DLP), content filtering, and URL filtering.

## **Next-Generation Firewalls (NGFW)**

 Provides advanced protection at Layer 7 with cloud-powered threat intelligence, deep packet filtering, intrusion prevention, behavioral analysis, and user behavior monitoring to detect insider threats.

## **Layer 4 Firewalls (Stateless)**

 Focuses on basic packet filtering, permitting or blocking packets based on predefined rules. Operates at the Transport Layer and does not perform deep packet inspection.

## **Layer 7 Firewalls (Application Firewall)**

Inspects traffic at the Application Layer, allowing for deep packet inspection, control over specific applications, user activities, and content, providing enhanced security and control.

# Secure Communication/Access!!!!

# **Virtual Private Network (VPN)**

1. **VPN Setup**: A VPN server resides within the company's network, while clients connect via specific software over the internet, enabling cost-effective and secure access for authorized users.
2. **L2TP/IPSec VPN**: Combines L2TP with IPSec for strong encryption and enhanced security.
3. **HTML5 VPNs**: Simple to use, requiring only an HTML5-compatible browser (e.g., Opera, Edge, Firefox, Safari). However, they offer less security compared to L2TP/IPSec.

# **Remote Access**

## **SSH**

- **SSH**: Securely replaces Telnet for remote access to network devices. Supports both command-line and GUI use.
    - **SSH Key Authentication**: Generate key pairs using `ssh-keygen -t rsa` (keys stored in `~/.ssh/`). Add the public key to the server using `ssh-copy-id` or manual methods for secure authentication.

## **RDP**

A Microsoft protocol for secure access to Windows desktops or servers. Used for remote work, IT troubleshooting, and accessing machines with specific capabilities.

- **Setup**: Requires enabling remote sessions and assigning users to a remote desktop user group. RDP cannot be used for Cisco routers or devices with non-Windows operating systems.

# **Tunneling**

**Definition**: Tunneling secures and encrypts data over untrusted networks by creating secure "tunnels" using protocols like TLS and IPSec.

## **TLS**

- Ensures authentication via certificates, followed by credential verification with a RADIUS server. Provides secure communication through the VPN gateway.

## **IPSec**

- Forms secure sessions between clients and servers with two key components:
    - **Authenticated Header (AH)**: Ensures data integrity using SHA-1 or MD5.
    - **Encapsulated Security Payload (ESP)**: Encrypts data with DES, 3DES, or AES and includes a header, payload data, and optional trailer.

## **Internet Key Exchange (IKE)**

Establishes shared keys using Diffie-Hellman (DH) over UDP port 500 for secure session creation. Phases:

- Phase 1: Key exchange using DH.
- Phase 2: Data encryption with DES, 3DES, or AES for secure communication.

## **IPSec Modes**

- **Tunnel Mode**: Encrypts AH and ESP, ideal for VPN sessions from remote locations.
- **Always-On Mode**: Used for site-to-site VPNs, ensuring constant availability with AH and ESP encryption.
- **Transport Mode**: Encrypts only ESP for internal network client/server communication.

# **Software-Defined Wide Area Network (SD-WAN)**

1. **Definition**: SD-WAN enables organizations to connect dispersed branch offices, data centers, and cloud resources over a wide area network (WAN).
2. **Key Features**:
    - **Encryption**: Protects data during transmission across the WAN.
    - **Traffic Routing**: Routes traffic based on application requirements.
    - **Firewall Integration**: Works with firewalls to enhance security.
    - **Centralized Management**: Simplifies managing network security policies across the entire network.

# **Secure Access Service Edge (SASE)**

1. **Definition**: SASE combines security and cloud agility, offering centralized protection and simplified access, no matter the user's location.
2. **Key Features**:
    - **Zero-Trust Model**: Ensures security by verifying all users and devices before granting access.
    - **Identity and Access Management (IAM)**: Manages user identities and controls access.
    - **Threat Prevention**: Includes intrusion prevention and content filtering.
    - **Combines WAN and Cloud Security**: Merges WAN technologies with cloud-based security for comprehensive protection.

# **Selection of Effective Controls!!!!**

- **Preventative Controls**: Placed at the network perimeter to defend against potential threats before they breach the network. They monitor incoming and outgoing traffic to ensure only legitimate data is allowed. Examples: Firewalls, Intrusion Prevention Systems (IPS), Access Control Lists (ACLs).
- **Detective Controls**: Located within the network to track potential intrusions. They monitor network activities to detect security incidents and alert Security Operation Centers (SOCs) if unauthorized access or malicious activity is detected. Examples: Intrusion Detection Systems (IDS), Security Information and Event Management (SIEM) systems, log analyzers.