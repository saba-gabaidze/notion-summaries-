# 3.1 Compare and contrast security implications of different
architecture models.

# Securing the Network

## **Firewalls**

- First line of defense, filtering network traffic using Access Control Lists (ACLs). Default rule: "deny all"; allow rules must be created.

## **ACLs**

- Define traffic rules based on specific criteria.

## **IDS/IPS**

- Intrusion Detection Systems detect, and Intrusion Prevention Systems block suspicious activities in real time.

## **SIEM**

- Security Information and Event Management tools analyze data across network sources, providing real-time alerts for proactive defense.

## Securing the Servers~~~~~~~~

## **Domain Controllers**

- Authenticate users.

## **SQL Servers**

- Store sensitive data like credit card information.

## **Mail Servers**

- Frequent attack vectors; require robust security.

## **Video Conferencing Apps**

- Secure tools like Zoom/Teams against intruders.

## **Cloud Storage**

- Providers (AWS S3, Azure Blob, Google Cloud) offer encryption, access controls, and monitoring.

## Securing the Hosts~~~~~~~~~~

## **Endpoint Security**

- Use antivirus, Endpoint Detection and Response (EDR), and Mobile Device Management (MDM) tools.

## **MFA**

- Multifactor authentication adds layers of verification, protecting accounts from unauthorized access.

# Architecture and Infrastructure Concepts$

# Cloud Computing

## **Cloud Service Providers (CSPs)~~~~~~~~~~**

- Choose trusted providers like Microsoft or AWS. Cloud services are scalable, and you pay for what you use.

## **Public Cloud**

Multi-tenant model, shared server hosting for multiple organizations.

## **Private Cloud**

 Single-tenant, more secure with separate hosting for each organization.

## **Community Cloud**

 Shared costs among companies in the same industry for a dedicated application.

## **Hybrid Cloud**

 Combines on-premises and cloud infrastructures, ideal for businesses with diverse needs.

## **Cloud Services~~~~~~~~~~~~~**

## **IaaS (Infrastructure as a Service)**

Provides network hardware (servers, storage, firewalls). Customers must configure and patch the devices

## **SaaS (Software as a Service)**

Predefined software applications hosted by the CSP (e.g., Office 365, Salesforce).

## **PaaS (Platform as a Service)**

 Provides development environments for building applications (e.g., Microsoft Azure, MySQL).

## **SECaaS (Security as a Service)**

Provides Identity and Access Management (IAM) and security staffing.

## **XaaS (Anything as a Service)**

 Includes services like Network as a Service (NaaS), Desktop as a Service (DaaS), Backup as a Service (BaaS), etc.

## Responsibility~~~~~~~~~~

In the cloud, responsibilities are shared between the service provider and the customer. The level of responsibility depends on the type of cloud service being used. Providers typically handle server availability and physical security, while customers are responsible for application security.

## Hybrid Considerations~~~~~~~~~~~

## Data Management

- **Complexity**: Maintaining control and visibility over data is difficult with cloud and on-premises integration.
- **Latency**: Communication between on-premises and cloud resources may suffer from slowdowns, especially for applications over large physical distances.
- **Synchronization**: Issues with bandwidth can lead to poor data synchronization between on-premises and cloud infrastructures.
- **Maintenance Overhead**: Managing both resources can slow down maintenance tasks due to the added complexity.

## Third-party Vendors~~~~~~~~~~~~~~

External suppliers offer expertise but can introduce security risks:

## **Data Breaches**

Lax security by vendors can lead to data breaches and financial losses.

## **Security Vulnerabilities**

Vendor software or services may introduce vulnerabilities, potentially creating entry points for cybercriminals.

## **Compliance Challenges**

 Vendors failing to meet industry regulations can result in noncompliance and legal consequences.

## **Operational Disruption**

Dependence on vendors for critical services can cause disruptions if the vendor faces downtime or issues.

# Infrastructure as Code (IaC)

 IaC involves defining and managing IT infrastructure using machine-readable code (e.g., YAML, JSON). It replaces manual provisioning with automation.

