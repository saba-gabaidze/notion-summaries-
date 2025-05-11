# 2.2 Explain common threat vectors and attack surfaces

# Message-based+

## **Email**

Phishing emails appear legitimate but contain malicious links or attachments. They aim to steal data, inject malware, or cause financial harm.

## **SMS (Smishing)**

SMS is increasingly targeted for phishing. Attackers use text messages to trick users into revealing personal information or downloading malicious content.

## **Instant Messaging (IM)**

IM platforms, often encrypted, still face security risks. Attacks involve malware-laden attachments or socially engineered links to deceive users.

# **Image-Based+**

Images can hide harmful code or links, leading to cyber attacks like unauthorized access or ransomware. Attackers exploit image-based vulnerabilities to embed malicious content. Protecting against these attacks requires advanced image analysis tools to detect concealed threats and prevent system compromises.

# **File-Based+**

Malicious files exploit software vulnerabilities to launch attacks when opened. They can execute harmful code, allowing hackers to steal data or gain remote control. Defending against these attacks involves file screening and blocking attachments to prevent threats from breaching the network.

# **Voice Call+**

Voice calls can be manipulated for cyber attacks like **caller ID spoofing**

and **vishing**. Attackers disguise their identity to deceive users into revealing personal information or committing financial fraud. They may also leave malicious voicemails to further exploit trust.

# **Removable Device+**

Removable devices like USB drives can spread malware when plugged into a network or system. An attacker might drop an infected USB to trick someone into activating malicious code. Once executed, the malware grants unauthorized access. To protect against this, found USBs should be handed to security to be opened in a sandbox.

# **Vulnerable Software**

Vulnerable software has weaknesses that can be exploited by attackers to gain unauthorized access, compromise data, or disrupt systems. These vulnerabilities often arise from coding errors, outdated components, or design flaws. To mitigate risks, regular security updates, patch management, and best coding practices are essential.

**!vulnerable Software Scanning!!**

## **Client-based scanning**

 Requires an agent on each host to automate vulnerability detection and reporting.

## **Agentless scanning**

 Scans without installing software, preferred by attackers for reconnaissance (e.g., Nmap, Wireshark).

# Unsupported Systems and Applications

Unsupported systems and applications, including legacy and third-party software, present significant vulnerabilities. Outdated software components are prime targets for cyber threats.

**Risks**:

- Hackers exploit known vulnerabilities in unsupported software.
- Unpatched gaps can lead to unauthorized access, data exfiltration, or large-scale attacks like ransomware.

**Protection strategies**:

- Regularly update and patch all software.
- Replace or upgrade unsupported systems and applications to minimize security risks.

# Unsecure Networks

## **Wireless Networks**

- Open system authentication lacks encryption, exposing data like login credentials and financial details to interception.
- **Protection strategies**:
    - Use encryption protocols.
    - Disable SSID broadcasting to hide the network.
    - Enable MAC filtering to restrict access to approved devices.

## **Wired Networks**

- Unsecured wired networks risk physical access to ports, leading to data breaches or malware.
- **Protection strategies**:
    - Use encryption and access controls.
    - Regularly assess security measures.
    - Disconnect unused ports to reduce risks.

## **Bluetooth Networks**

- Bluetooth's easy pairing can allow unauthorized access if unchecked.
- **Protection strategies**:
    - Enable Bluetooth only when needed.
    - Update devices regularly with security patches.

# Open Service Ports

Unsecured open service ports are vulnerabilities that allow attackers to access systems and applications. These ports act as entry points for malicious activities.

**Protection strategies**:

- Regularly scan for open ports.
- Close unnecessary ports to reduce the attack surface.

# Default Credentials

Default credentials, set by manufacturers for easy setup, are a major security risk. Attackers exploit default usernames and passwords to gain unauthorized access.

**Protection strategies**:

- Change default credentials immediately after installation.
- Use strong, unique passwords for all systems and applications.

# Supply Chain

A supply chain involves the transformation of raw materials into finished products, connecting suppliers, manufacturers, distributors, and retailers. Each party plays a crucial role in the product journey.

## **Managed Service Providers (MSPs)**

- MSPs handle all IT needs for a company, but a breach in their infrastructure can impact multiple clients.
- **Protection strategies**:
    - Demand strict security standards, regular audits, and prompt patching from MSPs.

## **Vendors**

- Vendors often access sensitive information, making them potential vectors for cyber threats.
- **Protection strategies**:
    - Conduct comprehensive risk assessments and evaluate security protocols before granting access.
    - Maintain regular communication to align security expectations.

## **Suppliers**

- Suppliers provide goods or services but can introduce risks if their security is weak.
- **Protection strategies**:
    - Scrutinize suppliers’ security practices and ensure due diligence.
    - Set clear security expectations in contracts and raise security awareness throughout the supply chain.

# **Human Vectors/Social Engineering**

Cybercriminals exploit human psychology to breach security systems, often manipulating individuals into revealing sensitive data or access.

## **Phishing**

Deceptive emails or websites that trick victims into sharing personal info, often using urgency or authority.

- *Spear Phishing*: A more targeted version, aimed at specific individuals or groups (e.g., executives).

## **Smishing**

 Phishing via SMS messages, tricking recipients into clicking malicious links or downloading malware.

## **Misinformation/Disinformation**

- *Misinformation*: False info spread unintentionally.
- *Disinformation*: Deliberately false info to mislead or manipulate.

## **Impersonation**

 Attackers pose as trusted individuals or entities (e.g., police or support teams) to gain trust and extract sensitive data.

## **Brand Impersonation**

Attackers create fake websites or emails resembling reputable brands (e.g., banks) to steal information or money.

## **Business Email Compromise**

 Hackers take control of legitimate business emails to commit fraud, like invoice scams, to redirect funds.

## **Pretexting**

The attacker creates a fake scenario (e.g., tech support) to convince the victim to share confidential info.

## **Watering Hole Attacks**

 Malicious code placed on trusted websites. When users visit, they unknowingly download malware.

## **Typosquatting**

 Cybercriminals register domains similar to legitimate ones with minor errors, hoping users mistype URLs and fall for phishing or malware.

**Key Strategies to Defend**

- Awareness training (e.g., phishing simulations).
- Verify sources before sharing sensitive info.
- Use security tools to detect malicious links, websites, and typosquatting.