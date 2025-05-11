# 4.3 Explain various activities associated with vulnerability
management.

# vulnerability
management.

# Identification methods!!!

## Vulnerability Scans

### **Non-Credentialed Scans**

- Limited privileges; identifies vulnerabilities visible externally.

### **Credentialed Scans**

- Elevated privileges; more detailed scans of files, certificates, and account info.

- **Identifies weak points (e.g., outdated software, misconfigurations).**
- **Helps prioritize remediation using CVSS.**
- **Enables continuous monitoring of security posture.**
- **Tool Example: Nessus supports both scan types.**

---

### Security Content Automation Protocol (SCAP)

- **Purpose**: Ensures systems adhere to predefined configuration baselines.

### **OVAL**

- This XML-based format is used to describe system vulnerabilities and security statuses. It helps scanners understand and query security information.

### **XCCDF**

- This XML format is used to create automated configuration checklists. It’s a machine-readable version of best practice guides that were traditionally written for system admins to manually follow. By using XCCDF, scanners can validate compliance with security best practices without human intervention.

## Application Security

 Identifies vulnerabilities in application source code and runtime behavior.

### **Static Analysis**

- Examines code without execution (e.g., injection vulnerabilities).

### **Dynamic Analysis**

- Interacts with the app during runtime to simulate real-world attacks.
- **Special Tools**:
    - **Web Application Scanners**: Detect SQL injection, XSS, and authentication issues.

---

### Package Monitoring

- **Definition**: Tracks vulnerabilities in software components (e.g., libraries, frameworks).
- **Databases**:
    - **CVE**: Public database of disclosed vulnerabilities.
    - **NVD**: Comprehensive vulnerability database.

## !Threat Feeds!

Curated streams providing real-time insights into cyber threats, aggregated from:

**sources:**

### **Security vendors**

- Cybersecurity companies offering the latest threats and vulnerabilities.

### **Government agencies**

