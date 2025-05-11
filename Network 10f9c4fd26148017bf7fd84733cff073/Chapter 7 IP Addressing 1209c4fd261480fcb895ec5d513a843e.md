# Chapter 7 IP Addressing

# Broadcast address

- **255.255.255.255**: Targets all networks and hosts.
- **172.16.255.255**: Targets all subnets and hosts in the 172.16.0.0 network.
- **10.255.255.255**: Targets all subnets and hosts in the 10.0.0.0 network.

# Network Classes

The designers of the Internet categorized networks based on size:

- **Class A**: For networks with a small number of large hosts.
- **Class B**: For networks of moderate size.
- **Class C**: For many networks with a small number of hosts.

**Address Structure:**

- Class A: Network (8 bits) | Host (24 bits)
- Class B: Network (16 bits) | Host (16 bits)
- Class C: Network (24 bits) | Host (8 bits)
- Class D: Used for multicast
- Class E: Reserved for research

# Class A

- **Structure**: The format is **network.host.host.host**.
- **Example**: In the IP address **49.22.102.70**, **49** is the network address, and **22.102.70** is the host address.
- **Network Address**: The first byte (8 bits) is for the network; the remaining three bytes (24 bits) are for host addresses.
- **Class A Range**: The first bit of the first byte must be **0**, making the range **0 to 127** for Class A addresses.
    - Usable addresses: **1 to 126** (0 and 127 are reserved).
- **Total Networks**: There are **128** possible Class A networks, but **126** are usable.
- **Total Hosts**: Each Class A network can have **16,777,216** unique hosts, but after reserving patterns, the maximum usable is **16,777,214**.

**Valid Host IDs in Class A:**

- **Network Address**: All host bits off (e.g., **10.0.0.0**).
- **Broadcast Address**: All host bits on (e.g., **10.255.255.255**).
- **Valid Hosts**: Numbers between the network and broadcast addresses (e.g., **10.0.0.1** to **10.255.255.254**).

# Addresses Class B

In a **Class B** network address, the structure is as follows:

- **Format:** `network.network.host.host`
- **Example:** In the IP address **172.16.30.56**, the **network address** is **172.16**, and the **host address** is **30.56**.

**Key Points**

1. **Network and Host Segmentation:**
    - The first **2 bytes** (or **16 bits**) are designated for the **network address**.
    - The remaining **2 bytes** are used for **host addresses**.
2. **Address Range:**
    - Class B addresses start with the binary digits **10**, which indicates the first byte must be in the range of **128 to 191**.
    - This gives a total of **16,384** (or **2^14**) unique Class B network addresses.
3. **Host Addresses:**
    - Each Class B network can have **65,534** usable host addresses.
    - This is calculated as **2^16 - 2** (subtracting 2 for reserved addresses).

**Valid Host Example**

- **Network Address:** All host bits turned off is **172.16.0.0**.
- **Broadcast Address:** All host bits turned on is **172.16.255.255**.
- **Valid Host Range:** The valid host addresses fall between the network and broadcast addresses: **172.16.0.1** through **172.16.255.254**.

# Addresses Class C

- **Structure:** `network.network.network.host`
- **Example:** For the IP address `192.168.100.102`:
    - **Network Address:** `192.168.100`
    - **Host Address:** `102`
    - 

**Key Points:**

1. **Addressing:**
    - The first three bytes (24 bits) are for the network.
    - The last byte (8 bits) is for host addresses.
2. **Binary Representation:**
    - Class C addresses always start with the binary `110` in the first octet.
    - The range for the first octet is from `192` to `223`:
        - `11000000` (192) to `11011111` (223).
3. **Number of Networks:**
    - There are 221 or **2,097,152 possible Class C networks**.
        
        2212^{21}
        
4. **Host Addresses:**
    - Each Class C network has **1 byte (8 bits)** for host addresses.
    - This allows for 28 or **256 addresses**, but:
        
        282^8
        
        - **2 addresses are reserved:**
            - All host bits off: Network ID (e.g., `192.168.100.0`).
            - All host bits on: Broadcast address (e.g., `192.168.100.255`).
    - **Total valid host addresses per Class C network:** **254** (from `192.168.100.1` to `192.168.100.254`).

