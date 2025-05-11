# Chapter 14 Network Threats and Mitigation

# Recognizing Security Threats

- **Security threats are real** and can quickly affect unprotected systems.
- **Example incident:** A friend's computer was exposed to 15 virus alerts within 10 minutes of connecting to a high-speed network without a firewall, despite having antivirus software.
- **Main attack purposes:** Threats are designed for **destruction** (damaging data or denying access) or **reconnaissance** (stealing information).
- **Types of attacks:** Often combinations of simpler attack forms, aimed at breaching network security.

## DoS

- **Denial of Service (DoS) attacks** block users from accessing a network or resources.
- **Common targets:** Large companies’ intranets and websites (e.g., Microsoft, Amazon).
- **Reputation in hacking:** DoS attacks are **easy to deploy** and looked down upon by experienced hackers; even young, inexperienced users can launch them.
- **Variety in DoS attacks:** Several types exist, each affecting networks differently.

This covers the nature, perception, and impact of DoS attacks, emphasizing their simplicity and the wide range of DoS methods hackers can use.

### Ping of Death

**Key points for notes:**

- **Ping of Death attack:** A large ICMP packet floods a target’s buffer, causing **system reboot** or **hang**.
- **Ping’s usual function:** Sends small ICMP packets to check if a remote computer is responsive.
- **Defense:** Most operating systems have **patches** to prevent Ping of Death attacks.

### Smurf

**Key points for notes:**

- **Smurf attack:** A DoS attack using **spoofed broadcast ping messages** to flood a victim’s network.
- **How it works:** Attacker **spoofs victim’s IP**, sends multiple pings to broadcast addresses, causing all hosts on the network to respond, which **overloads the victim’s network**.
- **Prevention:** Modern routers are usually **configured to block broadcast packets**, and routers/hosts can be set not to respond to broadcast pings.

### SYN flood

**Key points for notes:**

- **SYN flood attack:** A DoS attack that overwhelms a server with **fake SYN packets**, causing it to use up resources.
- **Normal SYN use:** SYN packets start a TCP connection, with the server responding to each SYN as a **new request** for communication.
- **Attack method:** The attacker sends excessive SYN requests, **forcing the server to try responding** until it runs out of resources and **blocks further connections** (even legitimate ones).
- **Defense:** Most network operating systems now have **patches** to help prevent SYN flood attacks.

### TFN, TFN2K

**Key points for notes:**

- **Tribe Flood Network (TFN) and TFN2K:** These are **DDoS (Distributed Denial of Service) attacks** that coordinate **synchronized attacks** from multiple sources, targeting multiple devices.
- **IP spoofing in TFN attacks:** The attacker uses **fake IP addresses** to hide their identity and make it harder to block the attack.
- **Stacheldraht attack:** A complex DDoS method that combines **TFN techniques** with **encryption** and involves root-level access, ending with a DoS attack.

## Viruses

- **Viruses:** Malicious programs that cause various harmful effects, from annoying to devastating, such as displaying messages, deleting files, or flooding networks with data.
- **Propagation:** Viruses require user action (e.g., opening infected attachments) to spread to other systems; they cannot replicate themselves automatically.
- **Types of viruses:**
    - **File viruses:** Infect executable files.
    - **Macro viruses:** Target data files, particularly in applications like Microsoft Office.
    - **Boot-sector viruses:** Infect the boot sector of storage devices.
- **Hacker motivation:** Writing unique viruses is seen as a programming challenge, gaining respect in the hacking community and media attention.
- **Common misconception:** **Macs are not immune** to viruses; they can also be targeted, though it may require more skill to create viruses for them compared to Windows.
- **Virus prevalence:** Windows is a primary target for virus creation due to its widespread use, offering attackers greater potential impact.

### File viruses

- **File viruses:** Target executable files (e.g., **.COM, .EXE, .DLL**) by replacing some or all of the program's code.
- **Activation:** They activate and cause damage only when the infected file is **executed**.
- **Propagation:** Once loaded into memory, the virus seeks to infect other executable files, spreading its effects throughout the system or network.
- **Examples:**
    - **Jerusalem virus**
    - **Nimda virus:** An Internet worm that infects common Windows files and files with extensions like **.HTML, .HTM, and .ASP**.

### macro

- **Macro:** A script of commands that automates tasks in applications, allowing users to perform actions without manual input.
- **Macro viruses:** Use the **Visual Basic macro-scripting language** to execute harmful actions in data files, primarily in programs like Microsoft Office.
- **Commonality:** While many macros are harmless and useful, macro viruses can be **annoying** and affect the functionality of applications (e.g., inability to save files or open new documents).
- **Examples of macro viruses:**
    - **Cap**
    - **Cap A**

### Boot-Sector Viruses

