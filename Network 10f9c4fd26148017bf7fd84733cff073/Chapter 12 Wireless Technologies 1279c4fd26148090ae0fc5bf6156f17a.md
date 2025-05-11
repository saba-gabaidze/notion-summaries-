# Chapter 12 Wireless Technologies

# **Wireless Networking Hardware**

Wireless networking hardware functions similarly to wired hardware. Wireless Ethernet NICs encapsulate data from the upper OSI layers into frames, transmitting them as radio waves instead of through cables. It's important to note that **802.11 frames** are not encapsulated in the same way as **802.3 Ethernet frames**.

Many modern devices, especially portable ones, have built-in wireless capabilities. Desktop computers can add wireless functionality through **expansion cards** or **USB wireless network adapters**, which are versatile and can be repositioned for better signal strength.

**Creating a Wireless Network**

For simple setups, such as connecting a few laptops together, the wireless adapters may suffice. However, to extend a wireless network or connect it to a wired network, you need additional equipment like a **wireless access point (WAP)**.

A basic WAP connects wireless nodes to wired networks and operates at **OSI Layer 1**. Many manufacturers combine WAPs with switches and routers into a single device, functioning at multiple OSI layers.

**Terminology Note:** Manufacturers often refer to WAPs simply as **access points (APs)**, and the abbreviations WAP and AP are commonly used.

# Software

Every **wireless network adapter** requires two key pieces of software to work with an operating system:

- **Device driver:** Communicates with the wireless NIC.
- **Configuration utility:** Manages the connection settings for the wireless hardware.

Driver installation for wireless networking devices is usually **automatic**, but it's essential to check the vendor’s instructions before installing the card.

Each operating system includes built-in **wireless clients** for configuration, but these may lack advanced features needed for complex networks. In such cases, utilities provided by the **wireless adapter vendor** or third-party solutions can be used.

A typical wireless network adapter’s client configuration utility allows you to:

- Check **link state** (connection status).
- Assess **signal strength** (connection quality).
- Configure settings like **wireless mode**, **security encryption**, and **power-saving options**.

Wireless Access Points (WAPs) are typically configured through **browser-based setup utilities**.

In the next section, the different **modes** of wireless networks will be discussed.

# Wireless Network Modes

802.11 networks operate in two modes:

1. **Ad Hoc Mode**:
    - Devices communicate directly with each other.
    - No intermediary hardware is involved.
2. **Infrastructure Mode**:
    - Uses a Wireless Access Point (WAP) as a hub for all wireless clients.
    - The WAP connects wireless network segments to wired network segments.

**Ad Hoc Mode**

- Also known as **peer-to-peer mode**.
- Wireless nodes are in **direct contact** with each other in a **decentralized** manner.
- Does not use a **Wireless Access Point (WAP)**; utilizes a **mesh topology**.
- Two or more nodes form an **Independent Basic Service Set (IBSS)**, similar to a **wireless workgroup**.
- Ideal for small groups (less than a dozen) needing to **transfer files** or **share printers**.
- Suitable for **temporary networks**, like study groups or business meetings.
- Not typically used for daily work, as it cannot connect to other networks unless using **Internet Connection Sharing (ICS)**.

**Infrastructure Mode**

- Uses one or more **WAPs** to connect wireless nodes centrally, similar to a **physical star topology**.
- Creates a **wireless local area network (WLAN)**.
- Connects wireless network segments to **wired segments**.
- Recommended for large numbers of devices or when **centralized control** is needed.
- A single WAP serves an area called a **Basic Service Set (BSS)**; multiple WAPs create an **Extended Service Set (ESS)**.
- The terms **Extended Basic Service Set** and **Extended Service Set** (ESS) are often used interchangeably.
- Requires **more planning** (placement of WAPs for coverage) than ad hoc networks.
- Provides a stable environment for **permanent installations**.
- Best suited for **business networks** or networks needing shared resources, like **Internet connections** and **centralized databases**.

# **BSSID, SSID, and ESSID**

Wireless devices need a way to identify their network, whether it's ad hoc or infrastructure, to ensure proper data delivery and avoid confusion with overlapping Wi-Fi networks.

**BSSID**

- **Basic Service Set Identifier** defines a basic infrastructure network comprising one Wireless Access Point (WAP) and multiple wireless clients.
- For a simple network, the BSSID is the same as the **MAC address** of the WAP.
- In an **ad hoc network** (IBSS), the BSSID is a randomly generated 48-bit string resembling a MAC address, included in each frame.

**SSID**

- **Service Set Identifier** is a user-friendly name for the BSS or IBSS, consisting of a **32-bit identification string**.
- It allows devices to connect by sharing the same SSID, simplifying network identification.
- WAPs advertise their SSID through continuous broadcasts, making available networks visible to devices.

