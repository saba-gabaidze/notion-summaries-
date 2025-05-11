# Chapter 13 Authentication and
Access Control

# **Security Filtering**

To ensure that the computer or person on the other end of a connection is who they claim to be, security filtering is essential. Simple identification isn't enough, as attackers can lie and use tools to impersonate others, often leading to identity theft.

Security filtering involves controlling access to a network by identifying specific computers and individuals authorized to enter and ensuring data security. This process has two main components:

1. **Allowing Only Authorized Access**: Ensure only approved computers and users can enter the network.
2. **Securing Data Transfer**: Protect the data being transmitted between networks so that it can't be intercepted or decoded by unauthorized individuals.

Security filtering serves as a fundamental defense against unauthorized access and helps protect network resources and data.

# Access List

It’s common for networks today to be connected to the **Internet**, a public internetwork open to everyone. In contrast, **private networks** (personal or company) should remain secure and isolated. When connecting a private network to the Internet, **firewalls** play a crucial role in preventing unauthorized access. Firewalls can be standalone devices or integrated with other hardware, like routers or servers, and rely on **Access Control Lists (ACLs)** as their primary security feature.

**Access Control Lists (ACLs)** reside on routers and control access based on the requesting device's **IP address**. ACLs have existed for decades and serve purposes beyond firewalls. For instance, in a setup with **Network A and Network B**, an ACL can allow Network A users to access Network B, while restricting Network B from accessing Network A. However, vulnerabilities like **IP spoofing** (where a user pretends to be from a trusted network) remain possible.

ACLs can be configured to various levels of complexity, such as separate **inbound and outbound ACLs** to ensure data leaving and entering a network originates from appropriate sources. Common security configurations for ACLs include:

- **Deny any addresses from internal networks**
- **Deny local host addresses** (127.0.0.0/8)
- **Deny reserved private addresses**
- **Deny IP multicast address range** (224.0.0.0/4)

These addresses should never be allowed into the network.

ACLs generally filter traffic based on the **IP address** of the source or destination device, known as **port ACLs** since they’re applied on router ports. For networks running protocols other than TCP/IP, ACLs can filter based on **MAC addresses** (hardware addresses), although **IP-based filtering is typically easier**. Using both IP- and MAC-based ACLs simultaneously can lead to configuration issues where access may be inadvertently blocked.

# **Tunneling**

The Internet constantly handles massive amounts of sensitive data, most of it unencrypted, highlighting the importance of **security protocols**. Security protocols are sets of rules that define how a secure connection is maintained when sending sensitive data over unsecure networks like the Internet or wireless connections.

**Tunneling** involves encapsulating one protocol within another to secure a transmission. For instance, **IP (Internet Protocol)**, a payload protocol, can be encapsulated within **IPSec (Internet Protocol Security)**, which encrypts the packets. The process of tunneling creates a secure point-to-point tunnel through the Internet, often with the tunneled protocol at a higher OSI layer than the payload protocol.

The main tunneling protocols you should know:

- **Virtual Private Network (VPN)**: Creates secure, encrypted connections over the Internet.
- **Secure Sockets Layer (SSL)**: Provides encrypted connections for web browsing.
- **Secure Sockets Layer Virtual Private Network (SSL VPN)**: SSL used specifically to create secure VPN connections.
- **Layer 2 Tunneling Protocol (L2TP)**: Works with IPSec to provide secure VPNs.
- **Point to Point Tunneling Protocol (PPTP)**: An older protocol for VPNs with limited security.
- **Internet Protocol Security (IPSec)**: Secures IP communications by authenticating and encrypting each IP packet.

These protocols are crucial for securely transmitting sensitive data across unsecure networks.

## **VPN**

 lets a host traverse an insecure network, like the Internet, to connect securely to a remote network, making it appear local. An example is a **corporate secure LAN or VLAN** accessed remotely.

There are three main types of VPNs based on their roles:

