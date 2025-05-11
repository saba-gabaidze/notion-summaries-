# 1.2 Summarize fundamental security concepts.

# **Confidentiality, Integrity, and Availability (CIA Triad)**

The CIA Triad is a fundamental concept in digital security, consisting of three core principles that work together to protect digital environments:

- **Confidentiality**: Ensures that sensitive information is kept private and only accessible to authorized individuals. It protects personal data, trade secrets, and confidential material from unauthorized access.
- **Integrity**: Ensures that data remains accurate, consistent, and unmodified. It prevents unauthorized alterations or corruptions, keeping the information trustworthy. Hashing algorithms like SHA-1 or MD5 are used to maintain data integrity.
- **Availability**: Guarantees that digital assets and services are accessible when required. It ensures that systems, data, and online services are operational and available for use whenever needed.

# **Non-Repudiation**

Non-repudiation ensures that actions or transactions cannot be denied

## **Digital Signatures**

Use cryptographic identifiers to confirm the sender’s identity and maintain the integrity of the message content.

## **Audit Trails**

 Track actions in chronological order, which are essential for tracing events and assigning accountability. This helps prevent the denial of actions, such as online transactions, ensuring reliability in e-commerce.

## Access Controls

### **Identification**

 Identifying users by their unique accounts, smart cards, or biometric data (e.g., fingerprints or facial scans).

### **Authentication**

Verifying a user’s identity by checking passwords, PINs, or biometric credentials.

### **Authorization**

 Determining the level of access a user has based on their role (e.g., a sales manager may have access to more data than a regular employee). The **Principle of Least Privilege** ensures that users only access the minimum amount of data necessary for their work.

# **Authentication, Authorization, and Accounting (AAA)**

1. **Authentication (Who are you?)**:
    
    Authentication verifies the identity of users or systems attempting to access a network. It ensures that only authorized users can access the system, helping to prevent security breaches.. The AAA server ensures that only users with correct credentials are allowed to enter.
    
2. **Authorization (What can you do?)**:
    
    After successful authentication, **authorization** determines what actions a user or system is allowed to perform within the network. It defines the scope of activities, ensuring that only authorized actions are taken. This helps prevent unauthorized access to sensitive resources.
    
3. **Accounting (What did you do?)**:
    
    Accounting involves tracking and recording key information such as usernames, timestamps, IP addresses, accessed resources, and actions performed. This data is stored securely and can be used for monitoring, generating reports, troubleshooting, and ensuring compliance with security policies.
    

**AAA Protocols: RADIUS, Diameter, and TACACS+**

- **Remote Authentication Dial-In User Service (RADIUS)**:
    - A widely-used protocol for remote access and network security.
    - Common RADIUS clients include wireless access points, routers, and switches.
    - Authentication requests are sent to a RADIUS server, secured with a **shared secret** known by both the client and server, ensuring the integrity of sensitive data.
- **Diameter**:
    - An advanced version of RADIUS designed for modern networks like 4G and 5G.
    - Clients include devices in LTE and WiMAX infrastructures.
    - Similar to RADIUS, it uses a **shared secret** for secure communication between Diameter clients and servers.
- **Terminal Access Controller Access Control System Plus (TACACS+)**:
    - A protocol developed by Cisco for managing access to network devices.
    - Common clients are routers, switches, and firewalls.
    - It uses a **shared secret** to secure interactions between TACACS+ clients and servers, ensuring secure access control.

# **Gap Analysis**

Gap analysis is a strategic method to evaluate an organization's security measures against industry standards, regulations, and best practices. It identifies "gaps" between the current and desired security states, allowing for targeted improvements.

## **Assessment**

- Review the organization's existing security policies, procedures, and technologies.

## **Benchmarking**

- Compare current practices with industry standards, frameworks, and compliance requirements.

## **Identification**

- Pinpoint specific areas where security measures are insufficient or do not meet the required levels.

## **Prioritization**

- Rank gaps based on their potential risk impact and likelihood of exploitation.

## **Remediation Strategy**

- Develop a detailed plan to address and close the identified gaps, strengthening the organization's security posture.

# **Zero Trust**

Every access request is verified, regardless of whether the request comes from inside or outside the network.

**!CONCEPTS!**

## **Adaptive Identity**

Tailors user privileges based on behavior, location, and device, adjusting dynamically to reduce unauthorized activity and enhance user experience.

## **Threat Scope Reduction**

Prevents threats by minimizing the attack surface (e.g., reducing exposed services, patch management) to preempt potential exploits.

## **Policy-Driven Access Control**

Automates enforcement of security policies to ensure consistent application and eliminate human errors in security protocols.

contorplane!!

## **Policy Engine**

Evaluates who can access network resources, using context (e.g., threat intelligence, user attributes) to inform decisions. Communicates decisions to the policy administrator.

## **Policy Administrator**

Executes decisions made by the policy engine to control access, issuing access tokens and interacting with the data plane.

## **Policy Enforcement Point**

Acts as a security checkpoint, ensuring only authorized actions proceed by following rules set by the policy administrator and policy engine.

# Trust Zones in Networking

## **Implicit Trust Zones**

Areas with assumed trust where components communicate without strict authentication, simplifying interactions but requiring careful management to avoid vulnerabilities.

## **Internal Network Zone**

Trusted internal devices behind the firewall, such as domain controllers and database servers.

## **Demilitarized Zone (DMZ)**

An intermediate zone allowing controlled external access to services; communication with internal networks follows strict controls.

## **External Network Zone**

Untrusted zones like the internet, requiring strong security for communication with internal networks.

---

# Physical Security

- **Bollards**: Sturdy posts that block vehicular threats, securing buildings and public spaces.
- **Access Control Vestibule**: Controlled entry areas where identity is verified before access is granted.
- **Fencing**: Acts as a visible deterrent; modern designs enhance protection.
- **Video Surveillance**: Provides real-time visibility and event records for monitoring and investigations.
- **Security Guards**: Enforce protocols, patrol, and respond to incidents with a human touch.
- **Access Badges**: RFID or smart badges grant entry to secure areas and log access events.
- **Lighting**: Enhances visibility, deters intruders, and aids identity verification.
- **Visitor Logs**: Maintain records of entries/exits for accountability and audits.
- **Sensor Technologies**: Detect threats with minimal human intervention:
    - **Infrared**: Detects heat signatures for perimeter and indoor security.
    - **Pressure**: Identifies movement via touch or step.
    - **Microwave**: Uses frequency alterations to detect moving objects.
    - **Ultrasonic**: Uses sound waves to detect presence in concealed areas.

# Deception and Disruption Technology

## **Honeypot**

A decoy system designed to mimic a legitimate website with lower security. It attracts attackers to study their methods and protect real servers.

## **Honeynet**

 A network of honeypots that serves as a decoy to divert attackers and provides a testing ground for analyzing malicious activities without risking actual networks.

## **Honeyfile**

A seemingly innocent file, like a password file, used to lure attackers. When accessed, it triggers alarms, revealing the intruder’s intent

## **Honeytoken**

 Deceptive, dummy data that appears valuable to attackers. When accessed, it alerts defenders and tracks the intruder’s actions.

## **Fake Information**

 Includes techniques like DNS sinkholes, where DNS queries are redirected to fake addresses, and fake telemetry, where attackers receive false data.