**ESS**

- **Extended Service Set Identifier** applies when multiple WAPs are connected to a central switch, forming a single broadcast domain (ESS).
- The same SSID is used across all WAPs, allowing clients to connect to the WAP with the strongest signal.
- Clients can roam seamlessly between WAPs as they move throughout the coverage area.

Most manufacturers use the term **SSID** instead of **ESSID**, simplifying the configuration process for users while technically using the ESSID in an ESS setup.

# **Broadcasting Frequency**

Wireless communication faces issues from interference caused by other devices. To minimize this, different devices must use specific broadcasting frequencies. Understanding these frequency ranges helps troubleshoot interference problems. The original **802.11 standards** operate on two main radio frequency bands: **2.4 GHz** and **5.0 GHz**.

## Methods

The **IEEE 802.11** standard allows devices to communicate using **spread-spectrum radio waves**. This technique broadcasts data in small chunks over various frequencies within a designated range.

The standard defines three **spread-spectrum broadcasting methods**:

1. **Direct-Sequence Spread-Spectrum (DSSS)**:
    - Sends data over multiple frequencies simultaneously.
    - Uses about **22 MHz** of bandwidth.
    - Capable of **greater data throughput** but more susceptible to **interference**.
2. **Frequency-Hopping Spread-Spectrum (FHSS)**:
    - Sends data on one frequency at a time, continuously **shifting frequencies**.
    - Uses about **1 MHz** of bandwidth.
    - Less prone to interference compared to DSSS.
3. **Orthogonal Frequency-Division Multiplexing (OFDM)**:
    - The latest method, effective at handling **interference**.
    - Used in all but the earliest **802.11 networks**.

Overall, DSSS offers higher throughput but is more vulnerable to interference, while FHSS is more stable but has lower bandwidth usage. OFDM provides an improved solution for modern networks.

# Channels

Every Wi-Fi network operates on a **channel**, which is a portion of the available spectrum.

In the **2.4-GHz band**, the **802.11 standard** defines **14 channels** of **20-MHz** each. However, different countries restrict which channels can be used. For instance, in the **United States**, only channels **1 to 11** are allowed.

These channels **overlap**, so it’s recommended that nearby **Wireless Access Points (WAPs)** avoid using adjacent channels (e.g., **6 and 7**). The preferred channels are **1, 6,** and **11**, as they are the only **non-overlapping channels**. Adjusting WAP channels helps minimize interference, especially in areas with many networks.

In the **5.0-GHz band**, there are about **40 channels** available, with varying regulations by country. The **802.11 standards** for this band typically utilize **automatic channel switching**, which simplifies setup since channel management is less of a concern.

# **CSMA/CA                !!!**

: CSMA/CA stands for **Carrier Sense Multiple Access with Collision Avoidance**. It is used in Wi-Fi networks, contrasting with **CSMA/CD** (Carrier Sense Multiple Access with Collision Detection), which is used in wired Ethernet networks.

**Network Media Sharing**: In a physical bus topology, devices share network media by **listening to voltage levels** on the wire. If the voltage is below a certain threshold, a device can send data. If it's above the threshold, the device must wait.

**Collisions**: When two devices send data simultaneously, their frames collide, corrupting each other’s signals. This situation is unavoidable, so networks must handle collisions effectively.

**Collision Handling**: In wired networks using switches in full-duplex mode, collisions are not a concern because devices can send and receive data simultaneously. However, in wireless networks, collisions cannot be detected due to the half-duplex nature of radio transmission and the possibility of "hidden nodes."

**Backoff**: With CSMA/CD, when a collision is detected, each node waits for a **random timeout period** (backoff) before trying to send data again.

**Collision Avoidance in CSMA/CA**: To manage potential collisions, CSMA/CA employs proactive strategies. The **802.11 standard** has two collision avoidance methods:

- **Distributed Coordination Function (DCF)**: Currently the primary method used. It requires devices to wait a backoff period if the network is busy and mandates that receiving nodes send **acknowledgments (ACK)** for every frame processed. If no ACK is received, the sending node retransmits the data frame.
- **Point Coordination Function (PCF)**: Not widely implemented in current networks.

**ACKs and Backoff Duration**: The ACKs also communicate a duration for other nodes to wait before attempting to access the network again, based on the time it takes for the data frame to reach its destination.

**RTS/CTS**: Devices can optionally use **Ready to Send/Clear to Send (RTS/CTS)** to further prevent collisions.

# **802.11b**

![image.png](Chapter%2012%20Wireless%20Technologies%201279c4fd26148090ae0fc5bf6156f17a/image.png)

- **First widely adopted Wi-Fi standard**
- **Data throughput**: Up to **11 Mbps**
- **Range**: Up to **300 feet** under ideal conditions
- **Frequency**: Operates on the **2.4-GHz** band
- **Main downside**: **Crowded frequency** leading to potential interference from other wireless devices