## **Efficiency**

Automates infrastructure tasks, reducing provisioning time from weeks to minutes.

## **Consistency**

 Ensures uniform configurations across environments, minimizing errors.

## **Version Control**

IaC code can be tracked and managed like application code, promoting collaboration and transparency.

**Tools and Providers**

- Cloud providers: AWS, Azure, Google Cloud.
- Tools: Terraform, Ansible, Puppet, Chef.

# Serverless Computing

 Serverless computing offloads server management to the cloud service provider (CSP), allowing developers to focus on code without provisioning, configuring, or managing servers.

- CSP manages scaling, infrastructure security, and physical servers.
- Backend as a Service (BaaS) offerings handle backend functions like databases, authentication, and file storage.
- **Security**: CSPs provide robust security with dedicated expertise.
- **Cost-Effective**: Eliminates capital expenditure on physical servers.
- **Scalability**: Automatically adjusts resources based on demand.

# Microservices Architecture

Microservices involve breaking down an application into smaller, independent services that communicate via APIs. Each service handles a specific business capability (e.g., authentication, payment processing).

- Services operate independently, allowing separate development without disrupting the entire application.
- A failure in one microservice doesn’t affect the entire application, ensuring high availability and fault tolerance.

## **Agility**

 Enables quick adaptation to changing business needs with independent service updates.

## **Scalability**

 Services scale independently to handle traffic spikes.

## **Faster Development**

 Smaller code bases and independent development cycles accelerate time-to-market.

## **Easy Maintenance**

 Simplified troubleshooting and maintenance by isolating issues to specific services.

## Improved Fault Tolerance

 Microservices are inherently fault-tolerant, as a failure in one service does not cascade to
others.

## **Decomposition**

 Breaks down complex applications into manageable components, simplifying development and maintenance

## **Independence**

 Allows independent deployment of services, enabling quicker updates and parallel teamwork.

# Network Infrastructure

 Network infrastructure combines devices, protocols, and packet routing, working together in interconnected environments.

## **Router**

- Connects networks, routes IP packets, uses default routes (e.g., 0.0.0.0) when necessary.

## **Switch**

Links devices in LAN, uses MAC addresses to route packets via CAM tables. Includes port security for unauthorized access prevention

## **Layer 3 Switch**

 Operates at both Layer 2 and Layer 3 for enhanced routing within LANs.

## **Wireless Access Point (WAP)**

 Connects wireless devices to wired networks for Wi-Fi

## **Load Balancer**

 Distributes traffic evenly across servers to handle high loads.

## **Web Application Firewall (WAF)**

Protects web servers, applications, and data from attacks.

## **Network Intrusion Prevention System (NIPS)**

Monitors and prevents malicious network activity using techniques like signature-based and anomaly detection.

- **Function**: NIP is a type of **IPS** but is usually more specialized to focus solely on preventing network-based threats. It monitors network traffic and performs deep packet inspection (DPI) to block potential attacks in real-time.
- **Focus**: **Real-time network protection**—NIP is more focused on **actively preventing attacks** and blocking harmful traffic, much like an IPS but typically with a more dedicated focus on **network-level threats** like DoS, DDoS, and buffer overflows.

## Physical Isolation~~~~~~~~~~~~~

 Physical isolation involves keeping sensitive systems or computers separate from any network to prevent exposure or compromise.

## Air-gapped

network – a system with no network or internet connectivity, ensuring data cannot be stolen

- **Usage**: Common in secure environments like R&D departments to protect sensitive information such as trade secrets.
- **Data Transfer**: Data can only be transferred using removable media (e.g., USB drives)

## Logical Segmentation~~~~~~~~

- **Definition**: Logical segmentation involves dividing a network into smaller parts based on logical boundaries, not physical ones.
- **Purpose**: Enhances security, manages data flow, and isolates traffic within a network.

## **Subnetting**

- **Definition**: Dividing a network into smaller subnets for better control and security.
- **Security Benefit**: Reduces the broadcast domain, limiting the impact of malicious activities (e.g., containing a virus).

