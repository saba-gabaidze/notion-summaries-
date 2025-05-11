# 4.1 Given a scenario, apply common security techniques to
computing resources

# Secure Baselines

- **Secure Baseline**: A foundational set of security configurations and practices for protecting computing resources. Key for safeguarding sensitive data, continuity, and user trust.

---

## Establish

### **CIS Benchmarks**

- Community-driven, industry-recognized guidelines for secure configurations. Regular updates to address emerging threats.

### **STIG**

- U.S. Department of Defense guidelines for securing systems. Iterative assessment and remediation process for aligning with security configurations.

## Deploy

### **Microsoft Group Policy**

- Centralized tool for deploying and enforcing security baselines on Windows systems. Prevents configuration drift.

### **Puppet Forge**

Platform-agnostic tool for deploying baselines across Windows, Linux, and macOS. Leverages open-source modules for flexibility.

## Maintain

### **SCAP Compliance Checker**

- Compares system settings to predefined security requirements, identifies non-compliance, and provides actionable reports.

### **CIS-CAT**

 Evaluates systems against CIS benchmarks. Supports tailored assessments and automated scanning for efficiency.

# Hardening Targets

- **Hardening Targets**: Proactive cybersecurity measures to reduce vulnerabilities, mitigate risks, and strengthen security posture. Change default settings for new devices before placing them on the network.`

---

## **Mobile Devices**

- Use strong passwords/biometric authentication, enable encryption, and keep software up-to-date.

## **Workstations**

 Employ firewalls, antivirus software, and restrict unnecessary user privileges.

## **Switches**

- Change default login credentials.
- Enable port security, VLANs, SSH, disable unused ports, SNMP security, and ACLs.
- Regular firmware updates and network traffic monitoring.

## **Routers**

- Change default passwords, enable firewalls, disable remote management, use SSH for remote access.
- Keep firmware updated, implement ACLs and SNMP security, enable logging.

## **Cloud Infrastructure**

 Use access controls, encryption, and regular security assessments.

## **Servers**

Apply security patches, enforce least privilege, and maintain audit logs.

## **ICS/SCADA**

 Implement network segmentation, physical security, and regular security updates.

## **Embedded Systems**

 Minimize unnecessary services and follow secure coding practices

## **RTOS**

Implement encryption, secure boot, and frequent security evaluations. Change default passwords.

## **IoT Devices**

 Change default settings, use strong authentication, update firmware, and segment IoT traffic.

## **Wireless Access Points**

 Change default password, modify SSID, disable SSID broadcasting, use MAC filtering, and enable WPA3 encryption.

# Wireless Devices

**Installation considerations!!!!!!**

## **Site Survey**

- Essential for optimizing wireless network performance.
- Identifies interference sources: load-bearing walls, cordless phones, microwaves, elevators, metal frames, metal doors, and radio waves.
- Helps determine optimal placement of wireless access points (WAPs).

## **Heat Maps**

- Visualize network coverage and performance.
- Identify areas with poor coverage or malfunctioning WAPs.
- Coverage indicators:
    - **Red/Orange**: Good coverage.
    - **Blue**: Poor/no coverage.
    - Grayscale: Dark gray = good, light gray = weak connectivity.

# Mobile Solutions

## **Mobile Device Management (MDM)**

MDM ensures centralized control, maintenance, and security of mobile devices.

- Enforces encryption, password policies, and app whitelisting.
- Allows remote wipe for lost/stolen devices to prevent data breaches.

---

## **Deployment Models**

### **BYOD (Bring Your Own Device)**

- Personal devices used for work.
- Risks: Company data on personal devices.
- Mitigation: Containerization, strict policies.

### **CYOD (Choose Your Own Device):**

- Company-provided device options.
- Flexibility with security control.

### **COPE (Corporate-Owned, Personally Enabled):**

- Devices owned by the company, for work and personal use.
- Full encryption, strong passwords, and compliance with company policies.

## Connection Methods!

## **1.Wireless Networks**

### **WAP** (Wireless Access Point)

 Provides connection in home networks (wireless router).

### **Ad hoc Network**

- Direct connection between devices (e.g., Wi-Fi Direct).

### **Captive Portal**

- Redirects users for validation before accessing the internet (e.g., airport Wi-Fi).

### **WPS**

- Simplifies connection via button push, no password required.

### **Pre-Shared Key (PSK)**

- Password for network access, e.g., Wi-Fi passwords.

### **Evil Twin Attack**

- Fake SSID network set by attackers to intercept data.

## **2. Bluetooth**

### **Security**

- Disable unnecessary connections, use BLE (Bluetooth Low Energy), and set devices to non-discoverable mode.

### **Authentication**

- Pairing devices with a passkey (avoid default ones).

### **BLE**

- Energy-efficient, random-generated addresses for privacy.

### **Bluetooth Attacks**

- **Bluejacking**: Sending unsolicited messages.
- **Bluesnarng**: Unauthorized access to data.

## **3.Cellular Networks (4G/5G):**

- Provide voice and data services via cell towers and satellites.
- **Security**: Encryption, but still vulnerable to SIM card cloning and eavesdropping.

## **4. NFC (Near-Field Communication):**

- Allows devices to communicate within close proximity (e.g., contactless payments).
- **Security**: Store NFC cards in aluminum pouches to prevent skimming.

## **5. GPS (Global Positioning System):**

- Satellite-based technology for geolocation (used in navigation and tracking).
- **Functionality**: Uses satellites to triangulate location and can transmit data over cellular networks.

### **Mobile Solutions – Other Factors**

### **RFID**

- Tracks assets using radio waves (e.g., theft prevention tags).

### **Geolocation**

- Location tracking via GPS, Wi-Fi, or Bluetooth.

### **Tethering**

- Shares mobile internet with other devices (e.g., laptop).

# Wireless Security Settings

## **Wi-Fi Protected Access 3 (WPA3)**

### **Protected Management Frames (PMF)**:

- Protects against IV attacks. adds protection to management frames exchanged between devices and access points (APs).

### **WPA3-Enterprise**

- Uses Elliptic-Curve Die Hellman Ephemeral ECDHE for government/finance sectors. super-secure version of Wi-Fi encryption meant for high-security environments.

### **SAE**

- Replaces WPA2-PSK, uses secure Die Hellman handshake, and protects against brute-force attacks.

### **Wi-Fi Easy Connect**

- Connect IoT devices with a QR code.

### **Wi-Fi Enhanced Open**

- Encrypts open networks in public places to prevent eavesdropping.

## **AAA/Remote Authentication Dial-In User Service (RADIUS)**

### **Authentication**

- Verifies identity (password, PIN).

## **Authorization**

- Determines access level after authentication.

## **Accounting**

- Logs user activities for security and compliance.

## **RADIUS Clients**

- Servers like VPNs, WAPs, and authenticated switches.

## **Shared Secret**

- Used for communication between RADIUS client and server.

## **Cryptographic Protocols**

### **WEP**

- Outdated and insecure with weak encryption (RC4, 64-bit).

### **WPA**

- Fixes WEP vulnerabilities with RC4 and TKIP, improving security.

### **WPA2**

- Uses AES encryption (128-bit), strong protection for wireless networks.

### **WPA3**

- More secure than WPA2, relies on SAE for encryption.

## **Authentication Protocols**

### **PEAP**

- encrypting the entire authentication process using a secure TLS (Transport Layer Security) tunnel. It is commonly used in wireless networks to protect user credentials and ensure secure authentication.

### **802.1x**

- Controls access based on authentication, requires certificate installation.

### **EAP-TLS**

- Requires a certificate on the endpoint to verify identity.

### **EAP-TTLS**

- Establishes a secure session before authenticating client credentials.

### **EAP-FAST**

- Cisco-developed, session authentication without certificates.

# Application Security

## **Input Validation**

- Ensures data complies with predefined rules, formats, and ranges. Protects against SQL injection, buffer overflow, and integer overflow attacks.

## **Secure Cookies**

- Encrypts cookies to preserve user sessions, preferences, and authentication tokens, reducing risks of data theft and privacy issues.

## **Static Code Analysis**

- Examines source code without executing it to identify vulnerabilities like buffer overflow and integer injection.

## **Code Signing**

- Provides a cryptographic seal to verify software authenticity and integrity. Ensures the code is from a trusted source and untampered.

## **Secure Coding Practices**

- Guidelines to write secure and resilient code, minimizing vulnerabilities. More details: [OWASP](https://owasp.org/).

# Sandboxing and Monitoring

## **Sandboxing:**

- Isolates applications from networks for testing, patching, or malware inspection.
- Uses tools like **Docker** for virtual machines or **Cuckoo** for automated malware inspection.
- Modern browsers (e.g., Chrome, Firefox, Edge) sandbox tabs to contain malicious code without affecting the system.

## **Monitoring:**

- **Purpose**: Detect and respond to threats using logging and alerting systems.
- **Commercial Tools**: Solutions like **Splunk** and **SolarWinds Security Event Manager** enable robust monitoring and incident management.

### **Splunk Process**

- **Data Collection**: Gather IT data (logs, network, etc.).
- **Data Aggregation**: Centralize and organize the data.
- **Real-Time Analysis**: Continuously monitor for threats.
- **Alerting**: Trigger alerts when threats are detected.
- **Detailed Information**: Provide specifics for response.
- **Swift Response**: Security analysts mitigate threats.
- **Reporting**: Generate logs and compliance reports.