# **802.11a**

![image.png](Chapter%2012%20Wireless%20Technologies%201279c4fd26148090ae0fc5bf6156f17a/image%201.png)

- **Frequency Range:** Operates in the **5.0 GHz** range, which is less crowded than the **2.4 GHz** range.
- **Interference Reduction:** The 5.0 GHz range minimizes interference from devices like **telephones** and **microwave ovens**, leading to reduced latency and improved responsiveness.
- **Market Availability:** Despite being designated as "a," **802.11a** was released after **802.11b**.
- **Throughput:** Offers speeds up to **54 Mbps**, significantly higher than **802.11b**.
- **Range:** Maximum effective range is about **150 feet**.
- **Popularity:** Despite its superior speed, **802.11a** did not achieve the same popularity as **802.11b**.

# **802.11g**

![image.png](Chapter%2012%20Wireless%20Technologies%201279c4fd26148090ae0fc5bf6156f17a/image%202.png)

The **802.11g standard** provides data transfer speeds up to **54 Mbps**, similar to **802.11a**, while offering a wider range of about **300 feet** like **802.11b**. It is **backward-compatible** with **802.11b**, allowing the same **802.11g WAP** to support both **802.11b** and **802.11g** devices.

**Network Modes**

- In **native mode** (with only **802.11g** devices), the network operates at **54 Mbps**.
- In **mixed mode** (when **802.11b** devices connect), the speed drops to **11 Mbps**.

**Channel Bonding**

Manufacturers of **802.11g** devices later introduced **channel bonding**, which allows the use of **two channels** for increased throughput. This feature is **not part of the official 802.11g standard** and requires both the **NIC** and **WAP** to be from the **same manufacturer** to function properly.

# **802.11n**

![image.png](Chapter%2012%20Wireless%20Technologies%201279c4fd26148090ae0fc5bf6156f17a/image%203.png)

The **802.11n standard** enhances Wi-Fi networking with **faster speeds** and **multiple antenna technology** called **MIMO (Multiple In/Multiple Out)**. This allows devices to make **multiple simultaneous connections** or **streams**.

**Speed and Throughput**

With up to **four antennas**, 802.11n devices can achieve speeds up to **600 Mbps**, although practical speeds are usually lower. **Channel bonding** is also utilized to further increase throughput.

**Transmit Beamforming**

Many 802.11n Wireless Access Points (WAPs) use **transmit beamforming** to improve signal coverage, reducing **dead spots** by optimizing the signal for specific clients.

**Compatibility with Older Standards**

Like 802.11g, 802.11n WAPs can support older **802.11b/g** devices. However, supporting these older devices can lead to **overhead**, as 802.11n frames must be encapsulated into 802.11b or 802.11g frames. If any **802.11b** devices join the network, overall traffic drops to **802.11b speeds**, but this does not happen with 802.11g devices.

**Connection Modes**

802.11 WAPs operate in three modes:

- **Legacy Mode**: Sends separate packets for legacy devices. This is inefficient for 802.11n usage.
- **Mixed Mode**: Also known as **high-throughput mode**, supports older standards while leveraging wider bandwidth for better speeds.
- **Greenfield Mode**: Exclusively for **802.11n-only** networks. It processes only 802.11n frames, resulting in the best **goodput**.

**Exam Tip**: If an **802.11g** device shows a connection type of **802.11g-ht**, it indicates it is connecting to an 802.11n WAP running in **mixed mode**.

# **802.11ac**

![image.png](Chapter%2012%20Wireless%20Technologies%201279c4fd26148090ae0fc5bf6156f17a/image%204.png)

 is an enhancement of the **802.11n** standard, featuring:

- **More streams:** Allows for increased data transmission.
- **Wider bandwidth:** Enables higher speeds for wireless connections.
- **5.0-GHz band only:** Avoids device density issues present in the 2.4-GHz band.

**Key Feature:**

- **Multiuser MIMO (MU-MIMO):** This new version of MIMO allows a wireless access point (WAP) to communicate with multiple users at the same time.

**Broadcasting Method:**

- **Quadruple Amplitude Modulated (QAM):** 802.11n and 802.11ac utilize a special version of OFDM for broadcasting.

# **WPS**

By 2006, **802.11** was widely used, especially in non-PC devices like **printers**, **scanners**, and **speakers**. These devices lacked interfaces for easy wireless configuration.

**Wi-Fi Protected Setup (WPS)**

To simplify setup, the wireless industry developed **WPS**, which operates in two main modes:

- **Push Button Method**:
    
    Press a button on one device and then on the other. The devices automatically connect with encryption.
    
