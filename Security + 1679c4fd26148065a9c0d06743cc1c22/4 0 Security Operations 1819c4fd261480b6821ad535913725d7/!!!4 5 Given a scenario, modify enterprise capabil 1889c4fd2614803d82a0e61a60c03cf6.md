# !!!4.5 Given a scenario, modify enterprise capabilities to enhance
security.

# Firewall

- **Purpose**: First line of defense against cyber threats, protecting networks by creating rules to allow/block traffic using access lists, ports, and protocols.

## Firewall Types

| **Type** | **Mission** | **Use Case** |
| --- | --- | --- |
| **Host-based** | Protects individual devices (e.g., computers). | Ideal for personal device security. |
| **Network-based** | Safeguards entire networks and entry points. | Protects network borders from unauthorized access. |
| **Stateless** | Basic packet filtering. | Simple use cases without deep-level data inspection. |
| **Stateful** | Deeply analyzes data to prevent DDoS attacks. | Inspects application traffic and behaviors. |
| **Web Application Firewall (WAF)** | Protects web-based apps on servers. | Shields web apps from online threats. |
| **Unified Threat Management (UTM)** | Multi-tasking intrusion prevention, malware scanning, URL filtering, and email filtering, | All-in-one security solution. |
| **Next-Generation Firewall (NGFW)** | Cloud-powered, application-aware. | Advanced protection with intrusion prevention. |
|  |  |  |

---

## Firewall Rules

## **Types of Rules**

### **Inbound**

- Controls external requests entering the network.

### **Outbound**

- Regulates internal network access to external sources.

## **Explicit Allow/Deny**

### **Deny rules**

- Block specific traffic first.

### **Allow rules**

- Specify permitted traffic afterward.

---

## Access Control List (ACL)

- **Default**: Implicit deny ("deny all").
- **Configuration**: Add allow rules for permitted traffic.
- **Example**: Denying FTP requests if no rule for TCP port 21 exists.

---

## **Port Numbers**

- **Well-known Ports (0-1023):** Reserved for core network services like HTTP (80), HTTPS (443), and SMTP (25).
- **Registered Ports (1024-49151):** Used by user processes and applications, such as MySQL (3306) and RDP (3389).
- **Dynamic/Private Ports (49152-65535):** Typically used for ephemeral communication between devices, often dynamically assigned.

# Networking Zones

## **Three Distinct Zones**

### **Wide Area Network (WAN)**

- External public network covering large areas.
- **Untrusted zone**: Origin of potential threats.
- Protected by firewalls to block unauthorized access.

### **Local Area Network (LAN)**

- Internal network covering a small area (e.g., office buildings).
- **Trusted zone**: Houses critical resources and sensitive data.
- Isolated from external access by firewalls.

### **Screened Subnet (DMZ)**

- **Boundary layer** between WAN and LAN.
- Hosts public-facing services (e.g., mail/web servers).
- Accessible to both trusted (LAN) and untrusted (WAN) entities.

---

## **Firewall Configuration: Back-to-Back Firewalls**

- **Firewall 1**: Between WAN and the outer side of the screened subnet.
- **Firewall 2**: Between LAN and the inner side of the screened subnet.
- Segments the zones for better security.

---

### **Zone Definitions**

### **Untrusted Zone (WAN)**:

- Internet-facing, high-risk area.
- Firewalls protect against malicious traffic and unauthorized access.

### **Boundary Layer (DMZ)**:

- Acts as a buffer zone.
- Hosts publicly accessible services while shielding the LAN.

### **Trusted Zone (LAN)**:

- Secure area for internal systems and data.
- Most sensitive part of the network.

---

### **Additional Notes**

- Firewalls segment and secure zones.
- **Intrusion Detection Systems (IDS)** and **Intrusion Prevention Systems (IPS)** work within the network to detect and prevent attacks.

# IDS/IPS

## **Intrusion Detection System (IDS)**

- **Passive**: Detects and alerts about suspicious activities.
- Does not take action to block threats.

## **Intrusion Prevention System (IPS)**

- **Active**: Detects, blocks, and mitigates threats.
- Often placed inline (e.g., NIPS near the firewall).

---

## **Types**

- **Network-based (NIDS/NIPS)**: Operates on the network, not hosts.
- **Host-based (HIDS/HIPS)**: Protects individual devices, not the entire network.