- **Remote Access VPNs**: Enables remote users (like telecommuters) to securely access the corporate network from anywhere. A common issue is users failing to connect due to incorrect VPN address or password.
- **Site-to-Site VPNs**: Also called **intranet VPNs**, these connect a company’s remote sites to the corporate backbone securely over the Internet, providing a cost-effective alternative to WAN connections like frame relay.
- **Extranet VPNs**: Connects an organization’s suppliers, partners, and customers to the corporate network in a limited way, supporting business-to-business (B2B) interactions.

### **SSL and SSL VPN**

- **SSL (Secure Sockets Layer)**: Originally developed by Netscape to secure connections between web browsers and servers using RSA public-key encryption. SSL enables secure, service-independent Session-layer connections and is widely used for HTTPS (HTTP Secure). Over time, SSL evolved into TLS (Transport Layer Security), enhancing security and forming a new protocol suite.
- **SSL Connection Process**: A client requests a secure connection, and the server responds by establishing the SSL session with necessary security capabilities.
- **SSL VPN (Virtual Private Network)**: Uses SSL to create a secure VPN tunnel. A VPN provides a secure, encrypted connection over potentially insecure networks like the internet. This setup allows data to move safely between systems as if on a private network, shielding sensitive data from unauthorized access. For instance, finance teams can use a dedicated VPN within a network, keeping communications private but allowing optional connections with others in the organization as needed.

### L2TP

---

Next, we have the **Layer 2 Tunneling Protocol (L2TP)**, created by the **Internet Engineering Task Force (IETF)**. It supports **non-TCP/IP protocols** in **VPNs over the Internet** and combines Microsoft’s **Point-to-Point Tunneling Protocol (PPTP)** and Cisco’s **Layer 2 Forwarding (L2F)** technologies. A useful feature of **L2TP** is its position at the **Data Link layer (Layer 2)** of the **OSI model**, enabling support for various protocols beyond TCP/IP, including **Internetwork Packet Exchange (IPX)** and **AppleTalk**. This makes **L2TP** ideal for connecting two **non-TCP/IP networks** via the **Internet**.

### **IPSec**

IP Security (IPSec) is an IETF standard for providing **authentication** and **encryption** at the **Network layer (Layer 3)** of the OSI model. It protects all applications on higher layers and is widely used in **VPNs** because of its support for both **IPv4** and **IPv6**.

- **Protocols**:
    - **Authentication Header (AH)** provides authentication only, without encryption. It’s not compatible with networks using **Network Address Translation (NAT)**.
    - **Encapsulating Security Payload (ESP)** provides both **authentication** and **encryption** and is more commonly used for creating secure VPN tunnels.
- **Modes**:
    - **Transport Mode**: Creates a secure connection between two hosts without tunneling, providing authentication and/or encryption. The data flow remains visible.
    - **Tunnel Mode**: Encapsulates the entire packet, hiding details like transport protocol from potential attackers. Often used in VPNs with ESP for added security.

# **Encryption**

When sensitive data must be sent over the Internet, **encryption** is crucial to protect it from competitors, identity thieves, or anyone trying to intercept it. Without encryption, our data is vulnerable during transmission.

Encryption encodes data using a **key** shared between the sending and receiving devices. At the destination, the receiving device uses this key to decrypt the data back into its original form.

In 1979, the NSA classified encryption as munitions due to concerns about its use by hostile groups, which led to regulated export standards. **Encryption strength** is often measured by its **bit length**. Until 1998, only 40-bit encryption could be exported; now, 64-bit encryption is allowed for export, though some countries (such as Western Europe, Canada, Australia, and Japan) can receive stronger encryption.

For **secure financial transactions**, U.S. banks use stronger encryption methods to ensure safe communication with international branches.

**Password encryption** is now standard in most network operating systems for secure login. However, older protocols like **FTP** and **Telnet** lack password encryption, which can be supplemented by tools like **Pretty Good Privacy (PGP)** for email security. Encryption is also essential in **VPNs, e-commerce, and online banking**.

An **encryption key** is a specific formula or table that matches characters in the data to the key. Keys are either **public** or **private**, each with unique uses for secure data exchange.

## **Private key**