- National bodies (e.g., CISA, UK's early warning service) providing threat data.

### **OSINT**

- Open-source intelligence gathered from publicly available sources (forums, social media, dark web).

### **Commercial providers**

- Companies like FireEye and Symantec offer subscription-based threat intelligence.Benefits:
- Early vulnerability detection, enabling proactive patching.
- Context on affected systems, known exploits, and mitigation steps.

### **OSINT Sources**

- [ ]  **Websites and forums**
- Public sites yield information on vulnerabilities and hacker discussions.
- [ ]  **News and media**
- Reports on data breaches and cyberattacks.
- [ ]  **Government reports**:
- Agencies like US-CERT provide vulnerability details.
- [ ]  **Blogs and research papers**
- Insights from cybersecurity experts on vulnerabilities.

### **Proprietary vs. Third-Party Threat Intelligence**

- **Proprietary**: An organization’s own insights, generated internally.
- **Third-Party**: Collective threat data from vendors, open-source communities, and government bodies.Key tools:
- **STIX**: Standardized language for sharing structured threat data.
- **TAXII**: Protocol for automated cyber threat intelligence exchange.
- **SHODAN**: Search engine for Internet of Things (IoT) vulnerabilities.

### **Information-Sharing Organizations (ISOs)**

Facilitate the exchange of cyber threat intelligence and best practices:

### **IOCs**

- Indicators of Compromise (e.g., malicious IPs, malware signatures).

### **TTPs**

- Tactics, Techniques, and Procedures used by attackers.

### **Incident data**

- Narratives of past cyber incidents.

### **Notable ISOs**

- **Cyber Threat Alliance (CTA)**
- Coalition sharing threat intelligence to improve global defenses.
- **Automated Indicator Sharing (AIS)**: US government program to share cyber threat indicators.
- **FIRST**: Global platform for incident response and security teams.
- **ISACs**: Sector-specific organizations (e.g., FSISAC for financial services, H-ISAC for healthcare).
- **MS-ISAC**: Focused on state and local US government entities.

### The Dark Web

- **Tor Network**: Anonymizes users by routing internet traffic through volunteer servers, used for privacy but also attracting cybercriminals and illicit activities.

## Penetration Testing (Pen Testing)

Pen testing identifies vulnerabilities by replicating attack scenarios. Types:

### **Known Environment (White-box)**

1.  Full access to system info for targeted testing.

### **Partially Known Environment (Gray-box)**

1.  Limited information simulating a semi-informed attacker.

### **Unknown Environment (Black-box)**

1.  No prior info simulating an outsider attack.

## Responsible Disclosure & Bug Bounty Programs

### **Responsible Disclosure**

- Ethical hackers report vulnerabilities instead of exploiting them.

### **Bug Bounty**

- Hackers are rewarded for identifying vulnerabilities in an organization’s systems.

## System and Process Audit

System and process audits evaluate the effectiveness, efficiency, security, and compliance of an organization’s systems, workflows, and protocols with regulations. These audits identify improvements, verify compliance, and mitigate risks.

### **Objective Setting**

1.  Define clear goals to guide the audit.

### **Data Collection**

1.  Gather data via interviews, document reviews, observations, and analysis.

### **Evaluation**

1.  Assess data against criteria, standards, and best practices.

### **Reporting**

1.  Document and communicate findings to stakeholders.

### **Recommendations**

1.  Suggest improvements or corrective actions.

### **Follow-Up**

1.  Implement recommendations and track progress for continuous improvement.

**Primary Objectives**

- **Identifying Inefficiencies**: Uncover bottlenecks and redundancies to streamline operations.
- **Ensuring Compliance**: Verify adherence to regulations and industry standards to avoid legal risks.
- **Enhancing Quality**: Improve product and service quality through process evaluation.

# Analysis!!!

## **Confirmation**

### **False Positive**

- Vulnerability incorrectly identified.

### **False Negative**

- A vulnerability not detected by the scanner.

### **True Positive**

- Correct identification of vulnerabilities.

## **Prioritization Tools**

### **CVE**

- A catalog of known vulnerabilities used by scanners to identify issues.

### **CVSS**

- Standardized system to assess vulnerability severity:
    - 9.0–10.0: Critical
    - 7.0–8.9: High
    - 4.0–6.9: Medium
    - 0.1–3.9: Low

## **Vulnerability Classification**

- Categorize vulnerabilities based on their source or impact for effective mitigation.

## **Exposure Factor**

Measures the potential loss if a vulnerability is exploited.

## **Industry/Organizational Impact**

- Different sectors (e.g., finance, healthcare) face specific cybersecurity challenges and prioritize vulnerabilities differently.
- Vulnerabilities can lead to financial loss, reputational damage, operational disruption, or regulatory penalties.

## Risk tolerance

Risk tolerance is the level of risk an organization or person is willing to accept. It helps align vulnerability management with the overall risk management plan by considering how much risk can be handled.

## **Environmental Variables**

 Factors like infrastructure, industry, and regulations influence vulnerability severity and urgency.

# Vulnerability Response and Remediation

Address cybersecurity risks and respond to vulnerabilities using strategies like patching, insurance, segmentation, and compensating controls.

## **Patching**

1.  Regularly update software and systems to address vulnerabilities. Failure to patch exposes systems to cyberattacks. Legacy devices may lack patches due to discontinued vendor support.

## **Insurance**

1.  Cybersecurity insurance helps recover financial losses from cyber incidents. It’s not a substitute for strong cybersecurity practices but serves as a safety net.

## **Segmentation**

1.  Divide networks into isolated segments to limit lateral movement of attackers. This minimizes the impact of breaches, especially when handling sensitive data.

## **Compensating Controls**

1.  Temporary security measures (e.g., enhanced monitoring, stricter access controls) used when immediate patching isn’t possible.

## **Exceptions and Exemptions**

1.  Some vulnerabilities cannot be patched immediately due to operational constraints. Establish processes to handle these with proper documentation and risk assessment.

# Validation of Remediation

Confirm that identified security vulnerabilities have been successfully addressed and mitigated.

### **Rescanning**

- **Purpose**: Verify the effectiveness of remediation efforts after patches or fixes.
- Validation of remediation success
- Identification of new vulnerabilities or issues
- Compliance verification (documented evidence of remediation)

### **Audit**

- **Purpose**: Examine the entire remediation process to ensure it aligns with organizational policies and best practices.
- Documentation review (e.g., change logs, patch records)
- Process adherence (alignment with protocols)
- Compliance check (industry and regulatory requirements)

### **Verification**

- **Purpose**: Ongoing monitoring to ensure vulnerabilities remain mitigated over time.
- Continuous monitoring for new vulnerabilities or system changes
- Periodic assessments to ensure ongoing effectiveness
- Adaptive responses to re-remediate if needed

# Reporting

Provide management with a comprehensive vulnerability report to support informed decision-making.

## **Vulnerability Overview**

- Summary of the vulnerability landscape (total vulnerabilities, severity distribution, trends over time).

## **CVSS Scores**

- Severity levels of identified vulnerabilities.
- Highlight highest-priority vulnerabilities requiring immediate action.

## **Remediation Progress**

- Update on remediation efforts (vulnerabilities addressed vs. pending).

## **Risk Reduction**

- Metrics showing how vulnerability management has reduced overall cybersecurity risk.

## **Recommendations**

- Guidance on prioritizing and allocating resources for remediation.
- Suggestions for additional resources to address exposed vulnerabilities.