- **PIN Method**:
    
    Used for connecting a PC to a WPS device. Press the button on the WAP, find the SSID, and enter an **eight-digit PIN** as the WPA personal shared key. This PIN is printed on the device.
    

**Security Concerns**

While WPS is user-friendly, it is vulnerable to attacks targeting the **PIN**. Since the WPS PIN is short, hackers can easily attempt to **crack** it, potentially gaining control of the WAP and access to the entire network.

**Caution**

Be cautious when using WPS due to its security vulnerabilities.

# Wi-Fi security

Wi-Fi security issues arise because wireless networking devices often come with no built-in security, making setup easy but insecure. **Out-of-the-box wireless networks are open**, requiring no authentication or authorization. When adding security, you must decide how to share access.

**Wireless network security focuses on hardening the network** against attacks. Key methods include:

- **MAC address filtering**: Limits access by allowing only certain devices.
- **Authentication**: Controls who can connect to the network.
- **Data encryption**: Protects the data being transmitted over the air.

These methods help secure access and data. All require configuration on the wireless access points (WAPs) and devices.

## Mac filtering

MAC address filtering allows control over who can access a wireless network based on the physical addresses of wireless NICs. This method creates an access control list (ACL) that restricts access to the network. Here's a simplified summary of the important parts:

- **MAC address filtering**: Limits access to a network by using a whitelist of accepted MAC addresses.
- **Whitelist**: List of MAC addresses allowed to connect to the network.
- **Blacklist**: List of MAC addresses specifically denied from connecting to the network.
- **Access Control List (ACL)**: The WAP uses ACLs to enable or deny MAC addresses.
- **Whitelist vs. Blacklist**: Whitelisting allows only specific devices, and blacklisting denies specific devices. Whitelisting is more labor-intensive.
- **Spoofing**: Hackers can spoof MAC addresses, pretending to use legitimate addresses, making filtering less secure.
- **Security consideration**: For highly sensitive data, consider using a wired network or separating sensitive data from the wireless network.

## **Wireless Authentication**

Authentication secures a network so only users with proper credentials can access resources. Wireless networks follow a similar process to wired networks but add extra steps for user authentication.

**802.11i Standard:**
The first major 802.11 security standard, **802.11i**, covers both authentication and encryption. For now, focus on authentication.

**802.1X Standard:**
802.11i uses the **IEEE 802.1X standard** to set up secure authentication, using a **RADIUS server** and passwords encrypted with **Extensible Authentication Protocol (EAP)**.

**RADIUS Server:**
A **RADIUS server** stores usernames and passwords, determining user rights when accessing the network. The wireless computer (called the **supplicant**) communicates with the **Network Access Server (NAS)** (usually the WAP). The NAS collects the supplicant’s credentials and contacts the RADIUS server to verify the details.

**Authentication Process:**

- The **supplicant** requests access from the NAS.
- The NAS forwards the supplicant's credentials to the RADIUS server.
- If correct, the RADIUS server sends an **Access-Accept** code and an **Authenticator** section to confirm the packet came from the RADIUS server.
- The remote user gains access if authentication is successful.

**Securing Connections:**
Each device connection must be secure. Protocols like **PPP** secure the connection between the supplicant and NAS, while **IPsec** can secure the link between the NAS and the RADIUS server. **EAP** encrypts the authentication process for added security.

This summary covers the key points needed for your notes without using large resolutions or headers.

## **EAP**

EAP (Extensible Authentication Protocol) addresses the challenge of authentication by providing a single standard for different authentication methods, particularly in wireless networks. While it is a general-purpose authentication wrapper, its primary use is in wireless environments.

**Common EAP Types**

1. **EAP-PSK**:
    - Popular in wireless networks.
    - Uses a shared secret code stored on both the access point and client, encrypted with AES.
    - CompTIA refers to it as preshared key without a hyphen.
2. **EAP-TLS**:
    - Utilizes Transport Layer Security for mutual authentication.
    - Requires certificates on both server and clients (or smart cards instead of certificates).
    - Considered very secure but poses administrative challenges.
3. **EAP-TTLS**:
    - Similar to EAP-TLS but only requires a server-side certificate.
    - Commonly used in secure wireless networks.
4. **EAP-MS-CHAPv2 (Protected EAP/PEAP)**:
    - Uses MSCHAPv2 with an encrypted TLS tunnel.
    - The most common EAP implementation.
5. **EAP-MD5**:
    - Simple authentication using MD5 hashes.
    - Considered weak and is the least used version.
6. **LEAP**:
    - Proprietary to Cisco, using MS-CHAP authentication between client and RADIUS server.
7. **EAP-FAST**:
    - Cisco’s replacement for LEAP.
    - Supported by current operating systems with appropriate software.

**Conclusion**

EAP enables a range of authentication methods to function within a unified framework, primarily for wireless networks. The choice of EAP type depends on the required security level and administrative feasibilit

