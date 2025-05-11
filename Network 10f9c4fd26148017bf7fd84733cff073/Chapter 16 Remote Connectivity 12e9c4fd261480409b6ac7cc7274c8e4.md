# Chapter 16 Remote Connectivity

# **T1 and T3**

- **T-carriers:** Digital trunk carriers used by the telephone industry, with T1 being the most basic and common.
- **Meaning of “T”:** Commonly stands for “trunk-level” or “terrestrial,” differentiating ground-based from space-based communications.
- **T1 Connection:**
    - Refers to a digital networking technology.
    - Uses shielded, two-pair cabling (RJ-48C connector).
    - Point-to-point connection with two Channel Service Units/Digital Service Units (CSU/DSU) at each end.
- **CSU/DSU:** Connects customer equipment (like a router) to the T1 line, allowing for data transmission. You can connect two CSU/DSUs directly using a T1 crossover cable.
- **DS1 Signaling:**
    - Uses a simple frame with 25 pieces: one framing bit and 24 channels.
    - Each channel holds an 8-bit DS0 data sample.
    - Total throughput of **1.544 Mbps**, split into 24 **64-Kbps DS0 channels**.
    - Uses **Time Division Multiplexing (TDM)**.
- **Analogy:** Think of T1 like a conveyor belt in a milk factory, where multiple types of milk are processed in parallel, with some channels potentially empty while others are filled.
- **T1 Characteristics:**
    - Dedicated, leased connection with no telephone number.
    - **Fractional T1 Access:** Allows leasing of individual channels instead of the entire bundle.
- **T3 Connection:**
    - Supports a data rate of about **45 Mbps**, consisting of **672 DS0 channels**.
    - Commonly used by regional phone companies and ISPs.
- **E-carrier Level 1 (E1):**
    - European equivalent of T1, carrying signals at **2.048 Mbps** (32 channels at 64 Kbps).
    - Can interconnect with T1 for international use.
    - **E3 lines** carry 16 E1 lines at about **34 Mbps**.
- **CSU/DSU Functions:**
    - Connects T1/T3 lines to customer equipment.
    - Performs line encoding, conditioning, and testing.
    - Protects equipment from electrical interference and stores statistics.

**Important Points:**

- Understand the differences and functionalities of T1, T3, E1, and E3 lines.
- Remember that DS1 is often referred to simply as T1 in practice.

# **Fiber Carriers: SONET/SDH and OC**

- **SONET and SDH Adoption**: In 1987, major fiber-optic carriers adopted a unified international standard:
    - **SONET** (Synchronous Optical Network) for the U.S.
    - **SDH** (Synchronous Digital Hierarchy) for Europe.
    These standards enable simpler interconnections between carriers and made the Internet a universal network.
- **SONET Standards**: SONET defines standards at the **Physical** and **Data Link** layers of the OSI model. It supports a ring-based topology for fault tolerance.
- **Multiplexing Capabilities**: SONET can combine multiple signals (DS1, DS3, E1) into large SONET frames for transmission.
- **Optical Carrier (OC) Standards**: OC standards indicate the optical data capacity of fiber-optic cables:
    - **OC-1**: 51.8 Mbps
    - **OC-3**: 155.52 Mbps
    - **OC-768**: 39.8 Gbps.
- **Wavelength Division Multiplexing (WDM)**:
    - **DWDM** (Dense Wavelength Division Multiplexing) allows multiple signals over a single-mode fiber using different wavelengths, enabling high throughput (e.g., 7.6 Gbps with a single OC-1 line).
- **Coarse Wavelength Division Multiplexing (CWDM)**: A simpler method than DWDM, effective over shorter distances (~60 km), often used in higher-end LANs.
- **Synchronous Transport Signal (STS)**:
    - **Structure**: Consists of **STS Payload** (carries data) and **STS Overhead** (signaling/protocol info).
    - **Speed Designation**: STS is followed by a number indicating speed (e.g., STS-1 at 51.85 Mbps, STS-3 at 155.52 Mbps).

**Common Optical Carriers**:

| **Optical Carrier** | **Speed (bps)** |
| --- | --- |
| OC-1 | 51.8 Mbps |
| OC-3 | 155.52 Mbps |
| OC-12 | 622.08 Mbps |
| OC-24 | 1.244 Gbps |
| OC-48 | 2.488 Gbps |
| OC-192 | 9.953 Gbps |
| OC-768 | 39.8 Gbps |

