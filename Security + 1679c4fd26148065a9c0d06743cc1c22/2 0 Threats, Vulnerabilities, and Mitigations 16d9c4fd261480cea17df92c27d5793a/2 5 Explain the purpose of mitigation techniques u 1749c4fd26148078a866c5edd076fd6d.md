# 2.5 Explain the purpose of mitigation techniques used to secure the
enterprise.

# Segmentation

### **Physical Segmentation**

 Uses routers, switches, and firewalls to create isolated network segments. Ideal for large organizations.

### **VLANs**

 Logical segmentation within a switch to group devices by function or department, reducing broadcast traffic

### **Subnetting**

 Divides IP networks into subnets for improved security and network performance.

### **Micro-Segmentation**

Granular control over individual workloads, essential for cloud environments and data centers.

### Benefits of Segmentation!!!!!

**Enhanced Security:** Limits malware spread and protects sensitive data!!!

**Access Control:** Restricts resource access to authorized users or devices.

**Compliance:** Meets industry regulations like PCI DSS and HIPAA.
**Performance Optimization:** Reduces broadcast domains and congestion.

**Isolation of Critical Systems:** Adds extra protection to vital systems.

**Scalability and Agility:** Adapts to growing network requirements without compromising security.

# Access control

## **File and Data ACLs**

- Controls access to files and folders.
- Access levels follow the **principle of least privilege** (e.g., read, write, or execute access based on job roles).
- Example: A sales manager may have read access, while a sales admin has both read and write access to sales data.

## **Network ACLs**

- Implemented on firewalls or routers to regulate network traffic.
- Default rule is “deny all,” with specific **allow rules** added for authorized traffic.

# Application allow list/block list

**Purpose:**

- Prevents unapproved applications, including malware, from executing.
- Example: If a user installs games or malware like ransomware, the allow list ensures only authorized applications are allowed, blocking any unauthorized ones.

**Purpose:**

- Prevents known malicious or vulnerable applications from executing, reducing security risks.
- Enforces compliance and productivity policies (e.g., restricting non-business applications during work hours).

**Benefits:**

- Mitigates the risk of cyberattacks by blocking dangerous or non-compliant software.
- Automatically denies execution of unapproved applications by specifying their names or file paths.

# Isolation+

**Isolation** creates secure, self-contained environments within an enterprise's network to protect critical systems and sensitive data.

**Purpose:**

- Protects critical assets by ensuring they are isolated, even if outer defenses are breached.
- Helps control malware attacks by isolating affected devices, preventing further spread.

**Benefits:**

- Enhances protection for sensitive data and critical systems.
- Contains malware or other security threats by restricting their reach within the network.

# Patching+

**Patching** involves applying regular updates and fixes to systems and applications to protect against security threats.

**Purpose:**

- Fortifies systems by addressing vulnerabilities and increasing resilience to emerging cyber threats.
- Ensures digital assets remain secure and protected from exploitation.

# Encryption+

**Encryption** transforms sensitive data into unreadable code to protect it from malicious interception.

**Purpose:**

- Ensures the confidentiality and integrity of data during transmission and storage.
- Safeguards financial transactions, personal messages, and sensitive corporate data.

# Monitoring

**Purpose:**

- Ensures any deviations from normal behavior are swiftly identified and addressed.
- Monitors logs, traffic patterns, and system behavior for threat detection and alerts the security operations center (SOC).

**Systems for Real-Time Monitoring:**

## **SIEM (Security Information and Event Management)**

- Centralizes and correlates logs from servers and network devices.
- Captures network traffic and reports threats to the SOC(Security Operations Center) for action.

## **SOAR (Security Orchestration, Automation, and Response)**

- Uses AI and ML to detect anomalies, analyze patterns, and make data-driven decisions.
- Automates responses to security incidents with pre-defined playbooks, reducing the need for manual intervention.

# Least privilege+

**Least Privilege** is a security strategy that limits user and system accounts to the minimum permissions required to perform their functions.

**Purpose:**

- Reduces the risk of misuse or exploitation by unauthorized actors.
- Decreases vulnerability to attacks and lowers the chances of insider threats.

**Benefits:**

- Minimizes unnecessary access to digital assets.
- Enhances the overall security posture of the enterprise, safeguarding against potential breaches.

# Configuration enforcement

**Configuration Enforcement** involves implementing and maintaining strict rules and policies to ensure that digital systems and assets follow secure and predefined configurations, minimizing the risk of vulnerabilities and breaches.

## **Standardization**

 Use of CIS(Center for Internet Security Benchmarks) Benchmarks to establish a consistent set of security configurations across devices, software, and systems. This reduces variations and simplifies security management.

## **Vulnerability Mitigation**

Enforcing configurations aligned with best practices and security standards helps proactively address known vulnerabilities, reducing the risk of exploitation and breaches.

## **Compliance Adherence**

 Ensures that organizations meet regulatory requirements, avoiding fines and reputational damage.

## **Automation**

Automates real-time detection and correction of deviations from security policies.

# Decommissioning

**Decommissioning** is the process of retiring assets that are no longer needed within an organization’s infrastructure. These assets could include legacy devices running obsolete operating systems or outdated hardware, some of which may have stored sensitive data. Proper sanitization of this data is crucial.

## **Documentation**

 Keep an asset register that includes all hardware, software, and digital resources. Update the register during decommissioning to ensure accountability. Document the decommissioning process with details like dates, reasons, and responsible parties. This is vital for compliance and auditing purposes.

## **Paper Sanitization**

 The best method is burning. Second is pulping, where paper is turned into slurry. Shredding is less effective, but a crosscut shredder is recommended.

## **Media Sanitization**

 Shredding the media is the best method. Pulverizing with a sledgehammer is second. The least secure method is degaussing, which neutralizes magnetic fields on storage media to make it unreadable. If reusing media, overwrite, format, or wipe it.

# Hardening techniques

Hardening enhances the security of systems and networks by reducing vulnerabilities and minimizing attack surfaces. Key techniques include:

## Encryption

- Converts plaintext to ciphertext to protect data.
- Safeguards confidentiality and integrity even if data is intercepted.

## **Endpoint Protection**

- Secures devices connected to a network.
- Detects and mitigates threats like malware and ransomware.

### **Endpoint Detection and Response (EDR)**

- Continuous monitoring and behavioral analysis.
- Detects threats using threat intelligence and generates alerts. Indicators of Compromise (IoC’s)
- Enables swift response, remediation, and forensic analysis.
- Improves incident response and provides endpoint visibility.

### **Host-Based Intrusion Prevention System (HIPS)+**

- Monitors activities on individual devices to block unauthorized access.
- Includes host-based firewalls for managing network traffic at the device level.

## **Disabling Ports/Protocols**

- Reduces attack surfaces by closing unused ports and restricting risky protocols (e.g., disable Telnet on port 23).
- Use Secure Shell (SSH) for secure remote
- **Telnet (Port 23):** Disable, use SSH instead.
- **NETBIOS (Ports 137-139) & SMB(Server message block port) (Port 445):** Restrict for internal use only.

## **Changing Default Passwords**

- Prevents unauthorized access by replacing widely known factory-set passwords.

## **Removing Unnecessary Software**

- Reduces potential vulnerabilities by limiting attack vectors.