## 802.1X

 is an **authentication standard** developed to enhance security in Ethernet networks by enabling **port-based network access control**. It addresses the limitations of traditional EAP, which was designed for point-to-point connections using PPP, by embedding EAP information within **Ethernet frames**.

Key points about 802.1X:

- It requires devices to undergo a **full AAA (Authentication, Authorization, Accounting)** process before accessing the network, preventing unauthorized access.
- Before 802.1X, devices on a wired network could access other systems’ ports, allowing potential attackers to send packets even without proper credentials.
- 802.1X stops unauthorized devices from accessing the network until they are **authenticated and authorized**.
- The structure of 802.1X resembles a **RADIUS AAA setup**, integrating RADIUS-style AAA with various EAP methods.
- While 802.1X was developed to replace other authentication methods, it has mainly been adopted in **wireless networking** due to resistance to change from existing systems.

Overall, 802.1X significantly improves network security by controlling access at the port level and requiring proper authentication before any network communication occurs.

## **Data Encryption**

The main method for securing a wireless network is by encrypting data packets. Encryption scrambles data and locks it with an encryption key before transmission. Only devices with the decryption key can read the data, making it secure against eavesdroppers. Enabling **WPA2** provides strong security for data in transit.

Encryption can be **symmetric** (same key for both parties) or **asymmetric** (public and private keys). Various encryption methods exist for wireless networks, including **WEP**, **WPA**, and **WPA2**. **WPA3** has been introduced to enhance security, especially on open networks.

**Data Encryption Using WEP**

**Wired Equivalent Privacy (WEP)** uses a 64- or 128-bit encryption algorithm but is not secure. WEP can be cracked in under a minute using simple tools. Its main weaknesses are:

- The encryption key size is effectively only 40-bit or 104-bit due to the 24-bit **initialization vector (IV)**.
- WEP uses a static and shared key, making it vulnerable to cracking after capturing enough packets.

WEP also lacks user authentication, relying only on **MAC addresses** for identification, which can be easily spoofed. **WEP is outdated and should not be used**; modern devices no longer support it.

**Data Encryption Using WPA**

The **802.11i** standard was developed to address WEP's shortcomings, leading to **Wi-Fi Protected Access (WPA)**. WPA enhances security by:

- Using **dynamic encryption key generation** (keys are unique per user and session).
- Implementing **Temporal Key Integrity Protocol (TKIP)**, which adds an extra layer of security to the WEP scheme.

However, WPA still uses **RC4**, and vulnerabilities were discovered, allowing attackers to breach WPA security.

**Data Encryption Using WPA2**

**WPA2** builds on the **802.11i** standard by replacing TKIP with the more robust **CCMP-AES** encryption, which is a 128-bit block cipher. WPA2 is currently the top security standard for 802.11 networks and is much harder to crack compared to previous methods.

The common setup is **WPA/WPA2 Pre-shared Key (PSK)**, where a secret key is required for any device connecting to the network. While WPA-PSK and WPA2-PSK offer some level of security, they can be vulnerable to attacks if weak passphrases are used. To prevent attacks, use **long passphrases** (16+ characters).

For enhanced security, **WPA2-Enterprise** can be used with **RADIUS server authentication**, providing a robust wireless network setup.

# **Enterprise Wireless**

Setting up a simple BSSID or ESSID is easy with inexpensive WAPs, which can be connected to a switch and configured via a web interface. Many associate “wireless networks” with these cheap SOHO devices, as they've been available since the early days of 802.11.

**Limitations of SOHO Devices**

As wireless networks grow more crucial and complex, SOHO devices become insufficient. For reliable, secure, and manageable wireless networks, **enterprise-class wireless equipment** is necessary.

**Differences Between Enterprise and SOHO Devices**

An enterprise wireless device typically differs from a SOHO device in five key areas:

- **Robust Device Construction:** Built to withstand demanding environments and high usage.
- **Centralized Management:** Allows for easier configuration and monitoring of multiple devices from one location.
- **VLAN Pooling:** Supports multiple virtual networks to segregate traffic for better security and performance.
- **Power over Ethernet (PoE):** Simplifies installation by allowing devices to receive power through the Ethernet cable.
- **Personal Device Integration:** Facilitates the safe inclusion of personal wireless devices in the enterprise network.

## **Robust Device Construction**

- **Material Quality**: Enterprise WAPs are typically made from better materials, such as **metal** instead of plastic, making them more durable.
- **Configurability**: Enterprise WAPs are generally **more configurable** than typical SOHO WAPs.
- **Upgrade Capability**: Many enterprise WAPs allow for the **swapping of antennas and radios**, enabling upgrades to the latest technologies without replacing the entire unit.

## Enterprise Wireless Administration