---

## **Trends in IDS/IPS**

### **Machine Learning & AI**

1.  Automates threat detection with pattern recognition.

### **Cloud Security**

1.  Scalable, real-time updates for cloud environments.

### **Zero-Trust Architecture**

1.  Monitors traffic within the network, assuming no trust.

### **IoT/OT Protection**

1.  Inspects IoT and operational technology traffic for vulnerabilities.

---

## **Detection Methods**

1. **Signature-based**: Matches traffic to a database of known threat patterns.
    - Requires frequent updates to remain effective.
2. **Anomaly-based** : Identifies deviations from normal network behavior.
3. **Heuristic-Based Detection:**
- Heuristic detection goes a step further than anomaly-based detection by applying rules or heuristics to recognize malicious activity. It doesn't just compare traffic to an established baseline but also looks for behaviors that fit patterns typical of known attacks.
1. **Custom Signatures**: Tailored to specific organizational needs for unique threats.

# Web Filtering

Web filtering is a critical cybersecurity mechanism designed to **monitor, analyze, and restrict access** to web content based on various factors such as URLs, IP addresses, and content type. It serves as a **protective barrier** that prevents users from accessing malicious or inappropriate web resources, reducing security threats and enforcing organizational policies. Web filtering is widely used in enterprises, educational institutions, and government agencies to **safeguard networks, prevent cyber threats, and boost productivity** by controlling internet usage.

---

## **Agent-Based Filtering**

- Software agents on devices enforce internet filtering rules.
    - Provide real-time protection at host and application levels.
- Operate independently without requiring a central host.

## **Centralized Proxy Filtering**

- Proxy servers intercept and filter internet requests, applying rules before allowing traffic.

## **URL Scanning**

- Compares web addresses to a database of known malicious sites, blocking dangerous matches.

## **Content Categorization**

- Classifies websites into categories (e.g., news, social media).
- Enables blocking or allowing entire categories to enhance productivity and safety.

## **Block Rules**

- Administrators specify websites or content types to block, redirecting users from restricted resources.
- **Domains**
- **Keywords**
- **IP addresses**
- **File types (e.g., .exe, .torrent, .zip)**

## **Reputation-Based Filtering**

- Evaluates website trustworthiness based on history (e.g., malware hosting) and blocks harmful sites.

# Operating System Security

## **Keep System Updated**

- Regularly update OS, software, and applications with the latest security patches.

## **User Account Control (UAC)**

- Prevent unauthorized system changes by prompting for user or admin approval before actions requiring privileges.

## **Minimize Attack Surface**

- Disable unnecessary services and software to reduce potential entry points.

## **Strong Authentication**

- Use complex passwords and enforce regular password changes. Implement two-factor authentication (2FA) for extra security.

## **Access Controls:**

- Apply the principle of least privilege, limiting access to only necessary resources and regularly reviewing permissions.

## **Enable Firewall Protection:**

- Activate firewalls to filter network traffic and allow only trusted connections.

## **Encrypt Data:**

- Encrypt sensitive data both at rest (e.g., using BitLocker, FileVault, LUKS) and in transit (e.g., using TLS).

## **Monitor and Log Activities:**

- Enable system logging, use real-time threat detection tools like EDR, HIDS, or HIPS, and analyze logs for anomalies.

## **Patch Management:**

- Establish a patch management process to apply security patches promptly and mitigate known vulnerabilities.

## **Educate Users:**

- Train users on security best practices, phishing, and suspicious activity recognition.

## **Backup Data:**

- Regularly back up data and system configurations to prevent data loss in case of incidents.

## **Disaster Recovery Plan:**

- Have a plan for system restoration in case of a breach or failure.

---

## **Group Policy:**

- **Domain Level**: A domain GPO applies universally to all users and computers in that domain. For example, you can enforce a password policy that dictates the complexity, length, and expiration of passwords for all users within the domain.
- **Organizational Unit (OU) Level**: A more granular level, where policies can be applied to specific organizational units. This allows for different security or software policies in different departments, teams, or regions.

### **Password Policies**:

- Configured at the domain level (complexity, length, expiration).
- Ensures secure password practices.

### **Account Lockout Policy**:

- Mitigates brute-force attacks by locking accounts after a set number of failed login attempts.
- E.g., lock after 3 failed attempts.