# **Packet Switching**

- **WAN Connections**: T-carrier and OC connections alone do not provide a complete WAN solution. They form the backbone of long-range connections, carrying packetized voice and TCP/IP data.
- **Need for Packet Switching**: To connect multiple T1s, T3s, or OC connections, an additional level of devices is required, which is where packet switching comes in.
- **First Generation**: The initial packet-switching technology was **X.25**, enabling communication over high-speed digital links without needing individual leased lines.
- **Addressing Packets**: Packets require an addressing scheme to route data between locations. The telephone industry developed its own packet types for T-carrier and OC lines, which function similarly to routable network protocols like TCP/IP.
- **Traditional Packet Switching Methods**: The two main forms of packet switching used in WAN connections are:
    - **Frame Relay**: A now declining technology.
    - **ATM (Asynchronous Transfer Mode)**: A technology that is largely considered obsolete.
- **Packet Switches**: Devices that forward and store packets using any packet-switching protocol are known as **packet switches**.

## Currently outdated

**Frame Relay**

- **Definition**: Frame Relay is a packet-switching standard designed for T-carrier lines, optimized for bursty, on/off traffic typical of LAN applications.
- **OSI Model**: Operates at both **Layer 1 (Physical)** and **Layer 2 (Data Link)** of the OSI model, using frames instead of packets.
- **Functionality**:
    - Switches frames quickly.
    - Does not guarantee data integrity or delivery; frames may be discarded during network congestion.
    - Reliability is maintained due to the low error rates of T-carrier lines; higher-level protocols handle error-checking.
- **Current Status**: Once popular, Frame Relay has been largely replaced by newer technologies like **MPLS (Multiprotocol Label Switching)**.

---

**ATM (Asynchronous Transfer Mode)**

- **Definition**: ATM is a network technology designed for high-speed LANs in the early 1990s but became popular in WANs.
- **Usage**: Used in SONET rings to move voice and data, integrating all types of media (voice, video, data) over one connection.
- **Cells**:
    - Utilizes fixed-length frames called **cells** (53 bytes) for transferring information.
    - Cells from the same source and destination follow the same route.
- **Transfer Requirements**:
    - Data can tolerate delay but not loss, while audio/video tolerate loss but not delay.
    - ATM’s design effectively handles both transfer types.
- **Speeds**: Transfer rates range from **155.52 Mbps to 622.08 Mbps** and higher. Typically, OC lines connected to ATM switches.

## **MPLS**

 Multiprotocol Label Switching (MPLS) is a technology that enhances packet-switching efficiency, designed to overcome limitations in Frame Relay and ATM. It integrates an MPLS label between the Layer 2 header and Layer 3 IP information.

**MPLS Header Components**:

- **Label**: A unique identifier for routing.
- **Experimental Bits (Exp)**: Determines packet priority.
- **Bottom of Label Stack (S)**: Indicates if a packet has multiple labels.
- **Time to Live (TTL)**: Defines how many hops a packet can make before being discarded.

**Purpose of MPLS**:

- To allow ISPs to manage traffic efficiently across different interconnections, improving Quality of Service (QoS) network-wide.

**Key Terms**:

- **Forwarding Equivalence Class (FEC)**: A group of packets sent to the same destination.
- **Label Switching Router (LSR)**: Routers that forward packets based on MPLS labels.
- **Label Edge Router (LER)**: Routers that add or remove MPLS labels from packets.
- **Label Distribution Protocol (LDP)**: Used by LSRs and LERs to share state information dynamically.

**How MPLS Works**:

1. **Initial Configuration**: Administrators set routing metrics.
2. **Packet Labeling**: LERs add MPLS labels to packets entering the MPLS network.
3. **Routing**: LSRs forward packets based on labels until they reach the exit LER, which strips off the label.

**Applications of MPLS**:

- Originally designed for quick data movement, MPLS is also used to create end-user VPNs, allowing ISPs to provide users with virtual connections to their networks without requiring individual setups.

# Connecting to the Internet

1. **Two-Step Process**:
    - **Contact the Telephone Company**: To have a physical copper line installed.
    - **Choose an Internet Service Provider (ISP)**: To provide Internet access. Nowadays, many telephone companies also act as ISPs, simplifying the process.