- An **enterprise wireless infrastructure** typically involves many **Wireless Access Points (WAPs)**, making individual management impractical.
- Changing settings, such as the **WPA2 password** across numerous WAPs, would be extremely time-consuming if done individually.
- To simplify administration, the **wireless industry** developed **wireless controllers**. These devices manage multiple WAPs simultaneously, reducing the need to access each one individually.
- All WAPs on a single **SSID** should connect to a **single switch or group of switches**.
- WAPs can be categorized into two types:
    - **Thick clients**: These can be individually configured through their own interface.
    - **Thin clients**: These can only be configured through a wireless controller.
- Historically, the centralized configuration methods for WAPs were **proprietary**, leading to a lack of interoperability between brands.
- The introduction of **Lightweight Access Point Protocol (LWAPP)** has improved interoperability, allowing most WAPs to accept commands from various wireless controllers.

## **VLAN Pooling**

One challenge in large enterprise networks is the high number of clients on a single SSID, leading to excessive broadcasts. To manage this, networks can be divided into multiple broadcast domains using routers. However, if a single domain is needed, VLAN pooling can be used, where a pool of VLANs is created for a single SSID, and wireless clients are randomly assigned to one of the VLANs.

# Implementing Wi-Fi

Site Survey: Conduct a survey to identify obstacles (existing wireless signals, interference) and determine optimal access point locations.

Install Access Points: Set up one or more access points based on the site survey findings.

Configure Access Points: Configure the settings on the access point(s) and ensure they are set up for the wireless clients.

Test the Network: Verify the network functionality to ensure it operates as intended.

## **Performing a Site Survey**

The first step in installing a wireless network is the **site survey**. This survey identifies obstacles that could affect the wireless network and helps determine the best locations for **access points**.

Key components for conducting a site survey include:

- **Floor Plan**: A detailed layout of the area where you want wireless coverage.
- **Site Survey Tool**: For example, **NETSCOUT’s AirMagnet Survey Pro**.

**Wireless survey tools** assist in:

- Discovering other wireless networks in the vicinity.
- Integrating the floor plan with marked interference sources.

This information ensures you select the appropriate hardware and achieve optimal **network coverage**.

## **Wireless Network Discovery**

Discovering wireless network signals in your area helps you set both the SSID and channel to avoid overlaps.

**Wireless Analyzer**

A wireless analyzer is a device that detects and documents existing wireless networks. It's essential for diagnosing issues and conducting site surveys. You can use dedicated handheld tools or run software like AirMagnet Survey Pro on a laptop or mobile device.

**Wireless Signal Frequencies**

Wireless networks operate on the **2.4-** or **5.0-GHz** spectrum using discrete channels. Early setups required determining nearby channels to avoid interference, but modern networks typically adjust channels automatically using algorithms built into Wireless Access Points (WAPs).

**High Device Density**

The main challenge today is managing high device density in environments with many Wi-Fi networks. A robust wireless solution is necessary to handle multiple users on limited frequencies.

**Survey Tools**

Tools like AirMagnet Survey Pro are commonly used for wireless surveys. They generate various reports, with the **heat map** being one of the most powerful. A heat map visually represents RF sources on-site, using colors to indicate signal intensity.

## **Interference Sources**

In networks beyond a simple setup, it's essential to conduct a site survey to identify potential interference sources. Common culprits include **refrigerators**, **reinforced walls**, **metal plumbing**, and **microwave ovens**, which can create **dead spots** where radio waves struggle to penetrate.

For areas with high interference, consider upgrading to **802.11n** or **802.11ac** equipment with **three or four antennas** for better coverage. Alternatively, a **multiple WAP (Wireless Access Point)** network may be necessary to eliminate dead zones. A proper site survey is crucial for planning an effective network.

## installing client

- **Wi-Fi Client Installation**: Every Wi-Fi network requires clients, which can include smartphones, laptops, tablets, etc., that usually have built-in clients.
- **Desktops**: Most desktop computers do not have built-in wireless capabilities, necessitating the installation of a **wireless NIC** (Network Interface Card).
- **NIC Installation Options**: You can choose between a **PCIe card** or a **USB device**.
- **Installing a PCIe NIC**:
    - Power down the PC and disconnect it from the AC source.
    - Open the computer case and locate a free slot on the motherboard.
    - Remove the slot cover and take the NIC out of its antistatic bag.
    - Install the NIC and affix the retaining screw.
    - Attach the antenna if required.
    - Close the case, reconnect the power, and start the computer.
    - Install drivers and software from the manufacturer’s disc if prompted.
- **Installing a USB NIC**:
    - Install the drivers and software before connecting the USB NIC to the computer. This is standard procedure for USB devices.

## **Setting Up an Ad Hoc Network**