### **Software Installation and Updates**:

- Automates software distribution, updates, and removal across the network.

### **AppLocker**:

- Controls which applications can run by defining rules based on publisher, file path, or hash.
- Prevents unauthorized applications from executing.

### **Desktop Customization**:

- Enforces uniform desktop environments (e.g., wallpaper, browser settings).
- Ensures consistency and security in user environments.

---

## **SELinux (Security-Enhanced Linux)**

SELinux enhances Linux system security by implementing Mandatory Access Control (MAC) rather than the traditional Discretionary Access Control (DAC). It enforces strict security policies that govern how processes, users, and programs interact with system resources.

- **Mandatory Access Control (MAC)**: Enforces system-wide policies, even for system admins.
- **Policy-Based Security**: Uses predefined policies to control actions for processes, users, and resources. These policies can be customized.
- **Least Privilege**: Grants processes and users the minimum privileges needed, limiting potential damage from compromised processes.
- **Isolation and Sandboxing**: Isolates processes to prevent unauthorized access to sensitive files. Includes role-based access control (RBAC) for additional protection.
- **Enforcing vs. Permissive Modes**:
    - *Enforcing*: Blocks actions violating the policy and logs them.
    - *Permissive*: Logs violations but doesn’t block them, useful for troubleshooting.
- **Security Policy Management**: Administrators can define detailed rules for files, processes, and network resources. Predefined policies include targeted, strict, and MLS (Multi-Level Security).
- **SELinux and Kernel-Level Controls**: Enforces policies via kernel mechanisms that check access requests.

# Secure Protocols Implementation

## **1. Protocol Selection:**

- Choose correct secure protocols to ensure a secure environment.
- Example: Use SMTPS (port 587), TCP, for secure email.

## **2. Port Selection:**

- Choose the right ports to open or close in the firewall to reduce attack surface.

## **3. Transport Method:**

- TCP (connection-oriented) and UDP (connectionless) are the two transport methods.

## **Insecure Protocols**

| **Protocol** | **UDP/TCP** | **Port** | **Use Case** |
| --- | --- | --- | --- |
| **FTP** | TCP | 21 | File transfer – passive FTP |
| **Telnet** | TCP | 23 | Run commands on remote hosts (no password encryption) |
| **SMTP** | TCP | 25 | Transport mail between mail servers |
| **DNS** | UDP | 53 | Host name resolution (UDP), Zone transfer (UDP), Name queries (UDP) |
| **DHCP** | UDP | 67/68 | Automatic IP address allocation |
| **TFTP** | UDP | 69 | File transfer using UDP |
| **HTTP** | TCP | 80 | Web browser |
| **POP3** | TCP | 110 | Pulls mail from a mail server (no copy left on server) |
| **NTP** | UDP | 123 | Time synchronization |
| **NETBIOS** | UDP | 137-139 | NETBIOS to IP address resolution |
| **IMAP4** | TCP | 143 | Pulls mail from a mail server |
| **SNMP** | UDP | 161 | Notifies the status and creates reports on network devices |
| **LDAP** | TCP | 389 | Stores X500 objects; searches directory services for users, groups, and other info  |

## **Secure Protocols**

These are secure protocols that offer encryption and other security features, often used to replace insecure versions