## **Virtual Local Area Network (VLAN)**

- **Definition**: A software-based method for grouping network ports together, creating separate networks within a larger one.
- **Purpose**: Controls traffic flow and isolates devices or departments (e.g., IT and Finance).
- **VLAN Identification**: Each VLAN is tagged with an ID for easy identification and routing.

## SDN~~~~~~~~~~~~~~~

## Software-Defined Networking

**SDN** addresses the growing demands on network infrastructure, especially with virtual cloud computing. It separates the management, control, and data planes, which are traditionally integrated in network devices like switches and routers.

## **Management Plane**

- **Function**: Orchestrates network intelligence and monitors network traffic.
- **Purpose**: Manages and oversees the overall health and performance of the network.

## **Control Plane**

- **Function**: Acts as the “brain” of the network, typically represented by an SDN controller.
- **Purpose**: Makes high-level decisions about routing, network policies, and resource allocation based on rules set by administrators.
- **Benefit**: Provides administrators with a global view of the network and a single point to apply changes.

## **Data Plane**

Comprises switches, routers, and access points that forward data packets based on control plane instructions.

- **Efficient Resource Allocation**: Separating the control and data planes allows for dynamic resource allocation, responding to real-time network demands.
- **Dynamic Security Control**: SDN enables granular control over network traffic, allowing for real-time response to security threats (e.g., isolating compromised network segments).

# On-Premises

**On-premises** refers to an organization's infrastructure and software that are physically hosted within its own facilities. This model offers organizations complete control over their systems and data.

1. **Control & Security**: Essential for industries with strict compliance (e.g., healthcare, finance) to keep sensitive data on-site.
2. **Low-Latency & High-Performance**: Ideal for real-time processing and applications requiring fast, localized data access.
3. **Legacy System Integration**: Allows gradual modernization while leveraging existing legacy systems, avoiding costly cloud replacements.

# Centralized / Decentralized

## **Centralized**

- **Structure**: Decision-making authority is concentrated at the top (e.g., CEO).
- **Example**: **McDonald's Corporation**: Decisions on menu offerings, pricing, and marketing are made at headquarters to ensure consistency and efficient supply chain management globally.

## **Decentralized**

- **Structure**: Decision-making authority is distributed across various levels and locations.
- **Benefits**: Empowers employees, promotes ownership, and allows for quick responses to local market conditions.
- **Example 1**: **Toyota Motor Corporation**: Regional divisions have autonomy to design and produce vehicles tailored to local markets.
- **Example 2**: **Blockchain**: Uses a distributed public ledger to record transactions, with copies held by participants.

# Containerization

Containerization bundles software into containers, which package an application’s code, libraries, dependencies, and configurations for consistent and efficient deployment across various environments.

- **Portability**: Containers are self-sufficient and can be moved seamlessly between environments (e.g., developer laptop, staging server, cloud data center).
- **Independence**: Containers work independently from any operating system, providing agility in development and deployment.

# Virtualization

Virtualization involves providing virtual desktops via **Virtual Desktop Infrastructure (VDI)**, where virtual machines (VMs) are used to deliver cloud desktops to clients. The CSP controls the VM image, and if a VM is corrupted, it can be replaced with a new one immediately.

- **VDI**: A pool of identical VMs is used, accessible through a thin client (e.g., Citrix), with only mouse clicks and keyboard inputs exchanged between the desktop and VM.
- **Access**: Users can access modern applications from legacy devices, as the apps run within the virtual machine.
- **App-V**: A tool by Microsoft that virtualizes applications, separating them from the OS and running them in an isolated environment. This can save space, simplify updates, and resolve compatibility issues.

# IoT (Internet of Things)

IoT refers to a network of interconnected physical objects embedded with sensors, software, and connectivity, allowing them to collect and exchange data over the internet. IoT enables real-time monitoring, automation, and smarter decision-making, revolutionizing industries and offering greater efficiency, productivity, and comfort.

**CONSIDERATIONS**

## **Lack of Standardization**