2. **Cost-Reduction Strategies**:
    - **Check for Existing Services**: If you're in an office building, check with the building supervisor to see if an ISP already provides service there.
    - **Consider Nearby Interconnects**: If a T1 or better line is available nearby, it could lower costs.
    - **Be Prepared for High Costs**: Running an OC line to a residential area can be expensive, often running into thousands of dollars.
3. **Demarcation Point**:
    - The point where the telephone company’s responsibility ends and your responsibility begins. Everything after the demarc is managed by you or your ISP.
4. **Equipment Installation**:
    - After reaching the demarc, a CSU/DSU (Channel Service Unit/Data Service Unit) is installed to connect the T-carrier line to your router. These devices can sometimes be integrated into a single unit with the router.
5. **Reliability of WAN Connections**:
    - Telephony carriers are considered more dependable than cheaper alternatives, like cable modems, making them a preferred choice for businesses.
6. **Testing Connection Integrity**:
    - **Bit Error Rate Test (BERT)**: A critical test to verify the integrity of the T-carrier connection from end to end. It’s essential to understand how to perform this test on your specific CSU/DSU device.

# Last Mile

## Dial-Up

Dial-up is a traditional method of connecting to the Internet using standard telephone lines. It is categorized as one of the last-mile solutions for Internet access. Here's a breakdown of dial-up connections:

Types of Telephone Lines

1. **Dedicated Lines**:
    - Always connected and do not need to dial up to establish a connection.
    - **Example**: T1 lines, which provide a permanent, hard-wired connection between two locations.
    - No phone number is assigned because the connection is constant.
2. **Dial-Up Lines**:
    - Require a phone number and must dial each other to establish a connection.
    - Hang up when communication is complete, freeing the line for other uses.

Technologies Used in Dial-Up Connections

1. **PSTN (Public Switched Telephone Network)**:
    - The traditional circuit-switched telephone network.
    - Allows users to connect to the Internet through standard telephone lines.
    - Connection speeds typically range from 56 kbps, depending on the quality of the line.
2. **ISDN (Integrated Services Digital Network)**:
    - A digital transmission network that allows for higher data rates than standard PSTN.
    - ISDN offers two types of services: BRI (Basic Rate Interface) and PRI (Primary Rate Interface).
        - **BRI**: Commonly used for home or small business connections, provides two 64 kbps B channels.
        - **PRI**: Used by larger organizations, provides 23 B channels (for a total of 1.544 Mbps) in North America.

### **PSTN**

**Public Switched Telephone Network** 

- **Overview**: PSTN, also called plain old telephone service (POTS), is a standard phone line connecting homes to the central office of the Local Exchange Carrier (LEC). It was designed to transmit sound as analog signals.
- **LEC and IXC**:
    - **Local Exchange Carrier (LEC)**: Provides local phone service and owns central office connections.
    - **Interexchange Carrier (IXC)**: Handles long-distance services and manages lines between LECs.
- **Analog Signal**: PSTN uses analog signals, with the telephone microphone converting sound into electrical waveforms (cycling at 2400 bauds/second). These signals are then sent through PSTN lines.
- **Baud Rate**: PSTN operates at a **baud rate of 2400** (cycles per second).
- **Connectors**: Uses **RJ-11 connectors** for phone line connections.
- **Network Interface Unit (NIU) and Demarc**:
    - **NIU**: Small box on the side of a home that connects telephone lines and splits them to wall outlets.
    - **Demarc**: Defines where the telephone company’s responsibility ends and the customer's responsibility begins.
- **Modem and UART**:
    - **Modem**: Converts digital data to analog and vice versa, allowing PC communication over analog PSTN lines.
    - **UART**: A component in the modem that converts parallel (8-bit-wide) digital data from a PC to serial (1-bit-wide) digital data for transmission.
- **Importance**: PSTN and modems might seem outdated, but they’re still in use by around 10 million people in the U.S.

### **ISDN (Integrated Services Digital Network)**

- **PSTN Limitations**: Traditional **PSTN lines** max out around **33 Kbps** due to analog-to-digital conversion and line quality, despite having the capability to support a 64-Kbps DS0 channel.