- **Boot-sector viruses:** Infect the **master boot record** of a hard disk, which is critical for starting the operating system.
- **How they work:** Overwrite the boot sector, making it seem like there’s no pointer to the operating system.
- **Symptoms:** Users may see error messages like **"Missing Operating System"** or **"Hard Disk Not Found"** when powering up the computer.
- **Examples of boot-sector viruses:**
    - **Monkey B**
    - **Michelangelo**
    - **Stoned**
    - **Stealth Boot**

### **Multipartite viruses**

- Infect both the **boot sector** and **files** on a computer, making them particularly dangerous and hard to remove.
- **Examples:**
    - **Anthrax:** Mostly a hoax rather than a real virus.
    - **Tequila:** Activates four months after infection, making it a genuine threat.
- **Impact:** May require **reformatting** the computer to remove them.
- **Prevention:** Use a reliable virus scanner and tools like **Windows Defender** (available in Vista and Server 2008) to prevent infections.
- **Trojan Horses:** Many multipartite viruses spread through Trojan Horse techniques, hiding within legitimate programs. They activate when the host program runs.
    - **Examples of Trojans:**
        - **DMSETUP.EXE**
        - **LOVE-LETTER-FOR-YOU.TXT.VBS**
- **Tip:** Displaying file extensions can help identify misleading filenames that indicate viruses

## Worms

- **Worms:** Similar to viruses but more dangerous because they can **replicate independently**.
- **Self-activation:** Worms do not require user action (like opening a file) to **activate** and spread.
- **Propagation:** They can **actively spread** across networks and infect other systems on their own.
- **Destructive capability:** Worms can also **destroy data** or disrupt system performance without any user intervention.

# Hackers and their tools

- **Hackers:** You can't identify a hacker by appearance; they could be anyone, including seemingly harmless individuals.
- **Understanding threats:** It's better to understand the methods and strategies hackers use to penetrate defenses rather than being suspicious of everyone.
- **Types of attacks:**
    - **Directed attacks:** Specific attacks on targeted systems by hackers (e.g., using tools like **WinNuke** to send packets to a specific machine).
    - **Viruses:** Generally not directed; they spread **indiscriminately** from user to user.
- **Your role:** Network administrators need to track and prevent attacks to protect systems from intrusions or crashes.

## **IP Spoofing**

- **Definition:** Sending packets with a **fake source address** to make them appear as if they come from within the target network.
- **Implication:** A packet-filtering router may accept these packets as valid, allowing them into the network.
- **Prevention:** Use a **firewall** to block spoofed packets from entering your network.
- **Need for Firewalls:**
    - **Historical context:** The Internet once relied on an "honor system," but this is no longer effective.
    - **Current threats:**
        - Increased corporate intranet connections to the Internet.
        - E-commerce sites handling sensitive personal and financial data.
        - Rise in corporate espionage and identity theft.
    - **Best practice:** Implementing firewalls is a critical step in practicing "Safe Net" and protecting against malicious activities.

## **Backdoors**

 are hidden entry points into a computer or network that allow unauthorized access. Here are some key points to remember:

- **Definition**: Backdoors enable attackers to bypass normal authentication and gain access to systems or networks.
- **Methods of Entry**: Attackers may use simple invasions or complex methods like **Trojan Horses** to establish these backdoors.
- **Persistent Access**: Once a backdoor is installed, it allows attackers to return to the compromised system at will, making it a significant security risk.
- **Detection and Prevention**: It's crucial to monitor networks for unusual activity and use security tools to detect and remove backdoors to protect sensitive information.

## **Network Reconnaissance**

 is a critical phase in the hacking process where attackers gather information about a target network. Here are the essential points:

- **Purpose**: Hackers aim to understand the network's structure, systems, and vulnerabilities to effectively plan their attacks.
- **Methods Used**:
    - **Port Scans**: Identifying open ports and services running on those ports to find potential entry points.
    - **DNS Queries**: Gathering information about domain names and IP addresses associated with the network.
    - **Ping Sweeps**: Sending ICMP echo requests to multiple IP addresses to determine which hosts are active.
    - **Social Engineering/Phishing**: Manipulating individuals into revealing confidential information or granting access.
- **Importance of Awareness**: Recognizing these tactics helps in implementing better security measures to detect and prevent reconnaissance activities.

## **Packet Sniffers**

are tools that can capture and analyze network traffic. Here are the key points:

- **Functionality**:
    - Operate by setting a network adapter to **promiscuous mode**, allowing it to capture all packets on the network, not just those addressed to it.
    - The captured packets are then sent to a specialized application for analysis.
- **Uses**:
    - **Network Troubleshooting**: Help diagnose network issues by providing insights into traffic patterns and performance problems.
    - **Security Analysis**: Assist network administrators in monitoring and securing network traffic.