# D and E

- **Class D (224–239):** Used for multicast addresses. The multicast range is from **224.0.0.0** to **239.255.255.255**.
- **Class E (240–255):** Reserved for scientific purposes but not covered in detail.

Just remember that Class D is for multicast!

# Reserved IP Address Space(private)

certain IP addresses are reserved and cannot be assigned to hosts. These addresses serve specific functions. For details, refer to Table 7.1, which lists these addresses and their purposes.

- **Class A (10.0.0.0 to 10.255.255.255):** Used for large private networks.
- **Class B (172.16.0.0 to 172.31.255.255):** Used for medium-sized private networks.
- **Class C (192.168.0.0 to 192.168.255.255):** Used for small private networks.

These addresses are not routable on the public internet and are intended for internal use within private networks.

# **APIPA**

 **(Automatic Private IP Addressing):**

- Used when there's no DHCP server available, and Windows automatically assigns IPs.
- It assigns an IP address in the range **169.254.0.1 to 169.254.255.254** with a **Class B subnet mask of 255.255.0.0**.
- This lets hosts communicate locally without manual IP configuration.

# Broadcast Addresses

- **Layer 2 Broadcasts (Hardware Broadcasts):**
    - Sent to all devices on a local LAN.
    - Address: **FF.FF.FF.FF.FF.FF** (all 1s in binary).
    - Limited to the LAN, doesn’t go beyond a router.
- **Layer 3 Broadcasts (Network Broadcasts):**
    - Sent to all hosts on a specific network.
    - Example: If the network is **172.16.0.0/16**, the broadcast address is **172.16.255.255** (all host bits are set to 1).
    - **255.255.255.255** is a special broadcast to all networks and hosts in the local network.
    - Example of use: Address Resolution Protocol (ARP) requests.
- **Unicast:**
    - Sent to a specific host.
    - Example: A DHCP client sends a broadcast for an IP address, and the router forwards it as a unicast packet to the DHCP server (e.g., **172.16.10.1**).
- **Multicast:**
    - Sent from one source to multiple subscribed devices across different networks.
    - Multicast addresses range from **224.0.0.0 to 239.255.255.255** (Class D).
    - Example: A Routing Information Protocol (RIP) packet sent to **224.0.0.10**.
    - Multicast saves bandwidth by only targeting subscribed devices, unlike broadcasts that reach all hosts on the network.

# IPv6 Addressing and Expressions

- **Length**: An IPv6 address is **128 bits**, compared to **32 bits** for IPv4.
- **Format**: IPv6 addresses are written in **hexadecimal** and are composed of **eight groups** of four hexadecimal digits (16 bits each), separated by colons. For example:
    
    ```makefile
    makefile
    Copy code
    2001:0db8:3c4d:0012:0000:0000:1234:56ab
    
    ```
    

**Address Components**

1. **Global Prefix**: The first part of the address (e.g., `2001:0db8:3c4d`) identifies the network.
2. **Subnet**: The next segment specifies the subnet (e.g., `0012`).
3. **Interface ID**: The last part (e.g., `0000:1234:56ab`) uniquely identifies the interface on a networked device.

**Writing IPv6 Addresses**

- **Hexadecimal Representation**: Each segment uses hexadecimal digits (0-9, A-F).
- **Brackets for URLs**: When entering an IPv6 address in a web browser, enclose it in brackets to avoid confusion with port numbers. For example:
    
    ```vbnet
    vbnet
    Copy code
    http://[2001:0db8:3c4d:0012:0000:0000:1234:56ab]/default.html
    
    ```
    

**Importance of DNS**

