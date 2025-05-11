# 4.8 Explain appropriate incident response activities.

# Process

## **Preparation**

- Develop and maintain an **Incident Response Plan (IRP)**.
- Assemble a **Cybersecurity Incident Response Team (CSIRT)**.
- Establish a **discrete communication plan** for incidents.
- Document **system configurations, network diagrams, and critical assets**.

## **Detection**

- Identify abnormal behaviors using
    - **EDR (Endpoint Detection & Response)**
    - **IDS (Intrusion Detection System)**
    - **Syslog Server & SIEM (Security Information and Event Management)**
- Correlate logs and alerts to detect security incidents.

## **Analysis**

- **SIEM prioritizes and categorizes incidents** using:
    - **MITRE ATT&CK** (attacker techniques & tactics)
    - **Cyber Kill Chain** (stages of attack)
    - **Diamond Model** (attacker, infrastructure, capabilities, victim)

## **Containment**

- **Short-term**: Isolate affected systems, disable compromised accounts.
- **Long-term**: Apply security patches, implement firewall rules.
- Collect volatile evidence for forensic analysis.

## **Eradication**

- **Eliminate the root cause**: Remove malware, delete infected files, patch vulnerabilities.
- Disable unnecessary services to prevent reinfection.

## **Recovery**

- Restore systems securely with **patched and hardened configurations**.
- Meet **Recovery Point Objective (RPO)** (acceptable data loss threshold).
- Validate security before resuming operations.

## **Lessons Learned**

- Conduct a **post-incident review** to improve future responses.
- Update the **Incident Response Plan** and strengthen defenses.

# Attack Framework

MITRE ATT&CK, the Cyber Kill Chain, and the diamond model are key frameworks that help cybersecurity professionals understand, analyze, and respond to cyber threats during incident response.

## **MITRE ATT&CK Framework**

A publicly available knowledge base of real-world adversary tactics, techniques, and procedures (TTPs) maintained by MITRE.

### **Adversarial Profiles**

Detailed information on threat groups (e.g., APT28) including their **history**, **attribution**, and **behavior** patterns.

### **Tactics**

High-level objectives or strategic goals behind an attack (e.g., Initial Access, Execution, Exfiltration).

### **Techniques**

Specific methods used by adversaries to achieve tactics. Techniques include detailed processes (e.g., drive-by compromise) and may have sub-techniques for further granularity.

## **Cyber Kill Chain**

### **1️⃣ Reconnaissance**

- Attackers gather information (social media, email addresses, network scanning).
- Defense: Limit public info, train employees, monitor for suspicious scans.

### **2️⃣ Weaponization**

- Creating malware, malicious attachments, or exploit kits.
- Defense: Sandboxing, IDS, software updates.

### **3️⃣ Delivery**

- Sending attack via phishing emails, USB, malicious websites.
- Defense: Email filtering, phishing training, disabling auto-run.

### **4️⃣ Exploitation**

- Executing payload via vulnerabilities, macros, or scripts.
- Defense: Patch vulnerabilities, disable macros, behavior-based detection.

### **5️⃣ Installation**

- Malware persistence via registry edits, trojans, or rootkits.
- Defense: EDR tools, monitoring registry changes, restricting admin privileges.

### **6️⃣ Command & Control (C2)**

- Infected system connects to attacker's server for remote control.
- Defense: DNS filtering, network monitoring, blocking malicious domains.

### **7️⃣ Actions on Objectives**

- Data theft, ransomware, DDoS, system destruction.
- Defense: Network segmentation, backups, IPS tools.

🔹 **Purpose:** Detect & stop attacks early.

## **Diamond Model of Intrusion**

### **1️⃣ Adversary**

- Who they are what they want (e.g., APT groups, nation-states).
- Identified through threat intelligence, MITRE ATT&CK.

### **2️⃣ Capabilities**

- exploit an adversary develops
to carry out their attack.
- Linked to MITRE ATT&CK techniques.

### **3️⃣ Infrastructure**

- Channels for attack delivery (e.g., C2 servers, USB, phishing).

### **4️⃣ Victim**

- Targeted individual, organization, or system.

🔹 **Purpose:** Break down cyber intrusions into four components: Adversary, Capabilities, Infrastructure, Victim.

🔹 **Integration:** Complements MITRE ATT&CK and Cyber Kill Chain.

# **Incident Response Training**

## **Security Awareness Training**

educating employees about the l**atest
cyber threats**, **safe online practices,** **and their role in
protecting the organization**

## **Security Policies & Procedures**

- Ensures responders follow organizational policies and incident response procedures for consistency.

## **Incident Handling**

- Covers identification, classification, containment, eradication, and recovery of security incidents.

## **Incident Simulations & Drills**