The absence of a unified security framework leads to inconsistent security measures across IoT devices and manufacturers, creating gaps in overall security.

## **Data Privacy Concerns**

 IoT devices collect vast amounts of personal and sensitive data, which, if mishandled or accessed unauthorized, could lead to privacy breaches or identity theft.

## **Insecure Communication**

 IoT devices may communicate over unsecured channels, making them vulnerable to eavesdropping or man-in-the-middle attacks. Secure communication protocols like TLS/SSL should be implemented.

## **Lifecycle Management**

 IoT devices have long lifecycles, and when manufacturers discontinue updates or support, devices remain vulnerable to unpatched security flaws.

## **Physical Attacks**

 Attackers can tamper with IoT devices, extract sensitive data, or reprogram them maliciously if physical access is gained.

## **Supply Chain Risks**

IoT components are sourced globally, making them vulnerable to tampering or the insertion of malicious components, which can compromise security.

## **User Awareness**

 End users often lack security awareness, such as changing default passwords or updating firmware, necessitating manufacturer education and user-friendly security controls.

# Industrial Control Systems (ICS) / Supervisory Control and Data Acquisition (SCADA)

- SCADA systems are advanced Industrial Control Systems (ICS) that monitor, manage, and control industrial processes across multiple production stages. These systems ensure seamless coordination, from raw material handling to product assembly and quality control. While highly efficient, SCADA systems share vulnerabilities with the underlying software used in client computers.

**SCADA System Architecture:** 

## **Plant Level (Level 0)**

- **Components**: Sensors, actuators, motors, pumps, and other industrial devices.
- **Function**: Directly interacts with physical equipment on the factory floor, gathering data and performing actions as instructed by higher-level systems.

## **Controller Level (Level 1)**

- **Components**: Programmable Logic Controllers (PLCs).
- **Function**: Processes data from sensors and sends commands to control devices like actuators, ensuring efficient and safe plant operations

## **Coordinating Computer Level (Level 2)**

- **Components**: Supervisory computers and Human-Machine Interface (HMI) systems.
- **Function**: Provides operators with a centralized view of plant operations, enables adjustments, and manages alarms and events.

## **Program Logic Controller Level (Level 3)**

- **Components**: Advanced software systems.
- **Function**: Manages the overall production process, coordinates production lines, schedules tasks, and logs data for reporting and analysis.

**Applications and Vulnerabilities**

## Energy

 Used for creating electricity and used by oil and gas refineries.

## Facilities

Used for building management to control the
temperature by using an HVAC system.

## **Manufacturing**

 Assembly of complex products like computers, integrating components sourced from multiple locations.

## **Logistics**

- Coordinating production and delivery of bulk orders (e.g., desktops with peripherals).

## **Industrial Processes**

 Transforming raw materials into finished products, such as steel or clean water.

# Real-Time Operating System (RTOS)

- **Overview**: An RTOS is a specialized operating system designed for applications where timing is critical. Unlike general-purpose operating systems (like Windows or Linux), which prioritize tasks based on priority levels, an RTOS ensures that high-priority tasks are completed within a specific time frame. This makes RTOS ideal for systems where timing and precision are essential.

One of the key use cases of an RTOS is in flight control systems. In these systems, the RTOS is responsible for:

- **Managing Real-Time Tasks**: Ensures coordination and execution of multiple tasks with extreme precision.
- **Navigation Systems**: Controls and adjusts the aircraft’s navigation to ensure safe and accurate travel.
- **Engine Controls**: Manages engine parameters to ensure the aircraft operates efficiently and safely.
- **Flight Parameters Monitoring**: Continuously monitors altitude, speed, and attitude to maintain safe flight conditions.
- **Safety Systems**: Oversees responsive systems like collision avoidance to enhance passenger safety.

# Embedded

- **Overview**: Embedded systems are specialized computing systems designed to perform specific tasks within a larger system or product. These systems are often tailored to meet the needs of their environment, focusing on efficiency, reliability, and real-time performance.

**vehicle**