| **Protocol** | **UDP/TCP** | **Port** | **Use Case** |
| --- | --- | --- | --- |
| **SSH** | TCP | 22 | Secure remote access |
| **SCP** | TCP | 22 | Secure copy |
| **SFTP** | TCP | 22 | Secure FTP download |
| **DNSSEC** | TCP/UDP | 53 | Secure DNS traffic (TCP/UDP) |
| **Kerberos** | TCP | 88 | Secure authentication |
| **SNMP V3** | UDP | 162 | Secure status and reports on network devices |
| **LDAPS** | TCP | 636 | Securely manages directory service information |
| **HTTPS** | TCP | 443 | Secure web browsing |
| **TLS/SSL** | TCP | 443 | Secure data in transit |
| **SMB** | TCP | 445 | File and print sharing |
| **IPSec** | UDP | 500 | Secure session for VPN or between two hosts |
| **SMTPS** | TCP | 587 | Secure SMTP |
| **S/MIME** | TCP | 993 | Encrypt or digitally sign email |
| **Secure IMAP4** | TCP | 993 | Secure IMAP |
| **Secure POP3** | TCP | 995 | Secure POP3 |
| **FTPS** | TCP | 989/990 | Download large files securely |
| **RDP** | TCP | 3389 | Microsoft remote access |
| **SIP** | TCP/UDP | 5060/61 | Connects internet-based cells |
| **SRTP** | UDP | 5061 | Secure voice traffic |
- **SCP**: Secure file transfer protocol used in Linux environments.
- **SFTP**: Secure file transfer over SSH, ensuring data integrity and confidentiality.
- **DNSSEC**: Protects DNS traffic by digitally signing records, preventing DNS poisoning.
- **Kerberos**: Authentication system using tickets, mutual authentication, and time synchronization to prevent pass-the-hash and replay attacks.
- **SNMP v3**: Secure SNMP version with encryption and authentication for network device monitoring and management.
- **LDAPS**: Encrypted LDAP using TLS for secure access to Active Directory, protects sensitive directory information.
- **HTTPS**: Secures web traffic, commonly used for secure transactions and web forms.
- **TLS**: Successor to SSL, encrypts communications like email and internet traffic.
- **SMB**: Protocol for file and printer sharing in Windows environments.
- **SMTPS**: Secure SMTP using TLS encryption for secure email transmission.
- **IMAP4S**: Secure IMAP for email management with encryption.
- **POP3S**: Secure version of POP3 email protocol, does not store messages on the server.
- **S/MIME**: Uses certificates to encrypt or digitally sign emails, though cumbersome for large-scale use.
- **FTPS**: Secure file transfer using TLS, with implicit and explicit modes for setting up secure sessions.
- **RDP**: Remote desktop access protocol for Windows, requires user configuration for remote access.
- **SIP**: Protocol enabling internet-based communication (e.g., VoIP), used in applications like Teams calls.
- **SRTP**: Secures real-time communication like video conferencing, typically uses TCP port 5061, with VLAN separation for voice traffic.

# **DNS Filtering**

DNS filtering is a security technique that evaluates and controls DNS requests to manage internet access based on policies, enhancing network security and compliance.

## **Blocks malicious sites**

- Prevents access to phishing sites, malware hubs, and known threats.

## **Content filtering**

- Restricts access to specific categories (e.g., social media, gambling) to enforce policies and boost productivity.

## **Enhances privacy**

- Blocks websites that track or collect data without consent, safeguarding personal information.

# **Email Security**

Email security involves using various techniques and protocols to protect email communications from threats like phishing, spam, and unauthorized access. Key methods include encryption, authentication, and email gateways to ensure confidentiality, integrity, and authenticity.

## **Encryption:**

### **S/MIME(993)**

- Uses Public Key Infrastructure (PKI) for email encryption and digital signatures but is cumbersome and not scalable.

### **PGP**

- End-to-end encryption using a pair of keys (public and private) for secure email communication without PKI.

## **Authentication:**

### **DMARC**

- Protocol allowing domain owners to dictate actions when emails fail authentication, such as quarantine or deletion.

### **DKIM**

- Digital signatures on emails for verifying authenticity and preventing tampering.

### **SPF**

- Checks if the sender’s IP is authorized to send emails for a domain, preventing spoofing and phishing.

### **Gateways**

- Email gateways filter spam, malware, and phishing attacks, applying security policies to incoming and outgoing emails. They also use data loss prevention to stop sensitive data from being sent out.

# **File Integrity Monitoring (FIM)**

Tracks and detects unauthorized changes to system files, configurations, and applications.

## **Baseline Creation**

 Establishes a reference state for critical files.

## **Monitoring**

- Continuously or periodically checks files against the baseline.

## **Detection Methods**

- **Cryptographic Hashing (SHA-256, MD5)** – Detects file changes.
- **Signature-Based Detection** – Compares files with known malware signatures.
- **Behavioral Analysis** – Identifies unusual modifications.

## **Response**

- Alerts security teams when unauthorized changes occur.
- **Compliance:** Helps meet PCI DSS, HIPAA, NIST, and ISO 27001 requirements.

# **Data Loss Prevention (DLP)**

- **Purpose:** Prevents unauthorized access, sharing, or exfiltration of sensitive data (PII, financial records, intellectual property).