- **Risks**:
    - **Data Theft**: Can capture sensitive information such as usernames, passwords, and personal data, making them valuable for identity thieves.
    - **Malicious Use**: If used by attackers, they can facilitate unauthorized access to systems and data.
- **Preventive Measures**: To mitigate the risks associated with packet sniffers:
    - Use **encryption** (like HTTPS, VPNs) to protect data in transit.
    - Implement **network segmentation** and access controls to limit exposure.
    - Regularly monitor network traffic for suspicious activities.

## Password Attacks

- **Purpose**: Aim to discover user passwords to gain unauthorized access to accounts and resources.
- **Methods**: Can be executed using:
    - **IP Spoofing**: Disguising the source IP to bypass security.
    - **Packet Sniffing**: Capturing packets to obtain passwords during transmission.
    - **Trojan Horses**: Using malicious software to record keystrokes or steal credentials.

## Brute-Force Attacks

- **Definition**: A specific type of password attack that systematically tries all possible combinations of passwords until the correct one is found.
- **Execution**:
    - Utilizes software to automate the login attempts to a shared resource (e.g., a server).
    - This method can be time-consuming, depending on the complexity of the password.
- **Targeting Accounts**:
    - Attackers prefer accounts with higher privileges, as these provide greater access to sensitive information and systems.
    - Once an account is compromised, attackers can establish **backdoors** for future access, bypassing the need for passwords.

### Mitigation Strategies

- **Strong Password Policies**: Encourage the use of complex, unique passwords.
- **Account Lockout Mechanisms**: Lock accounts after a certain number of failed login attempts to prevent brute-force attacks.
- **Multi-Factor Authentication (MFA)**: Adds an additional layer of security by requiring a second form of verification.
- **Regular Monitoring**: Keep an eye on login attempts and anomalies in account access to detect potential breaches early.

## **Packet/Protocol Abuse**

Packet/protocol abuse occurs when protocols are exploited in unintended ways, creating security threats. A notable example involves the Network Time Protocol (NTP), which ensures accurate time synchronization across the Internet.

**NTP and Abuse**

NTP servers use peers to verify their time accuracy. When someone queries an NTP server using the `ntpdc` command, they can employ a malicious command called `monlist` to gather information about traffic with peers. Attackers can send spoofed requests to multiple NTP servers, overwhelming the target system with responses, resulting in a Denial of Service (DoS) attack.

**Malformed Packets**

Hackers can also inject malformed packets into network traffic to exploit systems. Tools like Scapy allow users to craft packets that may break or exploit vulnerabilities in servers, such as sending incorrect information in DHCP request packets, potentially leading to unauthorized access or server shutdowns.

## **Zero-Day Attacks**

Zero-day attacks exploit vulnerabilities in software or systems that are unknown to the vendor or have not yet been patched.

**Attack Surface and Attack Window**

- **Attack Surface**: This refers to the various ways a vulnerability can be exploited.
- **Attack Window**: This is the period during which a vulnerability can be exploited before a patch is applied to mitigate the risk.

## **Poisoning in Action**

Here’s how an ARP cache poisoning attack typically unfolds:

**Network Setup**

- **Components**: A small network consists of a gateway, switch, DHCP server, and two clients.
- **Normal ARP Cache**: Each device’s ARP cache should accurately map IP addresses to MAC addresses, ensuring proper communication.

**ARP Cache Poisoning Process**

1. **Intrusion**: An attacker gains access to the network, possibly by plugging into an unused Ethernet port.
2. **Sending False ARP Frames**: The attacker uses specialized tools to send deceptive ARP packets, convincing each device that the attacker's MAC address corresponds to legitimate IP addresses in the network.
3. **Resulting Poisoned ARP Caches**: All systems now have incorrect mappings stored in their ARP caches, which is referred to as ARP cache poisoning.

**Consequences**

- **Man-in-the-Middle Attack**: With the ARP caches poisoned, the attacker can intercept, read, and manipulate all traffic flowing through the network. This allows for sensitive data capture or further attacks.

### **Dynamic ARP Inspection and DHCP Snooping**

To combat ARP poisoning and unauthorized DHCP traffic, organizations can implement **Dynamic ARP Inspection (DAI)** and **DHCP Snooping** on their networks.

**Dynamic ARP Inspection (DAI)**

- **Functionality**: DAI monitors ARP packets on the network and maintains a database of trusted IP and MAC address pairs.
- **Action Against Attacks**: If an attacker attempts to send malicious ARP messages, the DAI-enabled switch detects the unknown ARP commands and blocks them, preventing the attack from succeeding.

**DHCP Snooping**

- **Purpose**: Similar to DAI, DHCP Snooping also uses a trusted database but focuses on DHCP traffic.
- **Detection of Unauthorized Devices**: It keeps track of known DHCP servers and clients. If an unknown MAC address sends DHCP server messages, the DHCP snoop–capable switch will block that device and issue an alert