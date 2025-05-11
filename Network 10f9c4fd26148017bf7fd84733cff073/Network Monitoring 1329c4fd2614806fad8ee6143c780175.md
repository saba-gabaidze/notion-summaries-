# Network Monitoring

# **SNMP**

**(Simple Network Management Protocol)** is the standard network management protocol for TCP/IP networks. It enables various network monitoring tools and consists of three main components:

- **SNMP Manager**: Requests and processes information from managed devices; runs on a **Network Management Station (NMS)**.
- **Managed Devices**: Devices like workstations, printers, and routers that run specialized software called **agents**.
- **Management Information Bases (MIBs)**: Categorize data that can be queried from managed devices.

**Key Functions of SNMP** include:

- **Get**: The manager requests information from an agent.
- **Response**: The agent sends back the requested information.
- **Set**: The manager instructs the agent to change certain variables.
- **Trap**: The agent sends alerts to the manager without a prior request.

**Example Scenario**: In an art department, an NMS queries a laser printer for page counts (Get/Response). If the printer runs low on toner, it sends a Trap to alert technicians.

**Additional Utilities**: Tools like **snmpwalk** automate multiple Get commands.

**Notification System**: NMS can send alerts via email when intervention is required.

**SNMP Versions**:

- **SNMPv1**: The original version from 1988.
- **SNMPv2**: Minor enhancements over SNMPv1.
- **SNMPv3**: Introduced security features like encryption and better authentication.

**Ports**: SNMP typically uses UDP ports **161** (for agents) and **162** (for managers). With security (TLS), ports **10161** and **10162** are used.

**Exam Tip**: Remember which ports are used for SNMP communications—agents on 161 or 10161 and managers on 162 or 10162.

# **Monitoring Tools**

Monitoring a network involves managing the significant amount of traffic that flows through various components. To effectively monitor, troubleshoot, and optimize networks, the right tools are essential.

**Types of Monitoring Tools**:

1. **Packet Sniffers**: Capture and analyze data packets traveling across the network to diagnose issues.
2. **Protocol Analyzers**: Examine the protocols in use on the network, providing insights into how data is transmitted.
3. **Interface Monitors**: Track the performance of network interfaces, measuring metrics like bandwidth usage and error rates.
4. **Performance Monitors**: Assess overall network performance, including latency and throughput, to ensure optimal operation.

## **Packet Sniffers**

A packet sniffer is a software tool that captures network packets for analysis, saving them in a **capture file**. They can operate on a single computer, a router, or dedicated hardware.

**Key Features**:

- **Usage**: Commonly employed when suspicious network activity is detected.
- **Modes**: To capture all packets, sniffers operate in **promiscuous mode** or on a **mirrored port** on switches, allowing them to gather maximum data.
- **Operation**: They run silently in the background, making them discreet information-gathering tools.

**Integration**: Packet sniffers are often packaged with **protocol analyzers** to facilitate the analysis of captured packets, as they are not typically standalone products.

## **Protocol Analyzers**

- A protocol analyzer processes capture files from packet sniffers, analyzing them according to specific monitoring needs.
- Also known as packet analyzers, they filter and sort data, helping monitor traffic effectively.
- Typical use: answering questions like “What is the IP and MAC address of the device sending out DHCP Offer messages?”

**Wireshark**:

- A popular and free protocol analyzer widely used in the field.
- Developed by Gerald Combs, it features a standard interface for capturing and analyzing packets.
- After selecting an interface to capture from, the main screen displays packets in a numbered list, detailed breakdowns, and hex/ASCII representations.

**Key Features of Wireshark**:

- Captures all traffic unless filters are applied.
- Users can filter captures live or after the fact (e.g., filtering for DHCP packets).
- Filters utilize acronyms (e.g., `bootp` for DHCP, `dns`, `ssh`, `http` for other protocols).

**Tip**: To practice, download Wireshark and explore its features.

## Packet Flow Monitoring with NetFlow

**Overview**:

- Packet flow monitoring involves tracking traffic between specific source and destination devices.
- Developed by Cisco, the primary tool for this is **NetFlow**.

**Key Features of NetFlow**:

- **Flow Concept**: A flow is defined as a stream of packets between two specific endpoints. Each flow is cached in a flow cache.
- **Flow Cache Entries**: Each entry typically contains:
    - Source and destination IP addresses
    - Source and destination ports
    - Source on the device running the flow
    - Total number of bytes transferred in the flow

**Usage**:

- Analyzing flow data helps network administrators understand traffic patterns, enabling network optimization by identifying where to add capacity or make adjustments.

**Activation**:

- To utilize NetFlow, it must be enabled on the network device (e.g., routers and switches).
- For devices that don’t support NetFlow, standalone probes can monitor maintenance ports and send data to a NetFlow collector.

**NetFlow Collectors**:

- Collectors store flow information from multiple devices' NetFlow caches and present it in a table for analysis.
- The choice of a collector tool can depend on features and cost; one popular tool is **LiveAction**.

**Alternative Flow Monitoring Concepts**:

- NetFlow has inspired other traffic flow monitoring tools and standards, including **sFlow**, **NetStream**, and **IPFIX**, which also build upon the idea of analyzing traffic flows.

Note:

To maximize the benefits of NetFlow, ensure it's properly configured and integrated into your network infrastructure.

## Interface monitors

 track the bandwidth and utilization of interfaces on network devices, working like traffic monitors to assess how hard each part of the network is working. For example, you might use one to answer, **“How much of our switch’s Gigabit Ethernet port 17’s capacity is currently being used?”**

**Metrics Monitored**:

