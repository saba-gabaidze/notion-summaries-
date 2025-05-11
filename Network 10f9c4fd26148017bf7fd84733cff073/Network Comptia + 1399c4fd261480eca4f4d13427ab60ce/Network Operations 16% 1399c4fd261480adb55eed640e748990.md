# Network Operations 16%

# 3.1

## **Network Metrics**

- **Bandwidth**: Refers to the amount of data transferred over the network within a given time. High bandwidth usage can indicate network congestion, which could lead to performance degradation.
    - **Solution**: Use **NetFlow** or SNMP polling to measure bandwidth on network links and identify bottlenecks.
- **Latency**: This is the delay in the transmission of data across the network. High latency can severely impact the performance of real-time applications like VoIP or video conferencing.
    - **Solution**: Measure latency between devices using ping tests or more advanced network monitoring tools like **SolarWinds** or **PRTG**.
- **Jitter**: Variability in latency, which is especially problematic for real-time applications. Consistent jitter could disrupt voice and video traffic.
    - **Solution**: Monitor jitter levels and ensure they stay within acceptable ranges (e.g., less than 30ms).

## SNMP - 161/162

- **Traps**: SNMP traps allow devices to send notifications (alerts) to a central management system when specific events occur (e.g., link down, threshold exceeded).
    - **Solution**: Configure devices to send SNMP traps to a network management system (NMS) for real-time alerts.
- **Object Identifiers (OIDs)**: These uniquely identify the various data points within an SNMP system (e.g., device temperature, CPU load).
    - **Solution**: Use SNMP OIDs to gather specific device statistics and integrate with monitoring tools.
- **Management Information Bases (MIBs)**: MIBs store the definitions of the OIDs that SNMP can query.
    - **Solution**: Ensure that MIBs for all critical network devices are available in your network management system to facilitate efficient monitoring.

## Network Device Logs

- **Log Reviews**: Check the store’s notebook for important stuff.
- **Traffic Logs**: See how much stuff is moving around to make sure it’s not too much.
- **Audit Logs**: Keep track of who’s doing what in the store.
- **Syslog**: Have a big notebook for everything going on.
- **Severity Levels**: Focus on fixing the biggest problems first.

## **Interface Statistics/Status**

- **Link State (Up/Down)**: Monitoring the up/down status of interfaces is crucial for understanding connectivity and availability.
    - **Solution**: Regularly check interface status through SNMP or network monitoring software to quickly detect failures or issues.
- **Speed/Duplex**: Misconfigured speed/duplex settings can result in inefficient network performance.
    - **Solution**: Ensure that network devices are configured with matching speed and duplex settings and monitor for discrepancies that could cause packet loss or collisions.
- **Send/Receive Traffic**: Monitoring the amount of data sent and received on network interfaces helps detect congestion, traffic spikes, or outages.
    - **Solution**: Use SNMP or traffic monitoring tools to track and visualize traffic flows.
- **Cyclic Redundancy Checks (CRCs)**: CRC errors occur when a packet is corrupted during transmission. A high number of CRC errors can indicate problems with network cabling, interference, or device issues.
    - **Solution**: Keep an eye on **CRC errors** and replace faulty hardware or cables if the error rate increases.
- **Protocol Packet and Byte Counts**: This data helps you identify which protocols are consuming the most bandwidth and whether this aligns with expectations.
    - **Solution**: Use network analysis tools to review protocol usage and optimize traffic flow accordingly.

## **Interface Errors or Alerts**

- **CRC Errors**: High CRC errors are typically due to bad cables, physical layer issues, or network misconfigurations.
    - **Solution**: Monitor CRC errors and replace defective cables or address potential issues with network interfaces.
- **Giants**: Packets larger than the maximum allowable size for an Ethernet frame (typically 1518 bytes) are considered “giants” and can cause issues.
    - **Solution**: Configure the network to drop or manage oversized frames.
- **Runts**: Runts are undersized packets that often result from network issues or misconfigurations.
    - **Solution**: Identify the source of runt frames and fix the configuration or issue.
- **Encapsulation Errors**: These errors are often related to mismatched encapsulation types between network devices (e.g., Ethernet, VLAN).
    - **Solution**: Ensure consistent encapsulation settings across the network.

## **UPS**

 **(Uninterruptible Power Supplies)** and **surge protectors** to ensure continuous power. Monitor power conditions to prevent downtime during outage

## **NetFlow Data**

NetFlow is a network protocol used to collect and analyze flow data, providing valuable insights into traffic patterns.

- **Solution**: Use **NetFlow** analysis tools (e.g., **SolarWinds NetFlow Traffic Analyzer**) to monitor traffic, identify bottlenecks, and ensure efficient use of network resources.

# 3.2?

## Physical Network Diagram