- **Engine Control Units (ECUs)**: These units manage fuel injection, ignition timing, and emissions, optimizing engine performance.
- **Anti-lock Braking Systems (ABS)**: Ensure safe braking by preventing wheel lock-up during sudden stops.
- **Airbag Deployment Systems**: Enhance safety by deploying airbags in response to a collision.
- **Autonomous Vehicles**: As the automotive industry moves toward self-driving cars, embedded systems will drive navigation, decision-making, and safety protocols.

**Smart Home Ecosystem**

- **Smart Thermostats**: Adjust temperature settings based on user preferences and environmental conditions, improving energy efficiency.
- **Smart Locks, Cameras, and Lighting**: Provide enhanced home security by enabling remote control and automation.
- **Microwaves and Refrigerators**: Employ embedded systems to optimize energy usage and streamline operation.

# High Availability (HA)

**Overview**:

High Availability (HA) refers to a system's ability to remain operational and accessible despite hardware failures, software issues, or other disruptions. In cloud computing, it ensures that applications and data remain accessible without interruption, regardless of the circumstances.

# **Key Infrastructure Considerations!!!!**

## **Availability**

- Data must be accessible at all times. This can be achieved by building additional data centers or storing data in the cloud using geographically dispersed regions. Failing to ensure availability can lead to business downtime and result in financial and reputational damage.

## **Resilience**

- Resilience refers to the time it takes for the organization to recover from a critical failure. Tools like load balancers improve web server resilience by distributing traffic, while automated recovery systems (such as data stored in geographically dispersed regions) enable immediate recovery. The cloud’s data storage and backup capabilities ensure high resiliency.

## **Cost**

- In evaluating infrastructure investment, consider not just the upfront purchase cost, but the total cost of ownership, maintenance, and third-party service-level agreements (SLAs). Cloud computing provides cost-effectiveness through a pay-as-you-go pricing model.

## **Responsiveness**

- Responsiveness ensures fast and efficient interactions, improving user satisfaction. This can be achieved using load balancers for quick web access, auto-scaling to adjust resources as needed, or edge computing, which places data closer to clients to reduce latency and enhance performance.

## **Scalability**

- Scalability allows the cloud to increase resources as needed. For example, a toy manufacturer may need to scale up resources and staff for increased demand during the holiday season but scale down afterward.

## **Ease of Deployment**

- Cloud infrastructure benefits from automation tools like Infrastructure as Code (IaC), Virtual Desktop Infrastructure (VDI), and machine templates, enabling seamless deployment of virtual machines or containerized applications.

## **Risk Transference**

- SLAs represent risk transference, where the responsibility for certain risks is transferred to a third party. For instance, an SLA may guarantee that a service provider will fix a failing SQL database within a set timeframe, thereby shifting the risk from the customer to the service provider

## **Ease of Recovery**

- Cloud Service Providers (CSPs) use geographically distributed regions that hold multiple copies of data to ensure redundancy. If one data center fails, other copies ensure continued data availability. CSPs also perform regular backups, including virtual machine backups, simplifying recovery and ensuring business continuity.

## **Patch Availability**

- CSPs must keep up-to-date with patches to ensure that systems are secure. Tools like Microsoft Intune, a cloud-based endpoint management solution, provide patch management for Windows devices, including those outside the corporate network. However, patches should be tested in a sandbox environment to ensure compatibility with critical business applications.

## **Inability to Patch**

- Some critical applications hosted in the cloud may be managed by the customer. In such cases, the CSP might be contractually prohibited from applying patches due to the potential impact on the application.

## **Power**

- CSPs must ensure they can meet the energy demands of their systems and workloads. Using an Uninterruptible Power Supply (UPS) guarantees that, in case of power failure, servers can be shut down properly to avoid data corruption. A Managed Power Distribution Unit (PDU) allows efficient power distribution, remote monitoring, and power usage alerts. Onsite power generators can also be maintained for use during power outages.

## **Compute**

- Cloud compute capabilities enable CSPs to offer additional resources on-demand. This is especially beneficial for serverless architectures, where resources can be dynamically allocated as needed to meet demand.