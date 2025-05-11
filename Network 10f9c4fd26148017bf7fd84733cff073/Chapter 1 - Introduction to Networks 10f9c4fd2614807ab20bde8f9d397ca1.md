# Chapter 1 -  Introduction to Networks

1. ***What is network?***
    
    the term network means two or more connected
    computers that can share resources like data and applications, office machines, an Internet
    connection, or some combination of these, these two hosts “talk” to each other using a computer language called binary code, which consists of lots of 1s and 0s in a specific order that describes exactly what they
    want to “say.”
    
2. ***What is LAN?***
    
    A local area network (LAN) is a collection of devices connected together in one physical location, such as a building, office, or home.
    
3. ***What is host?***
    
    The term "host" in networking can be a bit confusing because it can refer to many types of devices, like computers or servers. When talking about TCP/IP (the protocol that lets devices communicate over the internet), a "host" is simply any device that has an IP address. This includes workstations, servers, and other devices.
    

1. ***What is VLAN?***
    
    A VLAN (Virtual Local Area Network) is a logical grouping of devices on a network, allowing them to communicate as if they were on the same physical LAN, even if they're located in different places. VLANs improve network efficiency, security, and flexibility by segmenting devices based on function, department, or user, without the need for them to be physically connected to the same network.
    

5.  ***What is WAN?***

A wide-area network (WAN) is the technology that connects your offices, data centers, cloud applications, and cloud storage together. It is called a wide-area network because it spans beyond a single building or large campus to include multiple locations spread across a specific geographic area, or even the world. For example, businesses with many international branch offices use a WAN to connect office networks together. The world’s largest WAN is the internet because it is a collection of many international networks that connect to each other. This article focuses on enterprise WANs and their uses and benefits.

1. ***What is VPN?***
    
    A Virtual Private Network (VPN) is a networking technology that creates a secure, encrypted connection over a public network, such as the Internet. It allows users to send and receive data as if their devices were directly connected to a private network. 
    

1. ***What is network architecture?***
    
    **1)p2p**
    
    A **peer-to-peer (P2P) network** is a decentralized network architecture where each participant (or "peer") can act both as a client and a server. In this setup, peers can share resources, such as files or processing power, directly with each other without relying on a central server or authority.
    
    2)**client/server**
    
    Client/server networks are the opposite of peer-to-peer networks. In client/server networks, a single server manages the entire network using a network operating system. When a client requests a resource, it sends the request to the main server, which handles security and directs the client to the appropriate resource instead of the request going directly to the resource's location.
    

9. ***What are physical network topologies?***

Just as a topographical map shows the shape of the terrain, the physical topology of a network is also a type of map. It defines the specific characteristics of a network, such as where
all the workstations and other devices are located, and the precise arrangement of all the
physical media like cables. On the other hand, logical topologies, which were covered in the
previous section, delineate exactly how data moves through the network. And though these
two topologies are usually a lot alike, a particular network can have physical and logical
topologies that are very different. But basically, what you want to remember is that a network’s physical topology essentially gives you the lay of the land, and the logical topology
shows how data navigates through that layout.

**1)bus**

**Definition**: Bus topology is a network configuration where all devices are connected to a single central cable, known as the "bus." This cable acts as a shared communication medium for transmitting data.

2)**star** 

**Definition**: Star topology is a network configuration where all devices (nodes) are connected to a central device, typically a switch or hub. Each node has its own dedicated connection to the central device.

3)**ring**

**Definition**: Ring topology is a network configuration where each device (node) is connected to two other devices, forming a circular (ring) structure. Data travels in one direction (or sometimes both directions in a dual-ring setup) around the ring.

4)**mesh**

**Definition**: Mesh topology is a network configuration where each device (node) is connected to every other device in the network, creating multiple pathways for data to travel. This can be implemented in two ways: **full mesh** (where every device is connected to every other device) or **partial mesh** (where only some devices are interconnected).

5)**p2p topology**

**Definition**: Point-to-point topology is a network configuration that involves a direct connection between two devices (nodes). This simple setup allows for dedicated communication between the two endpoints

6)**point to multipoint topology**

Definition: Point-to-multipoint topology is a network configuration where a single central device (point) connects to multiple devices (multipoints). This setup allows one central device to communicate with several other devices, which can be helpful for distributing data to many endpoints.

7)hybrid topology

**Definition**: Hybrid topology is a network configuration that combines two or more different types of network topologies (such as bus, star, ring, mesh, etc.) to form a single, larger network. This allows for the benefits of multiple topologies to be integrated into one network design.

****