## **Detection Methods**

- **Pattern Recognition & Regex** (e.g., SSNs, credit card numbers).
- **Data Classification** (categorizes data sensitivity).
- **Contextual Analysis** (metadata, sender, transfer method).

## **Types of DLP**

- **Network DLP** – Monitors data in transit.
- **Endpoint DLP** – Prevents leaks via USBs, local storage.
- **Cloud DLP** – Secures data in cloud apps.
- **Email DLP** – Blocks/encrypts sensitive emails.
- **DLP Actions**
    - **Block & Alert** – Stops unauthorized transfers.
    - **Quarantine** – Holds flagged data for review.
    - **Encrypt** – Secures sensitive data transmission.
    - **Notify Users** – Educates on violations.

# **Key Concepts of Network Access Control (NAC)**

 Ensures devices meet security standards (e.g., fully patched) before accessing the network.

## **Agents**:

### **Permanent Agents**

- Continuously monitor and assess device health.

### **Dissolvable Agents**

- Temporary agents for single-use health checks.

### **Health Authority (HAuth)**

- Inspects device health (patches, antivirus, etc.) after user authentication. Grants access if compliant, quarantines if non-compliant.

### **Remediation Server**

- Provides updates and patches to non-compliant devices in a quarantine network.
- Device authenticates, undergoes health check.
- Compliant device gets network access.
- Non-compliant device is redirected to remediation for updates.
- Once patched, device is reassessed and granted access.

# **Endpoint Detection and Response (EDR)**

Protect endpoints (desktops, laptops, mobile devices, servers) from cyber threats.

## **Data Collection**

1.  Continuous data collection (system logs, file changes, network activity).

## **Detection**

1.  Combines **signature-based** and **behavior-based** analysis to detect threats.

## **Alerting**

1.  Generates alerts prioritized by severity when suspicious activity is detected.

## **Response**

1.  Tools for isolating devices, containing threats, and removing malicious software.
- [x]  **Strength**
- Deep visibility into endpoint activities, allowing for quick threat response.
- **Limitation**: Focuses only on endpoints; doesn't cover network/cloud environments.

---

# **Extended Detection and Response (XDR)**

Provides broader protection by integrating security data from endpoints, network, cloud, and email.

## **Data Integration**

1.  Aggregates data from EDR, NDR (Network Detection and Response), and cloud security.

## **Advanced Analytics**

 Uses **machine learning** to detect complex, multi-stage attacks.

## **Automation & Orchestration**

1.  Automates responses and streamlines incident response workflows.
2. **Scalability**: Scales to meet evolving security needs across various infrastructures.
- **Benefits**:
    - Broader coverage (endpoints, network, cloud).
    - Proactive threat detection and faster automated response.
    - Reduces complexity by integrating multiple security tools.
- **Limitation**: Higher cost and complex implementation compared to EDR.

# **User Behavior Analytics (UBA)**

- Monitors and analyzes user interactions within the network to detect abnormal behavior that could signal potential threats.
- Focuses on deep user activity patterns rather than just surface-level actions.
- Uses machine learning and advanced algorithms to identify deviations from normal behavior.
- Alerts the security operation center when anomalies are detected.
- Tools like **Dynatrace** provide insights indirectly through performance monitoring and session analysis, helping establish a baseline for user behavior.

## **User Behavior Analytics (UBA)**

Monitors user activities within a network to detect anomalies and potential threats.

## **Digital Footprints**

- Tracks user actions (logins, file access, network activity).

## **Pattern Recognition**

- Identifies deviations from normal behavior.

## **Machine Learning**

- Analyzes user data to build a baseline of "normal" behavior.

## **Anomaly Detection**

- Flags suspicious activity (e.g., unusual logins, file access).

## **Alerting**

- Notifies security teams about unusual behavior for further investigation.

## **Real-time & Historical Analysis**

- Monitors activities in real-time and analyzes past behaviors.
- **Tools**:
    - **Dynatrace**: Provides session analysis and performance monitoring to identify behavioral anomalies.
- **UBA Enhances Security**:
    - **Early Threat Detection**: Detects threats early, even when disguised as normal activities.
    - **Insider Threat Detection**: Spots malicious or accidental misuse of access.
    - **Data Exfiltration**: Identifies unusual data transfers indicating potential theft.