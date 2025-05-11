# Chapter 4 The Current Ethernet Specifications

# Name resolution&

![image.png](Chapter%204%20The%20Current%20Ethernet%20Specifications%201199c4fd261480f2a9abe3425536bcec/image.png)

# Binary& Number System

1. **Basic Concept**:
    - The **binary system** uses only two digits: **1** and **0**. Each digit is called a **bit**.
2. **Groupings**:
    - Bits are often grouped as follows:
        - **Nibble**: 4 bits (e.g., `1010`)
        - **Byte**: 8 bits (e.g., `11001010`)
3. **Value Representation**:
    - Binary numbers represent decimal values using powers of 2, starting from the right. Each position's value doubles as you move left.
    - Example for a **Nibble**:
        - If all bits are 1: 8+4+2+1=15
            
            8+4+2+1=158 + 4 + 2 + 1 = 15
            
        - For `1010`: 8+0+2+0=10
            
            8+0+2+0=108 + 0 + 2 + 0 = 10
            
        - For `0110`: 0+4+2+0=6
            
            0+4+2+0=60 + 4 + 2 + 0 = 6
            
4. **Byte Maximum Value**:
    - A byte with all bits as 1: `11111111` equals 128+64+32+16+8+4+2+1=255.
        
        128+64+32+16+8+4+2+1=255128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255
        

### Examples of Binary to Decimal Conversion

- **Binary**: `10010110` → **Decimal**: 128+16+4+2=150
    
    128+16+4+2=150128 + 16 + 4 + 2 = 150
    
- **Binary**: `01101100` → **Decimal**: 64+32+8+4=108
    
    64+32+8+4=10864 + 32 + 8 + 4 = 108
    
- **Binary**: `11101000` → **Decimal**: 128+64+32+8=232
    
    128+64+32+8=232128 + 64 + 32 + 8 = 232
    

### Memorization Chart for Binary-to-Decimal

| **Binary Value** | **Decimal Value** |
| --- | --- |
| 10000000 | 128 |
| 11000000 | 192 |
| 11100000 | 224 |
| 11110000 | 240 |
| 11111000 | 248 |
| 11111100 | 252 |
| 11111110 | 254 |
| 11111111 | 255 |

# Hexadecimal Number System

1. **Basic Concept**:
    - **Hexadecimal** (or **Hex**) uses 16 symbols: 0-9 and A-F (where A=10, B=11, C=12, D=13, E=14, F=15).
2. **Conversion**:
    - Hex values are converted from binary using **nibbles** (4 bits).
    - Each hex digit corresponds to a nibble, so two hex digits make a byte.
3. **Hexadecimal to Binary Conversion**:
    - For example, to convert `0x6A`:
        - 6 = `0110`, A (10) = `1010`
        - Combined: `01101010`
4. **Binary to Hexadecimal Conversion**:
    - For `01010101`:
        - Split into nibbles: `0101` and `0101` → Hex: `0x55`
        - Decimal: 64+16+4+1=85
            
            64+16+4+1=8564 + 16 + 4 + 1 = 85
            

More Conversion Examples

1. **Binary**: `11001100`
    - Hex: `CC` (12 in hex for both nibbles)
    - Decimal: 128+64+8+4=204
        
        128+64+8+4=204128 + 64 + 8 + 4 = 204
        
2. **Binary**: `10110101`
    - Hex: `B5` (B = 11, 5 = 5)
    - Decimal: 128+32+16+4+1=181
        
        128+32+16+4+1=181128 + 32 + 16 + 4 + 1 = 181
        

Understanding these concepts is essential as we move into more complex topics like IP addressing in the upcoming chapters.

4o mini

# Ethernet Addressing with MAC Addresses——————-

Ethernet uses a **Media Access Control (MAC) address**, which is a **48-bit (6-byte)** address written in **hexadecimal format**. Each MAC address is unique to every Ethernet Network Interface Card (NIC).

### Structure of a MAC Address

- **Organizationally Unique Identifier (OUI)**: Assigned by the **IEEE**, this part is **24 bits (3 bytes)** long.
- **Globally Administered Address**: The organization assigns another **24 bits (3 bytes)** for a unique address for each NIC.

**Figure 4.3** illustrates how a 48-bit MAC address is divided:

![image.png](Chapter%204%20The%20Current%20Ethernet%20Specifications%201199c4fd261480f2a9abe3425536bcec/image%201.png)

### Key Bits in MAC Addresses:

- **Individual/Group (I/G) Bit**:
    - **0**: Indicates a MAC address for a device (used in the source MAC header).
    - **1**: Indicates a broadcast or multicast address.
- **Global/Local (G/L) Bit**:
    - **0**: Signifies a globally administered address (standardized by the IEEE).
    - **1**: Indicates a locally administered address.

The low-order 24 bits often start with **24 zeros** for the first card and increment until reaching **24 ones** for the last card (over **16 million** total).

Many manufacturers also use the last six hex digits of the MAC address as part of the NIC's serial number.

# Ethernet at the Data Link Layer——————————

![image.png](Chapter%204%20The%20Current%20Ethernet%20Specifications%201199c4fd261480f2a9abe3425536bcec/image%202.png)

**Function:** Ethernet stations communicate by passing data frames using a format known as the MAC frame. This setup allows for error detection through a method called cyclic redundancy check (CRC), but it does not correct errors.

**Frame Formats:**