- **Bandwidth/Throughput**: Indicates the speed and duplex setting (e.g., full or half) of a port.
- **Utilization**: Shows the percentage of the port’s total bandwidth currently in use.
- **Packet Drops**:
    - Errors: Packets may be dropped if they are malformed or unreadable.
    - Discards: Some packets are intentionally discarded, for example, if they’re intended for a VLAN that isn’t being forwarded on a port.
- **Error Rate**: Monitors the rate of erroneous packets per second.
- **Discards**: Tracks how many frames per second are discarded and provides insight into the reasons, such as VLAN mismatches.
- **Interface Resets**: Measures the frequency of interface resets on a port.

Many interface monitors started as manufacturer-specific tools but now support a range of devices. **Cisco Network Assistant (CNA)**, for example, allows monitoring and managing Cisco routers and switches. While often labeled an interface monitor, CNA also supports setup, maintenance, and troubleshooting across multiple functions on Cisco switches

## Performance monitors

 track various system aspects over time, alerting users to deviations from normal performance. These monitors are typically integrated with specific operating systems or applications to understand system functions in detail. For example, you might use one to determine, **"How many hits per hour did my web server receive over the last two weeks?"**

**Common Performance Monitoring Tools**:

- **Windows Performance Monitor (PerfMon)**: Common in Windows systems.
- **Syslog**: Utilized on macOS and Linux systems.

Performance monitors use **logs** and **baselines** to track and understand system performance.

**Logs**:
Performance monitors use system logs to record metrics over time. Depending on the tool, these metrics may be labeled differently (e.g., **counters** in Windows Performance Monitor or **facilities** in syslog). Logs help administrators review usage patterns, such as bandwidth usage of an Ethernet port.

**Baselines**:
Creating a baseline captures normal system performance, helping to identify anomalies. Baselines typically record CPU usage, network utilization, and other metrics to document optimal performance. Administrators rely on these records for ongoing network management, creating **network configuration and performance baselines** for documentation.

**Log Management**:
Log management ensures log security and maintenance. Logs often contain sensitive data and must be protected by limiting access to designated users. Typically, **cyclical logs** are implemented to prevent logs from consuming too much storage. Cyclical logging deletes the oldest entries as new ones are added, ensuring log size remains manageable. Some logs are also recreated periodically (e.g., daily, weekly) to aid in maintenance.

Retention policies may require log files to be stored for specific periods. Legal guidelines often influence the retention period, so administrators should check legal requirements for compliance.

# Putting together

management and monitoring tools helps administrators handle complex networks like Bayland Widgets’. In a small office, these tools are simple and modular, but larger networks bring more nuanced challenges.

**Scenario Overview**:
In the Bayland Widgets campus area network (CAN), devices across the main office, factory, and warehouse require consistent management. Devices include:

- **Routers** (wired and wireless)
- **Switches**
- **Wireless access points**
- **Servers**
- **Workstations**
- **Printers**
- **Phones**

For complex networks, techs rely on customized monitoring tools rather than a one-size-fits-all approach. Each tool serves a specific purpose—for instance, using **Cacti** to monitor CPU usage or traffic, rather than checking toner levels in a printer.

**Network Operations Center (NOC)**:
A NOC centralizes network management, allowing techs to query SNMP-managed devices and display data visually. Programs like **Cacti** display essential network metrics (e.g., CPU utilization, bandwidth usage), helping techs identify issues.

Network tools allow:

- **Cacti**: Monitors switch CPU, memory usage, file server storage, and wireless channel usage.
- **Nagios Network Analyzer**: Sends proactive alerts for urgent issues (e.g., connectivity problems between access servers).

**Network Monitoring Process**:

1. **Baseline Comparisons**: Historical baselines reveal normal performance, helping identify anomalies when issues arise.
2. **Problem Detection**: Performance monitors quickly compare real-time and baseline data, identifying bottlenecks, failing devices, or traffic overloads.
3. **Network and Packet Analyzers**: Tools like **Wireshark** examine detailed traffic, helping locate the sources of network slowdowns (e.g., high data senders “top talkers” or receivers “top listeners”).

**Example**: Transitioning from IPv4 to IPv6
Testing IPv6 readiness showed that IPv4-disabled machines couldn’t connect to the network. Wireshark verified router IPv6 advertisements, and further troubleshooting identified configuration issues.

In larger troubleshooting cases, administrators use various tools to maintain network health, employing each tool appropriately to optimize network performance and detect issues efficiently.

# **(SIEM)**

**Security Information and Event Management** 

 is a critical approach for large organizations like Bayland Widgets to monitor and manage network security. SIEM combines **Security Event Management (SEM)** and **Security Information Management (SIM)** to provide comprehensive, real-time insights into network security activities.

**Two-Part Process of SIEM**

1. **Security Event Management (SEM)**:
    - **Real-time Monitoring**: SEM continuously monitors security events across the network, often through edge devices positioned at key points.
    - **Centralized Logging**: Events are logged and saved in a single location for easier, holistic review. SEM also consolidates logs from various devices, making data available for centralized analysis.
2. **Security Information Management (SIM)**:
    - **Log Analysis**: SIM involves analyzing logs to detect patterns, anomalies, or security threats, utilizing both automated tools and human review.
    - **File Integrity Monitoring (FIM)**: A key SIM task, FIM checks for changes in files, looking for:
        - **Attributes** (size, name)
        - **Configuration values**
        - **Content and credentials**
        - **Hash values** (for integrity)
        - **Privileges and security settings**
    
    Any deviation from the known "baseline" or authorized state of a file might signal an attack or ongoing threat.
    

**SIEM System Implementation**

SIEM systems are often complex and most commonly found in **enterprise environments**. Organizations might choose to self-manage these systems or outsource to a **Managed Security Service Provider (MSSP)**, who handles the implementation and monitoring tasks. Managed SIEM through an MSSP can be a practical choice for companies needing specialized expertise or around-the-clock security support.