- are often called **symmetrical keys**.
- In **private-key encryption**, both the sender and receiver share the **same key** for **encrypting and decrypting** messages.
- **Challenge**: Securely **transmitting the private key** initially to start communication can be difficult.
- **Solution**: **Public keys** help solve this issue (details on those are coming up).

### **(DES)**

**Data Encryption Standard** is an early symmetric-key encryption algorithm that encrypts data using a 56-bit key.

Key Points:

- **Symmetric-Key**: Uses the same key for both encryption and decryption.
- **Block Cipher**: Encrypts data in fixed-size blocks (64 bits).
- **56-Bit Key**: Considered short by modern standards, making DES relatively insecure today.

**Note**: DES is largely obsolete now and has been replaced by stronger algorithms, like AES (Advanced Encryption Standard), due to vulnerabilities in its short key length.

### **Triple Data Encryption Standard (3DES)**

3DES, developed in the late 1970s and recommended in 1999, combines three DES encryption cycles for enhanced security. It supports one, two, or three keys, with three-key 3DES offering the highest security level. Three-key TDES has a total key length of 168 bits (56 x 3), but due to a meet-in-the-middle attack, it effectively provides only **112 bits of security**. The two-key version has **112-bit keys**, but effectively **80 bits of security**.

**Limitations of 3DES**

3DES is slow, which has led to its gradual phase-out in favor of faster methods like AES. The **National Institute of Standards and Technology (NIST)** estimates that 3DES will remain viable only until around 2030.

## **Public Key Encryption**

Public key encryption uses the **Diffie-Hellman algorithm**, which involves a **public key** and a **private key** to encrypt and decrypt data. Here's how it works:

- The **sending machine's public key** encrypts a message to the **receiving machine**, which then decrypts it using its **private key**.
- This process allows for **one-way communication**. However, if the receiver wants to send a return message, they use the same method.
- If the original sender doesn’t have a public key, the message can still be sent with a **digital certificate** (also known as a **digital ID**) that verifies the sender.

**Key Points**:

- **Diffie-Hellman** refers to all public-key algorithms.
- Invented by **Whitfield Diffie** and **Martin Hellman** from the Stanford Research Institute.
- Introduced the **dual-key concept** in their **1976 paper**, "New Directions in Cryptography."

### **RSA**

**RSA (Rivest-Shamir-Adleman)** is an asymmetric cryptographic algorithm used for secure data transmission.

**key points**

1. **Definition**: RSA is a method of encrypting and decrypting messages using two keys—a **public key** (shared with everyone) and a **private key** (kept secret).
2. **Purpose**: It ensures the confidentiality, integrity, and authenticity of data, commonly used for secure communications over the internet, like in SSL/TLS for web security.
3. **Function**:
    - **Encryption**: A sender uses the recipient's public key to encrypt a message, turning it into ciphertext.
    - **Decryption**: The recipient uses their private key to decrypt the ciphertext back into readable plaintext.

summery

RSA enables secure communication by allowing users to encrypt messages with a public key while ensuring that only the intended recipient can decrypt them with their private key.

### PBG

In the early 1990s, **Phil Zimmerman** developed **Pretty Good Privacy (PGP)**, a free public-key encryption system aimed at securing email transmission. He likened unencrypted emails to **postcards** that anyone can read, while encrypted messages are like letters in an **envelope**.

**Encryption Process**:

1. The document is encrypted using a **session key**.
2. The session key is then encrypted with the recipient's **public key**.
3. This results in an encrypted message that includes the **ciphertext** and the **encrypted session key**.

**Decryption Process**:

1. The recipient uses their **private key** to decrypt the encrypted session key.
2. The session key is then used to decrypt the **ciphertext** back into the original document.

Zimmerman initially distributed PGP for **personal use only**. Both **RSA Data Security** and the **U.S. federal government** took issue with his software; RSA cited patent infringement, while the government prosecuted him for exporting **munitions-grade software**. Ultimately, the government dropped the charges, and a licensing fee is now paid to RSA, allowing PGP and similar public-key products to be widely available.

# **Remote Access**

Remote access allows employees to connect to their company's internal network and access resources from outside the office. It's especially useful for remote workers or those who travel frequently. However, if not secured properly, it poses a significant risk, making it vulnerable to hacking.