- **Digital Last Mile**: To meet demands for higher data rates, phone companies developed **ISDN**, a fully digital end-to-end service over existing copper lines, achieving a consistent **64 Kbps** per line. This digital setup improved reliability and throughput.

- **ISDN Channel Types**:
    - **B Channels**: Carry data/voice, using **64 Kbps DS0 channels**.
    - **D Channels**: Handle setup/configuration at **16 Kbps**.

- **ISDN Configurations**:
    - **Basic Rate Interface (BRI)**: Common setup with **2 B channels** and **1 D channel** (2B+D), providing **128 Kbps** total data rate.
    - **Primary Rate Interface (PRI)**: Equivalent to a **full T1 line** with **23 B channels**.
- **Physical Setup**:
    - **ISDN Connections**: Typically uses an **RJ-45 jack** similar to Ethernet.
    - **Terminal Adapter (TA)**: Acts like a modem for ISDN, connecting to the network and allowing LAN connectivity; available in **internal/external** variants.
- **Setup Requirements**: ISDN usage typically requires proximity to a central office (**within ~18,000 feet**), and configuration of an **ISDN phone number** and **Service Profile ID (SPID)**, provided by the ISP or phone company.

**Note**: A **B channel** is a **DS0 channel**, essential to remember for exam preparation.

## DSL

**(Digital Subscriber Line)**

- **Overview**: DSL offers a **dedicated, fully digital connection** through traditional telephone lines, requiring no new infrastructure. It comes primarily in **ADSL** (asymmetric) and **SDSL** (symmetric) types.
- **Types of DSL**:
    - **SDSL**: Offers **equal upload and download speeds**, with packages ranging from 192 Kbps to 9 Mbps, ideal for businesses needing balanced data flow.
    - **ADSL**: Prioritizes **download over upload speeds** (384 Kbps to 15 Mbps for downloads, 128 Kbps to 768 Kbps for uploads), making it affordable and suitable for home use.
    - **VDSL/VDSL2**: Offers even higher speeds (up to 100 Mbps in both directions) at shorter distances.
- **Installation and Operation**:
    - DSL lines allow **simultaneous voice and data transmission**. However, for voice clarity, **filters** are installed on phone lines to separate DSL and POTS signals.
    - DSL modems connect via **RJ-11** to a DSL Access Multiplexer (DSLAM) at the central office, which links users to the internet.
    - DSL modems now require **Point-to-Point Protocol over Ethernet (PPPoE)** for enhanced connection security, necessitating a username and password to access the service.
- **Practical Setup**:
    - DSL setup often includes a **DSL modem** and a router, connected through an RJ-11 cable. Filters are applied on phone lines for uninterrupted voice calls.
    - **PPPoE** settings can be configured on routers, providing simple network access control through user login credentials.

**Key Points**:

- SDSL provides balanced speeds, suitable for business.
- ADSL offers cost-effective asymmetric speeds, great for home use.
- VDSL/VDSL2 enables high speeds but is distance-sensitive.
- PPPoE ensures secure DSL access requiring user authentication.

## **Broadband Cable**

- **Introduction**: The **cable industry** evolved to compete with DSL, utilizing existing coaxial cable infrastructure used for cable TV to provide internet access. This transformation enabled cable modems to become widely available across the United States.
- **Speed and Performance**:
    - Cable modems typically offer **high-speed internet**, with advertised speeds ranging from **5 to 200 Mbps**.
    - Download speeds generally fall between **30 to 200 Mbps**, while upload speeds range from **5 to 10 Mbps**. Variability depends on the specific cable provider and plan.
- **Installation**:
    - **Connection**: A cable modem connects to a coaxial outlet (separate from the TV cable) and is split from the main line, similar to adding another cable outlet.
    - The modem links to a **router**, which then connects to devices using standard **NIC** and **unshielded twisted pair (UTP)** cabling.
- **Technology**:
    - Cable modems communicate through a network structure that includes a **head end**, comparable to a telephone central office. This head end connects to the cable company's broader network.
    - The communication protocol used is **DOCSIS (Data Over Cable Service Interface Specification)**, with the latest standard being **DOCSIS 3.1**.
- **Physical Characteristics**:
    - A cable modem typically features a **coax F-connector** for coaxial cable and an **RJ-45 connector** for Ethernet connections, distinguishing it from DSL modems, which use **RJ-11 connectors**.
