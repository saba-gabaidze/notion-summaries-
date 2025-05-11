# Chapter 8 IP Subnetting, Troubleshooting IP, and Introduction to NAT

# How to Create Subnets

To subnet a network, you take bits from the host portion of the IP address and use them to define subnets. The more subnets you create, the fewer bits you’ll have for hosts. Here’s a simplified guide for subnetting:

1. **Determine required network IDs:**
    - One for each subnet.
    - One for each wide area network (WAN) connection.
2. **Determine required host IDs per subnet:**
    - One for each device (TCP/IP host).
    - One for each router interface.
3. **Based on this, create:**
    - A subnet mask for the whole network.
    - A unique subnet ID for each physical segment.
    - A range of host IDs for each subnet.

# Powers of 2

![image.png](Chapter%208%20IP%20Subnetting,%20Troubleshooting%20IP,%20and%20I%201229c4fd26148026bff7ec0b7f26e5b4/image.png)

# CIDR

Classless Inter-Domain Routing

![image.png](Chapter%208%20IP%20Subnetting,%20Troubleshooting%20IP,%20and%20I%201229c4fd26148026bff7ec0b7f26e5b4/image%201.png)

# Subnetting a Class C Address

## **How Many Subnets?**

- Use the formula: **2^x = number of subnets**.
- Here, **x** is the number of bits you borrowed for subnetting (the number of 1s in the subnet mask).
- **Example**: If your subnet mask is 255.255.255.192 (or 11000000 in binary), you borrowed 2 bits, resulting in **2² = 4 subnets**.

## **How Many Valid Hosts Per Subnet?**

- Use the formula: **2^y - 2 = number of valid hosts per subnet**.
- Here, **y** is the number of bits remaining for hosts (the number of 0s in the subnet mask).
- **Example**: For the subnet mask 255.255.255.192 (which has 6 bits left for hosts), you get **2⁶ - 2 = 62 valid hosts**.

## **What Are the Valid Subnets?**

- Calculate the **block size**: **256 - subnet mask value**.
- Use the block size to find valid subnets by counting in increments.
- **Example**: For a subnet mask of 192, the block size is **256 - 192 = 64**. The valid subnets would be **0, 64, 128, 192**.

## **What’s the Broadcast Address for Each Subnet?**

- The broadcast address for the **0 subnet** is **63** (next subnet is 64).
- The broadcast for the **64 subnet** is **127** (next is 128).
- The broadcast for the **128 subnet** is **191** (next is 192).
- The broadcast for the **192 subnet** is **255**.

## **What Are the Valid Hosts?**

- **Example**: For the **64 subnet** (subnet = 64, broadcast = 127), valid hosts range from **65 to 126**.

# dasazepirebeli chart

### /25

- **Subnet Mask:** 255.255.255.128
- **Binary Representation:** 10000000
- **Block Size:** 128
- **Subnets:** 2
- **Hosts per Subnet:** 126

### /26

- **Subnet Mask:** 255.255.255.192
- **Binary Representation:** 11000000
- **Block Size:** 64
- **Subnets:** 4
- **Hosts per Subnet:** 62

### /27

- **Subnet Mask:** 255.255.255.224
- **Binary Representation:** 11100000
- **Block Size:** 32
- **Subnets:** 8
- **Hosts per Subnet:** 30

### /28

- **Subnet Mask:** 255.255.255.240
- **Binary Representation:** 11110000
- **Block Size:** 16
- **Subnets:** 16
- **Hosts per Subnet:** 14

### /29

- **Subnet Mask:** 255.255.255.248
- **Binary Representation:** 11111000
- **Block Size:** 8
- **Subnets:** 32
- **Hosts per Subnet:** 6

### /30

- **Subnet Mask:** 255.255.255.252
- **Binary Representation:** 11111100
- **Block Size:** 4
- **Subnets:** 64
- **Hosts per Subnet:** 2

# Troubleshooting IP Addressing

Basic Troubleshooting Steps:

## Ping commands

- **Ping the Loopback Address:**
    - Command: `ping 127.0.0.1`
    - **Response:**
        - **Successful:** IP stack is initialized.
        - **Failed:** Reinstall TCP/IP protocol suite.
- **Ping the Local Host IP:**
    - Command: `ping <local-host-ip> (e.g., 172.16.10.2)`
    - **Response:**
        - **Successful:** NIC is functioning.
        - **Failed:** Possible NIC problem.
- **Ping the Default Gateway (Router):**
    - Command: `ping <gateway-ip> (e.g., 172.16.10.1)`
    - **Response:**
        - **Successful:** NIC is connected to the network.
        - **Failed:** Local network issue (NIC to router).