- **Floor Plan**: This shows where everything is in the building, like where the computer rooms or network devices are placed, like drawing out your house or school.
- **Rack Diagram**: Imagine big **shelves** (called racks) where all the important equipment is stored in a **data center**. The rack diagram shows where each device is placed on those shelves.
- **IDF/MDF Documentation**: These are like **special rooms** in a building where network connections are set up. The **MDF** is the main room, and the **IDF** are smaller rooms that connect everything.

### **Common Agreements**

### **Non-Disclosure Agreement (NDA)**

- **Purpose**: A legal agreement where one party agrees not to disclose certain confidential information to third parties.
- **Importance**: Protects sensitive business information from being shared without authorization.

### **Service-Level Agreement (SLA)**

- **Purpose**: A contract that defines the expected service level (e.g., uptime, response time) between a service provider and a client.
- **Importance**: Sets clear expectations for service delivery and performance, ensuring both parties are aligned on key metrics.

### **Memorandum of Understanding (MOU)**

- **Purpose**: A formal agreement between two or more parties that outlines a mutual understanding of goals and actions.
- **Importance**: Helps clarify roles and responsibilities, ensuring all parties are on the same page before proceeding with an initiative or project.

# 3.3

## **High Availability (HA)**

High Availability refers to systems, networks, or services that are designed to operate continuously with minimal downtime, even in the event of hardware failures, maintenance, or other disruptions. HA systems are built using redundant components and technologies to ensure that there is no single point of failure.

Key elements of HA include:

- **Load Balancing**: Distributes incoming network traffic across multiple servers to ensure no single server is overwhelmed. This improves performance and reliability.
- **Multipathing**: Uses multiple paths to transfer data between devices (e.g., storage devices and servers) to ensure that data is always available even if one path fails.
- **NIC Teaming**: Combines multiple network interfaces into one logical unit to provide increased bandwidth and redundancy. If one network interface fails, the other can take over, ensuring continued connectivity.
- **Redundant Hardware/Clusters**: Ensures availability by having duplicate hardware components (servers, switches, routers) or clustering technologies where services are replicated across multiple devices. If one component fails, others can take over without disruption.
    - **Switches, Routers, Firewalls**: These critical network devices must be redundant to prevent network failure in case of malfunction.
- **Multiple ISPs/Diverse Paths**: Ensures that the network remains accessible even if one ISP or path fails. Using multiple ISPs or multiple physical paths to the internet increases reliability.
- **Active-Active vs. Active-Passive**:
    - **Active-Active**: All systems or servers are active and handle requests simultaneously. This maximizes resource usage and offers better performance and redundancy.
    - **Active-Passive**: One system is active and handling the workload, while the other is passive and only takes over when the active system fails. This setup is often simpler and cheaper but provides less immediate resource availability.
- **Virtual Router Redundancy Protocol (VRRP)**: A protocol that ensures router redundancy, allowing for failover in case the primary router goes down. It ensures continuous network connectivity.
- **Recovery Time Objective (RTO)**: The maximum time allowed for a system or service to be down before it causes significant disruption to the business.
- **Recovery Point Objective (RPO)**: Defines the maximum acceptable amount of data loss in the event of a failure. It represents the point in time to which data should be recovered after a disaster.
- **Mean Time Between Failure (MTBF)** and **Mean Time to Repair (MTTR)**: Metrics to assess the reliability and recovery speed of systems. MTBF refers to the average time between failures, while MTTR refers to the time it takes to repair and restore systems after failure.

## **Disaster Recovery (DR)**

Disaster Recovery refers to the process and strategies used to recover systems, applications, and data after a major disaster or failure, ensuring business continuity.

Key concepts in DR include:

- **Redundancy and High Availability (HA) for DR**: Similar to HA, disaster recovery depends on redundant systems and infrastructure to restore operations after a disruption.
- **Cold Site, Warm Site, Hot Site, and Cloud Site**:
    - **Cold Site**: A backup site with no equipment or data, but it provides space and infrastructure to set up systems when needed. It has the longest recovery time but is the most cost-effective.
    - **Warm Site**: A backup site with hardware and network infrastructure but no live data. Systems can be quickly brought online with up-to-date data backups, offering a balance of cost and recovery speed.
    - **Hot Site**: A fully operational backup site that mirrors the primary site with live data. Recovery is almost instantaneous, but this solution is the most expensive.
    - **Cloud Site**: Utilizes cloud-based services for disaster recovery, where virtual machines and data can be quickly spun up in a remote cloud data center. This is increasingly popular for its scalability, flexibility, and cost-effectiveness.
- 

**Facilities and Infrastructure Support**

- **Uninterruptible Power Supply (UPS)**: Provides backup power to prevent service interruptions during power outages.
- **Power Distribution Units (PDUs)**: Distribute power to various network devices and servers. They often have redundant paths to ensure power availability.
- **Generators**: Used as a long-term backup power source during extended power outages.
- **HVAC**: Ensures that servers and other critical equipment are kept at optimal temperatures, preventing overheating.
- **Fire Suppression**: Critical in protecting equipment from fire damage in data centers or server rooms.