- Since IPv6 addresses are long and complex, using **Domain Name System (DNS)** for translating domain names (like [www.example.com](http://www.example.com/)) into IP addresses will be critical for ease of use.

## Shortening IPv6 Addresses

1. **Remove Leading Zeros**:
    - You can drop leading zeros in each block of the address. For example:becomes:
        
        ```makefile
        makefile
        Copy code
        2001:0db8:3c4d:0012:0000:0000:1234:56ab
        
        ```
        
        ```makefile
        makefile
        Copy code
        2001:db8:3c4d:12:0:0:1234:56ab
        
        ```
        
2. **Compress Blocks of Zeros**:
    - If you have contiguous blocks of zeros, you can replace them with a double colon (`::`). For instance:can be further simplified to:
        
        ```makefile
        makefile
        Copy code
        2001:db8:3c4d:12:0:0:1234:56ab
        
        ```
        
        ```makefile
        makefile
        Copy code
        2001:db8:3c4d:12::1234:56ab
        
        ```
        

**Rules for Shortening**

- **Only One Block of Zeros**: You can only replace **one contiguous block** of zeros with `::`. For example:
    
    ```makefile
    makefile
    Copy code
    2001:0000:0000:0012:0000:0000:1234:56ab
    
    ```
    
    can become:
    
    ```makefile
    makefile
    Copy code
    2001::12:0:0:1234:56ab
    
    ```
    
- **Invalid Use of Double Colons**: You cannot use double colons multiple times in an address. For example:
    
    ```makefile
    makefile
    Copy code
    2001::12::1234:56ab
    
    ```
    
    is incorrect. The correct shortening retains only one block of double colons:
    
    ```makefile
    makefile
    Copy code
    2001::12:0:0:1234:56ab
    
    ```
    

## Address Types

1. **Unicast**:
    - **Definition**: Packets addressed to a unicast address are delivered to a single interface.
    - **Types**:
        - **Global Unicast Addresses**: These are publicly routable addresses, similar to IPv4.
        - **Link-Local Addresses**: Not routable beyond the local network segment; useful for creating temporary local area networks (LANs) for file sharing or access.
        - **Unique Local Addresses (ULAs)**: Designed for non-routable use, these addresses are nearly globally unique, minimizing the chance of overlap with other addresses. They replace site-local addresses and facilitate communication within a site while being routable across multiple local networks.
2. **Multicast**:
    - **Definition**: Packets sent to a multicast address are delivered to all interfaces identified by that address. These are often referred to as one-to-many addresses.
    - **Identification**: Multicast addresses in IPv6 always begin with `FF`.
3. **Anycast**:
    - **Definition**: Similar to multicast, anycast addresses identify multiple interfaces. However, packets sent to an anycast address are delivered to **only one** of the addresses—specifically, the closest one based on routing distance.
    - **Purpose**: This allows for a single address to be applied to multiple interfaces, functioning as a one-to-one-of-many address.

# **Special Reserved Addresses in IPv6**

**Here’s a simplified summary of the key IPv6 addresses and address ranges you should remember:**

- **:: (0:0:0:0:0:0:0:0)**: Equivalent to IPv4's 0.0.0.0; used as the source address in stateful configurations.
- **::1 (0:0:0:0:0:0:0:1)**: Equivalent to IPv4's 127.0.0.1; the loopback address.
- **0:0:0:0:0:0:192.168.100.1**: Representation of an IPv4 address in a mixed IPv6/IPv4 environment.
- **2000::/3**: Global unicast address range; used for standard IPv6 addresses.
- **FC00::/7**: Unique local unicast range; similar to private IPv4 addresses.
- **FE80::/10**: Link-local unicast range; used for communication within a local network.
- **FF00::/8**: Multicast range; used for multicast addresses.
- **3FFF:FFFF::/32**: Reserved for examples and documentation.
- **2001:0DB8::/32**: Also reserved for examples and documentation.
- **2002::/16**: Used with 6to4, allowing IPv6 packets to be sent over an IPv4 network without configuring explicit tunnels.

# !!!!!!!!!!!

Remember the Class A range. The IP range for a Class A network is 1–126. This provides
8 bits of network addressing and 24 bits of host addressing by default.

Remember the Class B range. The IP range for a Class B network is 128–191. Class B
addressing provides 16 bits of network addressing and 16 bits of host addressing by default.

Remember the Class C range. The IP range for a Class C network is 192–223. Class C
addressing provides 24 bits of network addressing and 8 bits of host addressing by default.

The Class A private address range is 10.0.0.0 through
10.255.255.255.

The Class B private address range is 172.16.0.0 through 172.31.255.255.

The Class C private address range is 192.168.0.0 through 192.168.255.255.

5