Ad hoc networks are less common but can appear on the CompTIA Network+ exam. They may also be necessary in real-world scenarios. Here’s how to configure them:

- **Configuring NICs**: You need to address four key components:
    1. **SSID**: All wireless nodes must use the same SSID.
    2. **IP Addresses**: Ensure no two nodes have the same IP address. Most operating systems use Automatic Private IP Addressing (APIPA) to avoid conflicts.
    3. **Channel**: Choose a channel for communication.
    4. **Sharing**: Make sure the File and Printer Sharing service is enabled on all nodes.
- **Ad Hoc Mode**: Set the network interface cards (NICs) to function in ad hoc mode.

**Practical Experimentation**

- **Try This**: If you and a friend have Wi-Fi-enabled devices, set up an ad hoc network using the configuration utility.
- **Connection**: Use default settings to connect both devices.
- **File Sharing**: Once connected, create a HomeGroup, copy sample images between devices, and transfer larger files to a Public folder.
- **Distance and Channels**: Experiment with distance and channel changes. Test how far apart the devices can be while still communicating, and observe the effects of changing channels (e.g., from channel 6 to channel 4) in the configuration utility.

# **Placing the Access Points/Antennas**

All wireless access points (WAPs) have antennas that radiate the 802.11 signal, and their optimal placement depends on the coverage area and signal bleed beyond the borders. It's essential to use antennas that provide sufficient signal strength and directionality.

**Antenna Types**

There are three common types of antennas in 802.11 networks:

- **Omnidirectional Antennas:** These radiate signals in all directions. For typical networks, place a WAP with an omnidirectional antenna in the center of the area for blanket coverage. The standard dipole antenna, often seen on older WAPs, has two opposing radiating elements and has a doughnut-shaped radiation pattern, which is effective for single-floor coverage but less so for vertical coverage.
- **Unidirectional Antennas:** These focus the radio wave into a beam and are useful when you want to limit the broadcast area. Types include parabolic and Yagi antennas, which can extend coverage over longer distances in narrow beams.
- **Patch Antennas:** Flat, plate-shaped antennas that generate a half-sphere beam, ideal for indoor settings where strong signal coverage is needed without broadcasting to adjacent rooms.

**Optimal Antenna Placement**

Placement varies based on coverage needs and security considerations. Conduct a site survey using wireless analyzer tools to identify dead spots and adjust antenna type and location accordingly.

**Antenna Gain**

The gain of an antenna is measured in decibels (dB), with a typical WAP providing about 2 dB. To enhance signal strength in an omnidirectional setup, consider replacing factory antennas with larger ones to increase coverage.

# **Configuring the Access Point**

- **Accessing the Setup Utility:** Use a web browser on a client workstation to enter the access point’s default IP address (e.g., **192.168.1.1**) and log in using the administrative password from the documentation.
- **Basic Configuration Options:** After logging in, you can change basic setup options, access point passwords, and security settings.
- **Configuring SSID and Beacon:**
    - **SSID:** Change to a unique identifier; clients scan for SSIDs to locate networks.
    - **SSID Broadcast:** Disabling it stops casual users but not determined intruders. Manual configuration of connections is required.
    - **Beacon Traffic:** Regularly sent timing frames from the WAP. Adjusting the beacon interval can improve network speeds but may slow device negotiations. Default is usually every **100 ms**.
- **MAC Address Filtering:** Enhance security by creating a list of allowed/denied MAC addresses. Enter the MAC address of devices in the filtering configuration.
- **Configuring Encryption:**
    - **Enable Encryption:** Protect data frames from unauthorized access by turning on encryption at the WAP and generating a security key.
    - **Match Keys:** Ensure that all connected devices use the same encryption key.
    - **Encryption Levels:** Use **WPA2** for the best security. If unavailable, use **WPA**; avoid **WEP** entirely. You can generate keys automatically or manually.
- **Configuring Channel and Frequency:**
    - **Channel Settings:** Most home networks can stay on defaults. Change channels in case of overlapping signals using a wireless analyzer.
    - **Dual-Band Settings:** With 802.11n WAPs, you can select between **2.4 GHz** or **5.0 GHz**. Use **5.0 GHz** in congested areas for less interference.

**Configuring the Client**

- **SSID Consistency:** Ensure all devices use the same SSID as the access point.
- **Connecting to Non-Broadcasting Networks:** Manually input the SSID and security information if the network does not broadcast its SSID.
- **Profile Storage:** After connecting, the client saves the settings. Future connections to the same SSID will use these stored settings. If the network configuration changes (e.g., encryption password), delete the profile and reconnect.

# **Extending a Wi-Fi Network**

To extend a Wi-Fi network beyond the range of a Basic Service Set (BSS) network, you can use various methods:

- **Add WAPs:** Installing additional Wireless Access Points (WAPs) creates an Extended Service Set (ESS). Ensure both WAPs share the same ESSID and use separate channels if they are close together.
- **Wireless Range Extenders:** These devices pick up and rebroadcast your Wi-Fi signal. They come in different forms, such as standalone units or models that plug into electrical outlets. They require minimal setup and can eliminate dead spots.
- **Wireless Bridges:** Used to connect two wired networks or join wired and wireless networks. They come in two types:
    - **Point-to-Point Bridges:** Communicate with one other bridge, linking two wired segments.
    - **Point-to-Multipoint Bridges:** Can connect to multiple bridges simultaneously, linking several network segments.

**Verifying Installation**

After setting up the Wi-Fi network, it’s crucial to verify the installation. Test the connection by transferring data between computers using the wireless link before concluding the setup.

# Symptom Types in Wireless Networking

1. **No Connection**
    - **Symptoms**: Unable to connect to the wireless network; constant password prompts; APIPA/zeroconf addresses.
    - **Common Issues**:
        - **Channel Problems**: Overlapping channels (especially in the 2.4 GHz band). Use channels 1, 6, and 11 to minimize overlap.
        - **Security Type Mismatch**: Incorrect encryption settings or wrong passphrase.
    - **Solutions**:
        - Ensure the correct password is entered.
        - Use wireless scanning tools to assess channel utilization.
2. **Slow Connection**
    - **Symptoms**: Connected to the SSID but experiencing slow data transfer; web pages load slowly; applications time out.
    - **Common Issues**:
        - **Overworked WAPs**: Too many devices connected to a single WAP can saturate bandwidth.
        - **Physical Problems**: Obstacles affecting signal strength.
        - **RFI (Radio Frequency Interference)**: Excessive interference from other devices.
    - **Solutions**:
        - Increase WAP capacity by adding more WAPs or upgrading to a higher standard (e.g., 802.11ac).
        - Ensure proper placement of WAPs to avoid physical obstacles.
3. **Weird Connection Issues**
    - **Symptoms**: Unpredictable behavior such as dropped connections or fluctuating speeds.
    - **Common Causes**:
        - Physical barriers affecting signal quality.
        - Interference from other wireless devices or electronic equipment.
    - **Solutions**:
        - Conduct a site survey to identify physical barriers.
        - Optimize WAP placement and consider using devices with multiple antennas for better coverage.

### Specific Troubleshooting Steps

- **Signal and Power Levels**:
    - Ensure WAPs are set to the appropriate power levels (if adjustable).
    - Use better antennas or upgrade to newer standards (like 802.11ac) to enhance coverage.
- **Physical Barriers**:
    - Recognize the effects of absorption (non-metallic materials), reflection (metal), and refraction (glass) on wireless signals.
    - Perform a site survey to identify problematic materials that could attenuate signals.
- **Captive Portals**:
    - Many public Wi-Fi networks use captive portals, which require users to accept terms before gaining internet access.

### General Tips for Effective Troubleshooting

- **Site Surveys**: Regularly conduct site surveys to identify potential issues caused by physical barriers or interference.
- **Documentation**: Keep a record of wireless configurations, devices connected, and any changes made to the network for future reference.
- **User Education**: Inform users about common issues and troubleshooting steps they can take before reaching out for help.

# **Untested Updates/Incompatibilities**

- **802.11 Standards**: Manufacturers continuously update client firmware/software and WAP firmware to keep devices compatible with evolving 802.11 standards.
- **Research Updates**: Always research and test updates, especially firmware, before deploying them in a production network to avoid potential issues.
- **Test Networks**: If possible, run updates on a test network first.
- **Backward Compatibility**: Understand the backward compatibility of different 802.11 versions, as incompatibilities may arise with updates.
- **Example of Incompatibility**: An example is a dual-band 802.11n WAP that only supported one band at a time, rendering it incompatible with new dual-band NICs.

## **Rogue Access Point**

- **Definition**: A rogue access point (rogue AP) is an unauthorized AP on a network.
- **Common Issue**: Rogue APs can be installed by users wanting to connect to the network or by malicious actors.
- **Evil Twin**: An evil twin is a type of rogue AP that mimics an existing SSID to trick users into connecting, often found in unsecured networks like those in airports and hotels.

## **War Driving and War Chalking**

- **War Driving**: This is the practice of searching for wireless networks using antennas and sniffing programs, common around 2005.
- **War Chalking**: War chalking involved marking locations of discovered networks on curbs or sidewalks for others to find.
- **Relevance**: While these practices were common in the past, they are less relevant today due to the widespread availability of wireless networks.

# !!!!!!!!!!!!!!!!!!!!!!!!!!

How many non-overlapping channels are available with 802.11a?
A. 3
B. 12
C. 23
D. 40

## IPSec