- **Ping the Remote Server:**
    - Command: `ping <server-ip> (e.g., 172.16.20.2)`
    - **Response:**
        - **Successful:** IP communication is working.
        - **Failed:** Possible issue with the remote network.

## Helpful commands

- **traceroute**: Displays the list of routers on a path to a network destination by using TTL time-outs and ICMP error messages. This command will not work from a DOS prompt.

- **tracert**: Same command as traceroute, but it’s a Microsoft Windows command and will not work on other devices, like a Cisco router or Unix box.

- **arp -a**: Displays IP-to-MAC-address mappings on a Windows PC.

- **ipconfig /all**: Used only from a DOS prompt. Shows the PC network configuration.

# NAT

**Network Address Translation (NAT)** is a technique used to manage IP address allocation and connectivity. Here’s a simplified overview:

### Purpose of NAT:

- **Conserves IP Addresses**: NAT allows multiple devices with private IP addresses to share a smaller number of public IP addresses.
- **Useful in Various Scenarios**:
    - When connecting to the Internet without globally unique IP addresses.
    - When changing to a new Internet Service Provider (ISP) that requires a different addressing scheme.
    - When merging two networks that have duplicate IP addresses.

### Where NAT is Used:

- Typically configured on a **border router** to manage the flow of traffic between an internal network and the Internet.

### Advantages of NAT:

1. **Conserves Public IP Addresses**: Reduces the need for many public addresses.
2. **Reduces Address Overlap**: Helps avoid conflicts when networks merge.
3. **Increases Flexibility**: Makes it easier to connect to different ISPs.
4. **Avoids Renumbering**: Internal addresses can remain the same even if the ISP changes.

### Disadvantages of NAT:

1. **Latency**: Translation can introduce delays in data transmission.
2. **Loss of Traceability**: Makes it harder to trace the source of IP packets.
3. **Application Compatibility Issues**: Some applications may not work properly with NAT enabled.

- **Static NAT (SNAT)**:
    - **Description**: Maps a local IP address to a specific global IP address on a one-to-one basis.
    - **Requirement**: You need one public IP address for every device on your network.
- **Dynamic NAT**:
    - **Description**: Maps a private IP address to a public IP address from a pool of available public IPs.
    - **Requirement**: You need enough public IP addresses in the pool for all devices that will access the Internet.
- **Overloading (Port Address Translation - PAT)**:
    - **Description**: Maps multiple private IP addresses to a single public IP address using different ports.
    - **Benefit**: Allows thousands of users to connect to the Internet using just one public IP address, making it a highly efficient way to manage IP address usage.

### NAT Terminology

1. **Global Addresses**:
    - These are public IP addresses used on the Internet. You only need them if you're accessing the Internet.
2. **Local Addresses**:
    - These are private IP addresses used within a local network.
3. **Inside Local Address**:
    - This is the private IP address of a device (like a computer) trying to connect to the Internet.
4. **Outside Local Address**:
    - This is the address of the destination host (like a website or server) before translation, usually a public address.
5. **Inside Global Address**:
    - After translation, this becomes the public IP address that represents the inside local address to the outside world.
6. **Outside Global Address**:
    - After translation, this refers to the address of the destination host as it appears to the outside world.

Summary Table

| **Name** | **Meaning** |
| --- | --- |
| Inside Local | Private address of the sending device before translation |
| Outside Local | Destination host address before translation |
| Inside Global | Public address of the sending device after translation |
| Outside Global | Destination host address after translation |

# !!!!!!!!!!!!!

 A network is 1–126. This provides
8 bits of network addressing and 24 bits of host addressing by default.

Remember the Class B range. The IP range for a Class B network is 128–191. Class B
addressing provides 16 bits of network addressing and 16 bits of host addressing by default.

Remember the Class C range. The IP range for a Class C network is 192–223. Class C
addressing provides 24 bits of network addressing and 8 bits of host addressing by default.

![image.png](Chapter%208%20IP%20Subnetting,%20Troubleshooting%20IP,%20and%20I%201229c4fd26148026bff7ec0b7f26e5b4/image%202.png)

![image.png](Chapter%208%20IP%20Subnetting,%20Troubleshooting%20IP,%20and%20I%201229c4fd26148026bff7ec0b7f26e5b4/image%203.png)

![image.png](Chapter%208%20IP%20Subnetting,%20Troubleshooting%20IP,%20and%20I%201229c4fd26148026bff7ec0b7f26e5b4/image%204.png)