- **Market Position**:
    - Cable companies actively market high-speed internet packages, making cable modems a viable choice for both residential and business customers.

**Key Points**:

- Cable modems leverage existing coaxial cable infrastructure to deliver high-speed internet.
- Typical speeds range from 30 to 200 Mbps for downloads and 5 to 10 Mbps for uploads.
- DOCSIS 3.1 is the current standard for cable internet technology.
- The physical connection involves a coaxial outlet and is distinguished from DSL connections by the type of connectors used.

## Satellite Internet Overview

- **Overview**: Satellite Internet is often the only option for high-speed connectivity in rural or remote areas where traditional broadband services like DSL or cable are unavailable. It offers two types of connections: **one-way** and **two-way**.
- **Types of Satellite Connections**:
    - **One-Way Satellite**:
        - **Download**: Data is received via satellite.
        - **Upload**: Requires a separate **PSTN** (Public Switched Telephone Network) or dial-up modem connection for sending data.
    - **Two-Way Satellite**:
        - **Download and Upload**: The service facilitates both downloading and uploading through the satellite connection.
- **Performance**:
    - Satellite services like **HughesNet** can provide download speeds of up to **25 Mbps**, making it a viable option for internet access in rural areas.
- **Installation**:
    - A small **satellite antenna** is necessary for satellite internet. This antenna connects to a **satellite modem**, which in turn connects to your PC or network.

## Fiber Internet

- **Market Evolution**: DSL was initially the leading last-mile WAN option, but cable modems soon gained popularity. To compete, telephone companies began deploying **fiber-to-the-home** (FTTH) and **fiber-to-the-premises** (FTTP) technologies, challenging cable providers.
- **Major Providers**:
    - In the U.S., major providers like **AT&T** and **Verizon (Fios)** offer fiber internet along with television and phone services.
    - Companies like **Google Fiber** provide dedicated internet services, offering speeds up to **1 Gbps**.
- **Technology**:
    - Most FTTH technologies use **Passive Optical Network (PON)** architecture to enhance affordability. This involves:
        - A single fiber line running to a neighborhood switch.
        - Individual fiber connections extending from the switch to each home or business.
    - **Wavelength Division Multiplexing (WDM)** technology allows multiple signals to be transmitted on the same fiber line. The signal is passively split at the switch to route traffic to the correct destination.

# Modem Properties

## Bit Rates vs. Baud Rate

Modem Speed Basics: Home modems transmit data up to 56 Kbps (kilobits per second) but are often confused with 56 kilobaud due to similarity between baud rate and bit rate at lower speeds.

Baud Rate vs. Bit Rate:

Baud Rate: The rate of analog signal cycles per second; PSTN lines sample analog signals 2400 times per second.

Bit Rate: The amount of data sent per second. For 2400-bps modems, each baud (analog cycle) transmits 1 bit, so bit rate and baud rate are equal up to 2400 bps.

Higher Speeds:

To exceed 2400-baud, modems modulate more bits per cycle:
4800 bps uses 2 bits per baud.
56 Kbps (the max for PSTN modems) achieves 24 bits per baud.

Key Point: PSTN modem speeds are multiples of 2400 baud, with the final standard being 56 Kbps for modern PSTN lines.

## **V Standards**

- **Compatibility**: For modems to connect at maximum speed, they need the same modulation standard. Proprietary protocols initially caused compatibility issues, leading to the **CCITT** (now **ITU**) standardizing **V standards** to unify modem speeds.
- **Common V Standards**:
    - **V.22** – 1200 bps
    - **V.22bis** – 2400 bps
    - **V.32** – 9600 bps
    - **V.32bis** – 14,400 bps
    - **V.34** – 28,000 bps
    - **V.90** – 57,600 bps (download)
    - **V.92** – 57,600 bps (download), up to **48 Kbps** upload, with features like **Quick Connect** (faster handshaking) and **Modem On Hold** (stay connected during voice calls).

- **Additional Standards for Data Integrity**:
    - **V.42** – Error checking
    - **V.42bis** & **V.44** – Data compression
    - **MNP5** – Combined error checking and compression
- **Usage Note**: Simply having compatible V standards on both modems allows access to benefits like higher transfer rates and data integrity without extra setup.