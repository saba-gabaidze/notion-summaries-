# 4.4 Explain security alerting and monitoring concepts and tools.

# Monitoring Computing Resources

**Security Alerting and Monitoring**

A proactive approach to safeguard digital assets by continuously observing and analyzing computing environments to identify potential threats in real-time.

## **Log Files**

- Record system events, errors, user interactions, and security incidents.
- Used for troubleshooting, anomaly detection, and security breach prevention.

## **Security Logs**

- Track authorized and unauthorized access to resources.
- Provide an audit trail and offer early warning of potential intrusions.

## **Systems Monitor**

- Monitor performance metrics of servers, workstations, and endpoints (e.g., CPU usage, memory, network traffic).
- Detect anomalies indicating potential breaches or system failures.

## **Application Monitors**

- Track performance, availability, and security of applications.
- Detect anomalies in application behavior (e.g., unexpected data access, traffic spikes).

## **Infrastructure Monitors**

- Monitor network components, databases, and cloud services for integrity and availability.
- Includes tools like network monitoring software and database activity monitoring.

**Tools for Monitoring Infrastructure:////////////////////////////////**

## **SNMP (Simple Network Management Protocol):**

- Monitors network devices and gathers information through SNMP agents and managers.
- Uses SNMP traps for real-time alerts on issues like hardware failures or high resource utilization.

## **Network Management System (NMS):**

- Uses SNMP data to visualize device statuses and health (e.g., green for healthy, red for critical).

## **NIDS (Network Intrusion Detection Systems):**

- Passive security tools that monitor network traffic for suspicious activities and generate alerts.

## **NIPS (Network Intrusion Prevention Systems):**

- Proactive security tools that detect and block malicious network traffic.
- Can enforce policies and reduce attack surfaces by blocking threats in real-time.

## **Functions of NIDS/NIPS:**

- **Trac Analysis:** NIDS inspects network traffic for unusual patterns or signatures.
- **Alerts & Notifications:** Both NIDS and NIPS alert security teams of potential threats.
- **Proactive vs. Passive:** NIPS actively blocks threats, while NIDS is passive and only detects threats.

# **Activities**

## **Log Aggregation**

1.  Collecting and centralizing logs from various IT systems to provide real-time insight into security events. SIEM systems play a key role in log aggregation, normalizing and analyzing logs for anomalies and potential threats.

## **Alerting**

1.  Setting rules and thresholds within security systems to trigger notifications when suspicious events occur. Alerts enable cybersecurity professionals to address threats before they escalate, using tools like IDS, IPS, and SIEM.

## **Scanning**

1.  Systematically probing systems and networks for vulnerabilities. Automated scanning tools identify weaknesses in software, configurations, and hardware. Regular scans, both credentialed and non-credentialed, reduce the attack surface.

## **Reporting**

1.  Converting monitoring insights into actionable intelligence through structured reports. Key elements include:
    
    ### **Customizable Dashboards**
    
    - for visualizing security metrics.
    
    ### **Compliance Reporting**
    
    - to meet regulatory requirements.
    
    ### **Executive Summaries**
    
    - to provide senior leadership with understandable insights.

## **Archiving**

1.  Storing historical data, including logs and emails, for compliance, data recovery, and post-incident analysis. SIEM systems use archiving policies for long-term data retention, aiding in forensic investigations and ensuring legal compliance.

# **{Alert Response and Remediation/Validation}**

## **Quarantine**

### **Automated Response**

- Systems automatically quarantine based on predefined triggers.

### **Manual Intervention**

- Manual assessment may be required before quarantine.

### **Isolation Duration**

- Determined by alert severity and remediation steps.

## **Alert Tuning**

1.  Optimizing alerts to reduce noise and improve accuracy.
    - **Goals:** Balance accuracy and coverage by fine-tuning thresholds and rules.
    - **Types of Alerts:**
        - **False Positive:** Erroneously flagged as a vulnerability.
        - **False Negative:** Missed vulnerability not detected by the system.
        - **True Positive:** Correctly identified vulnerabilities.
    
    ### **Priority Hierarchy**
    
    - Escalate critical alerts promptly; review less critical ones later.
    
    ### **Misconfiguration**
    
    - Overly sensitive thresholds can overwhelm with irrelevant alerts.

# **Tools**

## **Security Content Automation Protocol (SCAP)**

- A framework for ensuring system compliance and security configurations.

### **OVAL**

- XML schema to describe system security state and vulnerabilities.

### **XCCDF**

- XML format for creating and auditing best practice configuration checklists.

## **Benchmarks**

- Guidelines for securing systems, software, and network devices, developed by CIS and NIST.
- Used by vulnerability scanners to check system compliance with security best practices.

## **Agent vs. Agentless Collection**

- **Agent-based:** Software agents collect data from devices and send it to SIEM for analysis.
- **Agentless:** Gathers data remotely using existing protocols like SNMP and WMI.

## **Security Information and Event Management (SIEM):**

- Monitors events and correlates data for threat detection.
- Functions: Data collection, aggregation, correlation, alerting, and reporting.

## **Antivirus:**

- Scans for malware and suspicious activities, taking actions like deletion or quarantine.

## **Data Loss Prevention (DLP)**

- Prevents sensitive data (e.g., PII) from leaving the network through email or removable devices.
- Uses pattern matching to detect and block sensitive data.

## **SNMP Traps:**

- A protocol for network management where TRAP agents send alerts when anomalies are detected in the network.

## **NetFlow:**

- Cisco-originated technology for tracking network traffic.
- Identifies traffic anomalies and provides alerts on abnormal usage patterns.

## **Vulnerability Scanners:**

- Identifies weaknesses in systems by checking for outdated software, patches, and security misconfigurations.
- Uses CIS Benchmarks and CVSS scores to prioritize vulnerabilities.