- Hands-on exercises to practice real-world attack scenarios and improve response skills.

## **Communication Skills**

- Teaches clear reporting, internal coordination, and stakeholder communication during incidents.

## **Legal & Regulatory Compliance**

- Ensures understanding of data breach laws, compliance requirements, and legal obligations.

## **Team Collaboration**

- Focuses on role clarity, interdepartmental coordination, and effective teamwork under pressure.

# **Incident Response Testing**

## **Tabletop Exercises**

- Discuss hypothetical disaster scenarios with key stakeholders.
- Identify gaps in the recovery plan and refine communication.
- Minimal setup, paper-based, low cost, but theoretical (no real-world execution).

## **Simulations**

- Simulate disaster situations with a white team overseeing, red team attacking, and blue team defending.
- Adds urgency and competition, more realistic than tabletop exercises.
- Requires more resources, involves real-time pressure, and provides hands-on practice.

# **Root Cause Analysis (RCA)**

## **RCA Focus**

- Identifies the root causes of problems, not just past mistakes.

## **Purpose**

- Helps shape strategic decisions for strengthening systems and preparedness.

# **Threat Hunting**

## **Sources of Information**

- Open-source intelligence (OSINT), threat feeds, advisories, bulletins, and conferences.

## **Objective**

- Understand network dynamics and identify real threats.

## **Intelligence Fusion**

- Combining diverse data sources (OSINT, expert analysis, updates) for a unified defense.

## **Threat Feeds**

- Real-time information aggregating threats from multiple sources (e.g., Cyware, ThreatConnect).

## **Advisories & Bulletins**

- Government and vendor-issued alerts that provide critical security guidance (e.g., OPC Foundation Security Bulletin).

# **Digital Forensics**

## **Collection**

- Gather digital evidence without altering it.
- Use forensic imaging (create exact replicas).
- Document chain of custody (who collected, where stored).
- Preserve evidence integrity using hashing.

## **Examination**

- Re-hash evidence to confirm integrity.
- Use forensic tools (e.g., EnCase, FTK) for analysis.
- Recover deleted files and track user activities.

## **Analysis**

- Interpret data to construct a timeline and identify patterns.
- Use legal methods for admissible evidence.
- Reconstruct events of the crime.

## **Reporting**

**reporting** involves creating a clear timeline of events and showing how pieces of evidence are connected. The findings are then presented in court

## Legal Hold

### **Definition**

- A legal hold is a requirement to preserve data relevant to a legal investigation, preventing alteration or deletion.

### **Implementation**

- Organizations identify pertinent data and notify personnel to safeguard and retain the information.

### **Duration**

- The hold lasts through legal proceedings or until resolved.

### **Consequences of Non-compliance**

- Failure to comply with a legal hold can result in serious legal consequences.

## Chain of Custody

### **Definition**

- Chain of custody ensures the integrity of collected evidence by maintaining its original state.

- **Date and time** of evidence collection.
- **Location** of the evidence.
- **Meticulous packaging**, tagging, and sealing to prevent tampering.

## **Documentation**

- Each person handling the evidence is recorded to create an unbroken chain of custody.

## **Acquisition**

- Collecting evidence from digital and physical sources, ensuring integrity for investigation.

### **Record Time Offset**

- Capture the device’s regional time zone or time setting during evidence collection to accurately interpret timestamps.

### **Time Normalization**

- Converting all timestamps from different time zones into a common reference time zone (e.g., GMT/UTC) to ensure chronological accuracy across evidence sources.

## **Reporting**

- Translates technical findings into clear, concise narratives for legal and non-technical audiences.

- Documents the investigation process, tools used, and procedures followed.

- Summarizes collected evidence, including timestamps, file modifications, and system logs.

- Analyzes the evidence and its significance in the investigation.

## **Preservation**

- Ensures digital evidence remains intact using hashing and encryption.
- **Order of Volatility** Captures the most perishable data first to prevent loss.
    
    ### **CPU Cache**
    
    1. Most volatile, holds real-time processing data.
    
    ### **RAM**
    
    1. Stores active processes, lost on shutdown.
    
    ### **Swap/Page File**
    
    1. Temporary storage when RAM is full.
    
    ### **Hard Drive**
    
    1.  Least volatile, stores long-term data.

## **E-Discovery**

- The process of collecting, searching, and analyzing electronic data for legal evidence.
- **Data Sources**: Includes emails, documents, databases, and digital artifacts.
- **Legal Relevance**: Identifies and preserves crucial digital evidence for investigations and court proceedings.

## **Right-to-Audit Clause**

- A contract provision allowing customers to inspect a supplier’s operations.
- **Purpose**: Ensures compliance, transparency, and accountability.
- **Scope**: Can cover financial records, security practices, and operational procedures.