**Requirements**

To use remote access, you need:

- A server set up to accept incoming connections.
- Remote-access software installed on the client device.

## **RAS**

**Remote Access Services (**is a combination of hardware and software that enables remote access connections, popularized by Microsoft with its Windows NT tools.

**Functionality**: Users dial in via a modem, get authenticated by the server, and enter their username and password, gaining access to internal network data as if logged in locally.

**Security**: RAS itself is not secure but can incorporate secure tunneling protocols like **PPTP** and authentication methods such as **Microsoft Challenge Handshake Authentication Protocol (MS-CHAP)** and **Extensible Authentication Protocol (EAP)**.

**Versatility**: RAS supports various network protocols beyond **TCP/IP**.

**Illustration**: RAS typically connects a remote user to a server, with routers isolating different networks.

## **(RDP)**

**Remote Desktop Protocol**  allows users to connect to a computer running Microsoft’s Terminal Services. For this connection, the remote computer must have the appropriate client software installed, which is available on most Windows-based operating systems and other major OS like Linux, Solaris, and Mac OS X.

**Microsoft’s RDP client software** is called either **Remote Desktop Connection (RDC)** or **Terminal Services Client (TSC)**.

Once the connection is established, users see a terminal window resembling a desktop interface of the operating system. This allows clients to access applications and files as if they were directly logged into the network.

**Current Version**: The latest version of RDP is **RDP 6.1**, released in February **2008**.

When logged in via RDP, clients can access local files and printers from the remote desktop.

**Security Features**: RDP provides **128-bit encryption** using the **RC4 encryption algorithm** and supports **TLS 1.0** for secure connections.

## **(PPP)**

is a **Layer 2 protocol** used for **authentication**, **encryption**, and **compression**.

**Key Points:**

- Commonly used by **ISPs** to authenticate clients connecting via **modems** or **DSL/cable modems**.
- Supports **remote-access services**, such as **Remote Access Servers (RAS)**, for authentication.

This protocol is essential for secure remote logins and maintaining connections over point-to-point links.

## **PPPoE**

Point to Point Protocol over Ethernet (PPPoE) encapsulates PPP frames within Ethernet frames, designed for high-speed Internet connections. It emerged to address the demand for authentication and encryption in services like ADSL and cable modems.

**Key Components**:

- **Purpose**: Encapsulate PPP frames in Ethernet frames for high-speed Internet access.
- **Authentication**: Utilizes a RADIUS server to manage connections.

**Working Stages**:

1. **Discovery Phase**:
    - MAC addresses of both endpoints are exchanged.
    - A session ID is created for secure communication.
2. **Session Stage**:
    - Once MAC addresses are known, a point-to-point connection is established, and data transmission begins.

## VNC

Virtual Network Computing (VNC) is a graphical desktop-sharing system. It uses the
remote frame buffer (RFB) protocol to allow you to remotely control a computer that’s at
another location. When you do this, whatever you’re doing on your keyboard and mouse is
transmitted over the network to a specific computer, and the graphics are transmitted back
to you accordingly. One of the best features of VNC is that it’s platform independent—as
long as the client has a VNC viewer installed, it can connect to a VNC server regardless
of the type of operating system running on the other machine. Also, more than one VNC
client can connect to a VNC server at the same time—cool!
These are exactly the capabilities that make VNC such a great tool for troubleshooting
computers remotely. In fact, it’s the most common thing that VNC is used for today. Here’s
an example: Let’s say you work at the help desk, and a user calls you saying they’ve got a
problem with their workstation in some other part of the building. Using VNC, you can
connect to that workstation remotely, take control of the machine, troubleshoot the issue,
and fix it. This is all good, but there’s one drawback associated with VNC: the RFB protocol it uses just isn’t secure. But this problem can be resolved by tunneling VNC through a
secure protocol like SSH or even a VPN connection.

## **(ICA)**

**Independent Computing Architecture** is a protocol created by **Citrix Systems** for communication between servers and clients.

**Main Application**: The primary application using ICA is **Citrix’s WinFrame**, which allows administrators to set up Windows applications on a Windows-based server.

**Client Compatibility**: WinFrame enables clients running **Linux, UNIX, or Mac OS** to access Windows-based applications, providing network administrators with flexibility in client operating systems.

**Downside**: A significant drawback is that these connections can be **slow** due to the extensive **translation** required for effective communication between the client and server.

# Managing User Account
and Password Security

managing user accounts and password security is crucial for network safety. different authentication schemes exist, but knowledge of these means little if users aren't trained to manage their usernames and passwords properly. if hackers obtain usernames and passwords, they can easily access your network. if an attacker gains the administrator account credentials, they can cause significant harm, bypassing any authentication protocols.

usernames and passwords serve as the first line of defense for network security. it's essential for users to understand the importance of strong passwords and to keep them secure from theft. even if a system administrator assigns usernames and passwords, users often change them, highlighting the need for proper password management training.

key points to cover include:

- **importance of user training**: educate users on creating and managing strong passwords.
- **difference between good and bad passwords**: emphasize characteristics of secure passwords, such as length and complexity.
- **safeguarding passwords**: advise on methods to protect passwords from theft, including avoiding shared or reused passwords.
- **consequences of weak passwords**: explain the risks associated with compromised accounts, especially administrator accounts.
- **resource-sharing models**: understand how different models impact user account and password management.

focusing on these aspects will help enhance your network's overall security.

## **Share-level security**

allows you to assign passwords to individual files or network resources (like printers) instead of managing rights for each user. You give these passwords to users who need access.

**Limitations:**

- Resources are visible to anyone on the network.
- Anyone with the password can modify the resource.
- Network support staff cannot identify who is accessing or changing resources.

**Best Use Case:**

- Only practical for **smaller networks** where tracking is easier.

**Management Challenges:**

- Difficult to manage with more than **ten computers**.
- Inadequate tracking of resource access makes it a weak solution overall.

**Conclusion:**

- Though **easy to set up**, share-level security is rarely used today due to its management difficulties and lack of accountability.

## **User-level security**

- involves assigning access rights to specific **users** for network resources such as **files, directories,** and **printers**.
- Access is granted through **individually assigned usernames** and **passwords**.
- Only users with valid credentials that have the **appropriate rights** can view or access network resources.
- This method provides **greater control** over who can access specific resources.
- **Sharing usernames and passwords** can compromise security.
- User-level security is a **popular method** for securing files and is used by **most operating systems** today.

## managing user accounts

involves controlling access to network resources through user accounts and assigned rights. sys admins typically perform daily tasks such as:

- **renaming accounts**
- **setting the number of simultaneous connections**
- **specifying login locations and times**
- **adjusting password expiration frequency**
- **delimiting account expiration dates**

these tasks ensure secure and organized management of user access within the network.

## Disabling Accounts

When a user leaves the organization, you have three options for their account:

- **Leave the account in place:** This is not secure, as anyone can log in if they know the password.
- **Delete the account:** This can lead to problems, as deleting an account removes the associated UID (in UNIX) or SID (in Windows), which is linked to passwords and network resource rights. If a new account is created with the same name, it will have a different identification number, losing all previous settings.
- **Disable the account:** This is the best option. The account remains in the system but cannot be used to log in. This is useful for situations such as maternity/paternity leave, medical leaves, or sabbaticals.

For **temporary accounts**, set the account to expire on the employee's expected last day of work. Disabling accounts provides flexibility for future decisions, like renaming the account for a new hire.

## **Anonymous accounts**

- allow limited access for many users logging in with the same username, like "Anonymous" or "Guest." These accounts are often used for FTP access where users log in with the username "Anonymous" and their email as the password.
- **Third-party software** can be used to verify **IP addresses** and **Internet domain names** to determine user locations.
- Using anonymous accounts for **regular network access** is risky because it's hard to track users.
- **Windows Server products** from Windows NT onward have the **Guest account disabled** by default, which is generally a good practice. If you enable it, especially for a public kiosk, ensure **strict group policies** are in place to manage access.
- Some web servers create an **Internet user account** for anonymous access, which has a blank password. This account allows users to access web servers without a login request.
- Do not **rename the Internet user account** or set a password; doing so would prevent public access to your website. For securing documents, use a **separate secure HTTP** or **Windows Server**.

## **Limiting user connections**

- **is important** to prevent account sharing, ensuring that users can only be logged in once since they can only be in one place at a time.
- **One simultaneous connection per user** is standard to avoid unauthorized access through shared accounts.
- **Some users may need multiple connections** for specific applications or tasks, and these can be allowed on a case-by-case basis.
- **Location restrictions for logins** can enhance security, as users typically log in from their own workstations. However, enforcing this can complicate administration, especially if users move around or log in at different stations.
- **Windows Server can limit login locations**, but this feature is not enabled by default.
- **Average users are restricted from logging in at the Server console** to prevent accidental damage to the server.

## **Rename the default maintenance account**

- : Network operating systems assign default names to maintenance accounts (e.g., **Administrator** on Windows and **Root** on UNIX).
- **Security risk**: Keeping the default name makes it easier for attackers, as they only need to guess the password.
- **Choose a unique name**: Rename the account to something memorable but difficult to guess.
- **Avoid common names**: Do not use names like:
    - **Admin**
    - **Administrator**
    - **Analyst**
    - **Audit**
    - **Comptroller**
    - **Controller**
    - **Manager**
    - **Root**
    - **Super**
    - **Superuser**
    - **Supervisor**
    - **Wizard**
    - **Any variation on the above**
- **Do not write down the name**: Avoid sticking the account name on a post-it note attached to the server.

## **Managing Passwords**

Passwords must be managed to ensure network security by following specific guidelines to prevent unauthorized access. Here are the key points:

- **Strong Passwords:** Use a combination of alphanumeric and special characters.
- **Memorability:** Passwords should be easy for you to remember but hard for others to guess.
- **Avoid Writing Down:** Do not write passwords on paper or store them on your computer.
- **User Behavior:** Users often choose simple passwords, making them easy to guess.

## **Minimum Length**

Strong passwords should have the following characteristics:

- **Length:** At least **eight characters**; ideally no more than **15 characters** for memorability.
- **Importance of Length:** Short passwords are easily cracked due to limited combinations.

**Weak Password List:** Avoid these common passwords:

- **“password”**
- Proper names (self or others)
- Pet names
- Birth dates or anniversary dates
- Any dictionary word
- License plate numbers
- Usernames
- Company names
- Occupation
- Favorite colors
- Variations with numbers or spelled backward

These are frequently used and easily guessed passwords.

## **Using Characters to Make a Strong Password**

To create solid passwords, focus on the following:

- **Character Combination:** Use a mix of **numbers**, **letters**, and **special characters** (e.g., $, %, ^, #, @).
- **Example:** A strong password like **tqbf4#jotld** can be created using memorable phrases. For instance, take the first letters of the phrase “The quick brown fox jumped over the lazy dog” and add symbols/numbers.

**Tips for Creating Strong Passwords:**

- Use memorable phrases, quotes, or song lyrics, incorporating numbers and symbols.
- Avoid singing or quoting during logins.

**Testing Password Strength:**

- Use auditing tools (like crack programs) to check if passwords are secure.
- Ensure passwords aren't just regular words with special characters at the start or end, as crack programs can easily bypass these.

## **Password Management Features**

Network operating systems offer built-in features to enhance security:

- **Automatic Account Lockouts:** This feature locks accounts after a certain number of failed login attempts, preventing unauthorized access.
- **Password Expiration:** Passwords must be changed after a specified period, reducing the risk of long-term exposure.

These features help ensure that passwords remain secure and are not easily hacked by crack programs.

## **Automatic Account Lockouts**

To enhance security against unauthorized access, network operating systems implement the following:

- **Lockout After Failed Attempts:** Accounts are locked after several unsuccessful login attempts, preventing hackers from using automated scripts to guess passwords.
- **Administrator Intervention:** Accounts may require manual unlocking by network staff, especially in high-security environments, to monitor potential security breaches.

**Important Considerations:**

- **Avoid Locking Yourself Out:** Only administrators can reset passwords; if you lock yourself out, another administrator must unlock your account.
- **Renaming Default Administrator Account:** The default Administrator account is exempt from lockout policies, posing a security risk. It’s advisable to rename this account and create a new one for daily administrative tasks.

## **Password Expiration and Password Histories**

Passwords should expire to maintain security, as they become more vulnerable over time. Here are the key points:

- **Expiration Policy:** Set passwords to expire every **30–45 days**. Users must reset passwords either immediately or within a preset grace period (limited login attempts or a few days).
- **Customize Expiration Period:** Change the default expiration period to align with your security policy.

**Password Histories:**

- **Prevent Reuse:** Modern operating systems prevent users from resetting passwords to previous ones by maintaining a password history. This history records the last several passwords used, prohibiting their reuse.
- **Example Policy:** If passwords must be reset every two weeks, ensure the password history can store at least **20 passwords**.

**User Behavior:**

- Experienced users may attempt to bypass password history by cycling through passwords until they can revert to a favorite one.
- The latest systems enforce unique passwords and can store more than **20 passwords**, making it harder to revert to previous ones. However, users can still find ways to circumvent these rules, so don't rely solely on this feature.

# User-Authentication Methods

## **(PKI)**

**Public Key Infrastructure** 

PKI is a system that connects users to public keys, verifying identities through a Certificate Authority (CA), akin to an online notary public. Here are the key points:

- **Certificate Authority (CA):** Validates user identities and issues unique identifiers, certifying trustworthiness.
- **User Communication:** PKI allows users to communicate confidently without prior knowledge of each other, ensuring confidentiality and message integrity. It also verifies digital signatures of public key owners.

**Encryption Types:**

- **Asymmetric Cryptography (PKI):** Uses different keys for encryption and decryption. For example:
    - A sender encrypts a message using the recipient's **public key**.
    - The recipient decrypts it with their **private key**.
- **Symmetric Cryptography:** Uses the same key for both processes, making it less secure.

**Digital Signatures:**

- If a digital signature is required, the sender signs the document with their **private key**. Anyone with the sender's **public key** can verify the signature.

**Usage in Transactions:**

- PKI is commonly used for secure online transactions. If a website's certificate or key has expired, proceed with caution; it may indicate potential security risks.

## **Kerberos**

- **Origin:** Created at MIT, Kerberos is a comprehensive security system, not just a protocol.
- **Function:** Establishes user identity upon initial logon to a system, using strong encryption for all communications.
- **Access:** Source code is freely available online.

**How It Works:**

- **Ticketing System:** Users receive tickets upon logging in, allowing access to services within the network (like tickets for rides at an amusement park).
- **Expiration and Refresh:** Tickets expire quickly but are automatically refreshed as long as the user remains logged in.
- **Clock Synchronization:** All systems in a Kerberos domain must have synchronized clocks for proper ticket management.

**Considerations:**

- **Single Point of Failure:** If the Kerberos authentication server goes down, no one can log in. Hence, redundant servers are essential.
- **Centralized Database Risk:** All users' secret keys are stored in one database; if compromised, it poses a significant security threat.

## (AAA)

- Authentication, Authorization, and Accounting  **Definition:**
    - AAA stands for **Authentication**, **Authorization**, and **Accounting**. It serves as a framework for managing network security and is akin to the functions of an auto club (hence "triple A").
    - It provides a systematic approach to control access and monitor user activity within a network.
- **Components:**
    1. **Authentication:**
        - The process of verifying the identity of a user, device, or service.
        - It ensures that the entity requesting access is who they claim to be.
    2. **Authorization:**
        - Determines what an authenticated user is allowed to do within the system.
        - It defines permissions and access levels for different users or devices.
    3. **Accounting:**
        - Tracks user activities and resource usage after authentication and authorization.
        - It provides logs and reports for auditing and compliance purposes.
- **Auditing:**
    - While AAA traditionally refers to authentication, authorization, and accounting, it also encompasses auditing functions to monitor and analyze user activities.

### **RADIUS Overview**

- **Name**: Remote Authentication Dial-In User Service (not just a dial-up server).
- **Function**: Evolved into an authentication and accounting service for user verification over various links.
- **Usage**: Commonly used by ISPs to store usernames and passwords centrally, handling authentication requests.
- **Client-Server Model**: Maintains user profiles in a central database for authentication and encryption services.
- **Firewall Integration**:
    - Users provide credentials (username and password) for access to specific TCP/IP ports.
    - The firewall contacts the RADIUS server to verify these credentials.
- **Authentication Scope**: Supports domain-level authentication for both wired and wireless networks.

### **TACACS+ Overview**

- **Name**: Terminal Access Controller Access-Control System Plus (TACACS+).
- **Purpose**: An alternative AAA method to RADIUS; not fully compatible with the original TACACS protocol.

**Key Differences from RADIUS**:

- **Authentication and Authorization**: RADIUS combines them into one profile; TACACS+ separates them.
- **Protocol Type**: TACACS+ uses TCP (connection-based), while RADIUS uses UDP.

**Stability and Security**:

- TACACS+ is generally considered more stable and secure due to the above differences.

**User Authentication Process**:

1. **Login Request**
2. **Authentication Reply** (success)
3. **Authorization Request**
4. **Authorization Reply** (success)
5. **Accounting Start**
6. **Accounting Reply** (success)
7. **Logout Request**
8. **Accounting Stop**
9. **Accounting Reply** (success)

**Accounting in TACACS+**:

- Refers to logging session details, not financial transactions.
- Logged information includes:
    - Connection start and stop times.
    - Bytes sent and received.
    - Packets sent and received.
    - Reason for disconnection.
- Financial accounting may apply if service providers charge based on connection time or data usage.

## **(NAC)**

**Network Access Control**

- **Definition**: NAC secures network hosts before granting access to the network.
- **Common Usage**: Frequently applied in wireless networking due to the dynamic nature of adding and removing nodes.
- **Standard**: IEEE 802.1x is a widely used form of NAC.

**IEEE 802.1x**:

- **Purpose**: Developed to address security vulnerabilities in wireless networking.
- **Functionality**:
    - Supports multiple authentication schemes in an open framework.
    - A client (referred to as a supplicant) requests permission to join the wireless network from the access point (authenticator).
    - The supplicant provides credentials to the access point.
    - The access point forwards these credentials to a centralized authentication server.
    - If authentication is successful, the server sends an accept message back to the access point.
    - Only then does the access point allow the user to connect to the network.

## **CHAP**

- **Definition**: CHAP is a secure authentication protocol that prevents usernames and passwords from being transmitted over the network.
- **Mechanism**:
    - Both client and server share a common text phrase known as a **shared secret**.
    - When the client requests authentication, the server responds with:
        - A random value (nonce).
        - An ID value.
    - The client combines the nonce, ID, and shared secret, then generates a one-way hash using the **Message-Digest Algorithm 5 (MD5)**.
    - This hash value is sent back to the server.

**Authentication Process**:

1. Server sends nonce and ID to client.
2. Client generates a hash with the nonce, ID, and shared secret.
3. Client sends the hash to the server.
4. Server computes the hash using the same values and shared secret.
5. Server compares the received hash with its calculated hash.
6. If they match, the client is authenticated.

## **MS-CHAP**

- **Definition**: MS-CHAP is a variation of the Challenge Handshake Authentication Protocol (CHAP) developed by Microsoft.

**Key Differences from CHAP**:

- **Shared Secret Storage**:
    - **CHAP**: Requires the shared secret to be stored in clear text.
    - **MS-CHAP**: Encrypts the shared secret locally.
- **Authentication Capability**:
    - **CHAP**: Client authentication is only performed by the server.
    - **MS-CHAP Version 2**: Supports mutual authentication, allowing the client to verify the server's legitimacy.
- **Encryption Method**:
    - **CHAP**: Uses MD5 for hashing.
    - **MS-CHAP**: Uses **Data Encryption Standard (DES)** for generating the one-way hash.

**Platform Compatibility**:

- MS-CHAP is a Windows proprietary protocol and does not work on Linux or other platforms.