- **Ethernet II** includes:
    - **Preamble:** 8 bytes
    - **Destination Address (DA):** 6 bytes
    - **Source Address (SA):** 6 bytes
    - **Type:** 2 bytes
    - **Data:** Variable length (64 to 1500 bytes)
    - **Frame Check Sequence (FCS):** 4 bytes
- **802.3 Ethernet** has similar fields but uses a **Length** field instead of Type.

**Key Fields:**

- **Preamble:** An alternating pattern of 1s and 0s that helps synchronize the receiving device.
- **SFD (Start Frame Delimiter):** A specific sequence (10101011) that helps the receiver sync and detect the start of the data.
- **Destination Address (DA):** A 48-bit MAC address indicating where the packet is sent. It can be a single device or broadcast to all devices (all 1s in binary).
- **Source Address (SA):** A 48-bit MAC address identifying the sending device. Broadcast addresses are not allowed here.
- **Length or Type:** 802.3 uses a Length field, while Ethernet uses a Type field to identify the Network layer protocol.
- **Data:** The actual packet sent from the Network layer, size ranging from 64 to 1500 bytes.
- **FCS:** A field at the end of the frame used to store the CRC for error detection.

**Frame Examples:**

1. An **Ethernet II frame** might show:
    - Destination: 00:60:f5:00:1f:27
    - Source: 00:60:f5:00:1f:2c
    - Type: 08-00 (indicates IP protocol)
2. A **broadcast frame** shows:
    - Destination: ff:ff:ff:ff:ff(indicating a broadcast to all devices)
    - Source: 02:07:01:22:de
    - Protocol Type: 08-00 (indicates IP protocol)
3. An **IPv6 frame** would indicate:
    - Destination: A specific IPv6 address
    - Source: Another MAC address
    - Type: 0x86dd (indicates IPv6 protocol)

**Conclusion:** The Ethernet II frame's Protocol field allows it to carry various Network layer protocols, making it flexible for different types of data.

# Channel Bonding

**Definition:** Channel bonding, also known as Ethernet bonding, combines two or more network interfaces on a host to improve redundancy and increase data throughput.

**Common Names:**

- **Link Aggregation** is the most widely used term.
- Cisco refers to it as **EtherChannel**.

**Purpose:** Channel bonding allows multiple connections to be attached to a server, switches, or even to the Internet. This setup enhances fault tolerance (reliability) and boosts throughput (data transfer speed).

# cable a**bbreviations&**

### **Twisted Pair (Copper) Ethernet Types**

| **Type** | **Medium** | **Speed** | **Cable Type** | **Max Distance** |
| --- | --- | --- | --- | --- |
| **100Base-T** | Twisted Pair (Copper) | 100 Mbps | Cat5 | 100 meters |
| **100Base-TX** | Twisted Pair (Copper) | 100 Mbps | Cat5 | 100 meters |
| **1000Base-T** | Twisted Pair (Copper) | 1 Gbps | Cat5e/Cat6 | 100 meters |
| **1000Base-TX** | Twisted Pair (Copper) | 1 Gbps | Cat6 | 100 meters |
| **10GBase-T** | Twisted Pair (Copper) | 10 Gbps | Cat6a/Cat7 | 100 meters |

### **Fiber Optic Ethernet Types**

| **Type** | **Medium** | **Speed** | **Fiber Type** | **Max Distance** | **Wavelength** |
| --- | --- | --- | --- | --- | --- |
| **100Base-FX** | Fiber Optic (MMF) | 100 Mbps | Multimode | 2 km | --- |
| **1000Base-SX** | Fiber Optic (MMF) | 1 Gbps | Multimode | 300m | 850 nm |
| **1000Base-LX** | Fiber Optic (MMF/SMF) | 1 Gbps | Multimode/Single Mode | 550m (MMF) / 10 km (SMF) | 1310 nm |
| **1000Base-ZX** | Fiber Optic (SMF) | 1 Gbps | Single Mode | 70-80 km | 1550 nm |
| **1000Base-EX** | Fiber Optic (SMF) | 1 Gbps | Single Mode | 30-40 km | 1310 nm |
| **10GBase-SR** | Fiber Optic (MMF) | 10 Gbps | Multimode | 300 meters | 850 nm |
| **10GBase-SW** | Fiber Optic (MMF) | 10 Gbps | Multimode | 300 meters | 850 nm |
| **10GBase-LR** | Fiber Optic (SMF) | 10 Gbps | Single Mode | 10 km | 1310 nm |
| **10GBase-ER** | Fiber Optic (SMF) | 10 Gbps | Single Mode | 40 km | 1550 nm |
| **10GBase-LW** | Fiber Optic (SMF) | 10 Gbps | Single Mode | 10 km | SONET |
| **10GBase-EW** | Fiber Optic (SMF) | 10 Gbps | Single Mode | 40 km | 1550 nm |

# New Words&

**Broadcast&:** A method of sending a message to all devices on a network simultaneously.

**Ethernet&** -  is a widely used networking technology that allows multiple devices to share bandwidth efficiently. Its scalability, ease of implementation, and straightforward troubleshooting make it a preferred choice for both small and large networks. 

**collision domain&**

CSMA&/CD&

# LEFTOVER—————————-

**GBIC** stands for **Gigabit Interface Converter**. It is a type of transceiver used in networking that allows the connection of different types of media (such as fiber optics or copper cables) to network switches and routers. GBICs were commonly used for Gigabit Ethernet connections and support hot swapping, meaning they can be replaced without powering down the device. They have largely been replaced by the smaller **SFP (Small Form-factor Pluggable)** transceivers, which offer similar functionality in a more compact form.