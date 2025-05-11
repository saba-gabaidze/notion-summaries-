# Network Security 19%

# 4.1

## **Confidentiality, Integrity, Availability (CIA Triad)**

- **Confidentiality**: Ensures that information is only accessible to authorized individuals or systems. It prevents unauthorized access to sensitive data. Common methods to achieve confidentiality include encryption, access control lists (ACLs), and secure authentication mechanisms.
- **Integrity**: Refers to the accuracy and consistency of data. Ensuring data integrity means that information is not altered, corrupted, or tampered with by unauthorized parties. Techniques like hash functions and digital signatures help maintain integrity.
- **Availability**: Ensures that information and systems are accessible and usable when needed by authorized users. This includes ensuring network uptime, system reliability, and protection against denial-of-service (DoS) attacks. Redundancy, load balancing, and failover systems are commonly used to maintain availability.

## **CVE**

- **Common Vulnerabilities and Exposures**
- : CVEs are publicly disclosed vulnerabilities in software or hardware that could potentially be exploited. The CVE system assigns unique identifiers to these vulnerabilities, making it easier to track and address them.

## **Defense in Depth**

Defense in depth is a security strategy that uses multiple layers of defense to protect systems and data. If one layer is breached, other layers will still provide protection. Key components include:

- **Network Segmentation Enforcement**: Dividing the network into segments and restricting communication between them to limit the spread of attacks.
- **Perimeter Network (DMZ)**: A network segment placed between the internal network and the outside world. This zone hosts public-facing services like web servers, which are isolated from the internal network to reduce the risk of external attacks spreading.
- **Separation of Duties**: Ensures that no single individual has control over all aspects of a critical process, reducing the risk of fraud or unauthorized actions.
- **Network Access Control (NAC)**: Enforces policies to ensure that only authorized devices and users can access the network.
- **Honeypot**: A decoy system designed to attract attackers, allowing administrators to monitor attack patterns and gather intelligence about threats.

## **Security Information and Event Management (SIEM)**

SIEM systems aggregate and analyze data from various security devices (firewalls, intrusion detection systems, etc.) to detect, monitor, and respond to security incidents. They provide real-time analysis of security alerts, helping organizations to quickly identify and respond to potential threats.

# 4.2.

# 4.3?

## **Dynamic ARP Inspection (DAI)**

- : Validates ARP packets and ensures that only legitimate ARP responses are processed, helping prevent ARP spoofing attacks.

## **Control Plane Policing (CPP)**

 Controls the traffic directed to the control plane of network devices (like routers and switches) to prevent DoS attacks that target critical infrastructure.

## **Change Default VLAN**

 The default VLAN (usually VLAN 1) should be changed to avoid being the target of attacks that exploit default configurations.

## **Role-Based Access(RBAC)**

 Implement role-based access control (RBAC) to ensure users and devices have appropriate access levels based on their roles within the organization.

## **firewall rules**

 like a security guard at the entrance to a building.

- **Explicit Deny**: This is like telling the guard, "If anyone tries to enter wearing a red shirt, stop them right away!" The guard knows to **specifically** block anyone with a red shirt.
- **Implicit Deny**: This is like saying, "If you don’t have a special pass, the guard will just stop you without asking." So, if someone doesn't have the right permission, they won’t be allowed in, even if no one told the guard to stop them specifically.

## **Wireless Client Isolation**

 Ensures that clients connected to the same wireless network cannot communicate with each other, minimizing the risk of internal attacks between wireless devices.

**Captive Portal**

 A web page that requires users to authenticate before gaining access to the network, commonly used in public Wi-Fi environments like cafes or hotels.

# 4.4

## **Clientless VPN**

- **Description**: A clientless VPN does not require any special VPN client software on the user’s device. It uses a web browser to establish the VPN connection, often through SSL/TLS encryption.
- **Security Implications**:
    - **Encryption**: The use of SSL/TLS ensures the security of data in transit, but it’s only as strong as the web application’s security.
    - **Authentication**: Typically requires multi-factor authentication (MFA) for access control, enhancing security.
    - **Threats**: The reliance on web browsers means security can be compromised if there are browser vulnerabilities or if users do not use secure websites (HTTP vs. HTTPS).

## **Remote Desktop Gateway (RD Gateway)**

- **Description**: RD Gateway acts as a secure gateway for RDP connections over the internet. It uses HTTPS for encrypted communication, enabling remote access without exposing RDP directly to the internet.
- **Security Implications**:
    - **Encryption**: Provides encrypted tunneling of RDP over HTTPS, reducing exposure to attacks.
    - **Authentication**: Integrates with Active Directory and supports MFA for user verification.
    - **Threats**: Exposing RD Gateway to the internet still presents some risks, particularly if not hardened against attacks such as credential stuffing or brute force.

### **Virtual Network Computing (VNC)**

- **Description**: VNC is a remote desktop-sharing system that allows users to control a computer remotely using a graphical interface.
- **Security Implications**:
    - **Encryption**: Older versions of VNC do not provide strong encryption, which could expose sensitive data during remote sessions. Encryption can be added using tunneling protocols like SSH.
    - **Authentication**: Typically requires a password for access, but this can be weak and vulnerable to brute-force attacks.
    - **Threats**: If VNC is exposed directly to the internet without encryption or proper security configurations, it’s vulnerable to attacks.

## **What is VDI?(virtual desktop infrastructure)**

- Imagine you have a **computer** that you use every day, but instead of it being on your desk, it’s **hosted on a powerful server** somewhere else.
- With **VDI**, you can access that computer from **any device** (like a laptop, tablet, or phone), no matter where you are, as long as you have internet access.
- It’s like having your computer on the internet that you can use remotely. Everything you do on the VDI is **stored safely** on the server, not your device.

## **In-band vs. Out-of-band Management**

- **In-band Management**: In-band management refers to managing network devices (like routers and switches) via the same network that the device is part of.
    - **Security Implications**:
        - **Advantages**: Easier to implement as it does not require additional dedicated management networks.
        - **Disadvantages**: Exposes devices to the same vulnerabilities as the rest of the network, and if the network is compromised, so are the management capabilities.
- **Out-of-band Management**: Involves using a separate, dedicated management channel, usually through a serial or IP-based console, that does not rely on the primary network.
    - **Security Implications**:
        - **Advantages**: If the main network is compromised, administrators can still access devices securely through the out-of-band management channel.
        - **Disadvantages**: Requires additional infrastructure and configuration, which can increase costs and complexity.

# !!!!!!!!!!!!!!!!!

### **Summary of Key Points**:

- **DSCP**: Used for traffic classification and prioritization (not redundancy-related).
- **VRRP**: Provides router redundancy by electing a master router and backup routers.
- **IS-IS**: A link-state routing protocol used in large networks for scalability and efficient routing.
- **HSRP**: Cisco proprietary protocol for default gateway redundancy, with backup routers taking over if the active router fails.
- **EIGRP**: Hybrid routing protocol for fast, efficient, and scalable routing in Cisco networks.