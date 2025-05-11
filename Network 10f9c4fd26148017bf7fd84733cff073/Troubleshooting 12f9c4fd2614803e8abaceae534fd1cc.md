# Troubleshooting

**Troubleshooting Tools**

- **Purpose of Tools**: Used to gather information and repair network issues, both software (like **ping** and **tracert**) and hardware tools (like **cable testers** and **crimpers**).
- **Safety First**: Always consider **data safety** before troubleshooting. Ask if the action might harm your data.
- **Tools to Buy?**: Buying tools depends on your job’s needs—different roles require different tools.
- **Software Tools**: Most network problems in established networks can be fixed using **OS-provided tools**; for example, **ping** is often enough.

# Hardware Tools

## **Cable Testers, TDRs, and OTDRs**

- **Cable Issues**: Common problems include **open circuits** (wires don’t connect end-to-end), **short circuits** (wires connect to each other inappropriately), **wire map problems** (wires connected incorrectly to jack or plug), **crosstalk** (signal interference between wire pairs), **noise** (unwanted signals from faulty connections), and **impedance mismatch** (uneven resistance causing signal echo).
- **Cable Testers**: Detect **continuity issues** and **wire map errors**.

![image.png](Troubleshooting%2012f9c4fd2614803e8abaceae534fd1cc/image.png)

- **TDRs and OTDRs**: Identify **cable break location**; TDRs are for **copper cables** and OTDRs for **fiber optics**.
- **Exam Tip**: Know **open/short circuits** terms for CompTIA Network+ exam, which refer to **open circuits** and **short circuits** respectively.

![image.png](Troubleshooting%2012f9c4fd2614803e8abaceae534fd1cc/image%201.png)

## **Certifier**

is a **hardware device** used for testing the quality and performance of network cables. It verifies that the cable meets specific standards and can handle the intended data capacity, particularly useful during network installation or troubleshooting for performance issues.

## **Light Meter**

- **Purpose**: Measures **light loss** in fiber-optic cables caused by impurities, dust, poor connections, or light leakage.
- **Components**: Uses a **high-powered light source** at one end and a **calibrated detector** at the other to detect the light reaching the detector.
- **Exam Tip**: Known as **light meter**, **optical power meter**, or **power meter**; all terms may appear on the CompTIA Network+ exam.

## **Voltage Quality Recorder/Temperature Monitor**

- **Importance**: Proper **temperature** and **power** are crucial for network stability; issues often lead to **intermittent problems**.
- **Monitoring**: Use these devices to track **temperature** and **voltage quality** in server rooms over time.
- **Symptoms to Watch For**: High temperatures during certain times or equipment failures coinciding with air conditioning changes.
- **Usefulness**: Ideal for diagnosing problems that might occur unexpectedly, like **"something happened last night."**

## **Cable Strippers/Snips**

![image.png](Troubleshooting%2012f9c4fd2614803e8abaceae534fd1cc/image%202.png)

- **Purpose**: Used to make **UTP cables**; essential for stripping insulation from wires.
- **Complementary Tool**: Often used alongside a **crimping tool** (crimper) for proper cable assembly.
- **Note**: Not required for punching down **66- or 110-blocks**; a **punchdown tool** is used for that.

## **Multimeters**

- **Function**: Test **voltage** (AC and DC), **resistance**, and **continuity**.
- **Importance**: Essential for assessing voltage on lines and useful for continuity testing when a cable tester isn’t available.
- **Quality Advice**: Avoid **cheap tools**; invest in a reliable multimeter to ensure accurate readings and durability. Higher quality tools perform better and last longer, making your job easier.

## **Tone Probes and Tone Generators**

- **Purpose**: Used together to **locate specific cables**.
- **Function**: The **tone generator** sends a signal through the cable, and the **tone probe** detects that signal, helping you identify the cable’s path or endpoint.
- **Note**: A tone probe is **never used** without a tone generator.

## Punchdown Tools

Punchdown tools (Figure 21-5) put UTP wires into 66- and 110-blocks. The
only time you would use a punchdown tool in a diagnostic environment is a
quick repunch of a connection to make sure all the contacts are properly set.

# Software Tools

## Packet Sniffer/Protocol Analyzer

- **Definition**: A packet sniffer intercepts and logs network packets, allowing network technicians to analyze the data being transmitted across a network.
- **Types**:
    - **Software Sniffers**: Programs that run on computers (e.g., Wireshark).
    - **Hardware Sniffers**: Dedicated devices specifically designed for packet sniffing.
- **Protocol Analyzers**: These tools process the data captured by packet sniffers to interpret the network activity and diagnose issues.
- **Popular Tools**:
    - **Wireshark**: The most well-known graphical user interface (GUI) packet sniffer and protocol analyzer. It provides a visual representation of network traffic and allows for in-depth analysis of packets.
    ![Wireshark in action](Figure 21-6)
- **Command-Line Alternative**:
    - **tcpdump**: A command-line tool that works when a GUI tool like Wireshark isn’t available (e.g., on a server without a GUI). Tcpdump allows users to monitor and filter packets in the terminal and can create files that can be opened in Wireshark for later analysis. It is typically pre-installed on most UNIX/Linux systems.

Exam tip

Be familiar with both Wireshark and tcpdump, as you might encounter scenarios where one is more suitable than the other during the CompTIA Network+ exam.

## Port Scanners

- **Definition**: A port scanner is a program that probes the ports on another system to log the state of those ports. It helps identify whether ports are open, closed, or filtered, which can indicate potential vulnerabilities in a system.
- **Usage**:
    - **Network Administrators**: Used to discover unintended open ports that could expose a system to security threats.
    - **Hackers**: Often utilized to find vulnerabilities in systems for malicious purposes.
- **Popular Tools**:
    - **Nmap**:
        - Considered the most well-known and powerful port scanner.
        - Originally designed for UNIX systems but has been ported to work on Windows and other operating systems.
        - Highly versatile, offering a wide range of features for network discovery and security auditing.
    - **Angry IP Scanner**:
        - A user-friendly alternative primarily for Windows users.
        - Simple and effective for quickly scanning IP addresses and ports.
        ![Angry IP Scanner](Figure 21-7)

Key Considerations

- Understanding the implications of using port scanners is crucial for both network security management and ethical considerations. Always ensure that you have permission to scan a network or system to avoid legal issues or potential conflicts.

## Looking Glass Sites

- **Definition**: Looking glass sites are remote servers that provide a web-based interface for performing network diagnostic tests such as ping and traceroute from locations outside of the local environment. They are useful for analyzing network connectivity issues from different geographic points.
- **Features**:
    - **Diagnostic Tools**: Common tools available include:
        - **Ping**: Measures the round-trip time for packets sent to a target host.
        - **Traceroute**: Shows the path packets take to reach the target, identifying each hop along the way.
        - **BGP Query Tools**: Allows users to query Border Gateway Protocol (BGP) information, helping diagnose routing issues.
    - **Geographic Flexibility**: Users can select the origin of the diagnostic process from a list of locations, allowing for a broader perspective on network performance.
    - **IP Version Testing**: Some sites offer options to test both IPv4 and IPv6 addresses.
- **Usage**:
    - **Network Troubleshooting**: Helpful for diagnosing connectivity issues that may not be visible from within a local network.
    - **Performance Analysis**: Useful for understanding how the network performs from different geographic regions.

### Intrusion Detection Software (IDS)

- **What It Is**: IDS is a security tool that monitors your network or computer systems for suspicious activities and potential security breaches.
- **How It Works**:
    - It analyzes network traffic and system logs.
    - If it detects anything unusual or harmful (like an attack or unauthorized access), it alerts the system administrator or user.
- **Purpose**: The main goal is to **detect** and **alert** about potential security issues, allowing you to take action before any damage occurs.
- **Example**: Think of it like a security alarm that goes off when someone tries to break into your house.

### Intrusion Prevention Software (IPS)

- **What It Is**: IPS is a security tool that not only detects suspicious activities like IDS but also takes action to **prevent** them from happening.
- **How It Works**:
    - It monitors network traffic and can automatically block harmful traffic or attacks in real-time.
    - When it identifies a threat, it can drop malicious packets, block offending IP addresses, or adjust firewall rules.
- **Purpose**: The main goal is to **prevent** attacks and unauthorized access to systems, stopping threats before they can cause harm.
- **Example**: It’s like a security guard who not only calls the police when they see a break-in but also physically stops the intruder from getting inside.

# The Troubleshooting Process

**Troubleshooting** is a dynamic process that involves quick judgments to resolve network issues. It's impractical to cover every possible scenario, so focus on **basic rules** before acting:

1. **"First, do no harm."** Avoid making the problem worse.
    - **"First, do not trash the data!"** Protect irreplaceable data at all costs.
2. **"Always make good backups!"** Data recovery can be costly or impossible without backups.

**Simplified Steps in the Troubleshooting Process:**

1. **Identify the problem.**
    - **Gather information.**
    - **Duplicate the problem**, if possible.
    - **Question users.**
    - **Identify symptoms.**
    - **Determine if anything has changed.**
    - **Approach multiple problems individually.**
2. **Establish a theory of probable cause.**
    - **Question the obvious.**
    - **Consider multiple approaches:**
        - **Top-to-bottom/bottom-to-top OSI model.**
        - **Divide and conquer.**
3. **Test the theory to determine the cause.**
    - If the theory is confirmed, determine the next steps.
    - If not, reestablish a new theory or escalate.
4. **Establish a plan of action** to resolve the problem and identify potential effects.
5. **Implement the solution** or escalate as necessary.
6. **Verify full system functionality** and implement preventative measures if applicable.
7. **Document findings, actions, and outcomes.**

## **1)Identify the Problem**

**Identify the Problem**

**Understanding the true problem** is crucial rather than relying solely on user reports. For instance, if a user can't access the Internet, it might be an isolated issue or part of a larger network failure.

**Key Steps:**

1. **Gather Information:**
    - Observe symptoms directly if possible.
    - If troubleshooting over the phone, ask both closed-ended (yes/no) and open-ended questions to gather details.
2. **Duplicate the Problem:**
    - Try to replicate the issue on the user’s machine and from other machines to determine if it’s a user-specific problem or network-wide.
3. **Question Users:**
    - Adjust your questions based on the user’s technical knowledge.
    - Understand the extent of the problem: Is it isolated or widespread?
4. **Determine If Anything Has Changed:**
    - Ask questions like:
        - “What exactly was happening when the problem occurred?”
        - “Has anything changed on the system recently?”
    - Avoid placing blame to keep the conversation constructive.
5. **Isolate the Problem:**
    - Check for recent changes, software updates, or technician visits to the affected system.
    - Maintain up-to-date documentation for effective troubleshooting.
6. **Approach Multiple Problems Individually:**
    - In complex scenarios, break down issues and tackle them one at a time to identify root causes.

## 2)**Establish a theory of probable cause**

**Develop a theory** about the cause of the problem once you’ve identified it. Remember, a theory is not a fact and may need to be revised later in the troubleshooting process. Your theory should be based on experience and the use of available support tools.

**Key Points:**

1. **Select the Most Probable Cause:**
    - Aim to choose a solution that addresses the problem on the first attempt, avoiding unnecessary trial and error.
2. **Question the Obvious:**
    - Always check basic functionalities (e.g., ensuring a printer is plugged in and turned on).
3. **Consider Multiple Approaches:**
    - Use the OSI model for troubleshooting:
        - **Top-to-Bottom Approach:** Start from the application layer and move down.
        - **Bottom-to-Top Approach:** Begin from the physical layer and move up.
4. **Divide and Conquer Method:**
    - This strategy balances the two OSI approaches.
    - It allows you to focus on specific layers (e.g., Layers 1 and 2) without wasting time troubleshooting higher layers when the problem may be lower.
5. **Testing Theories at the Appropriate OSI Layer:**
    - Once you identify the likely cause at a particular OSI layer, begin testing your theories related to that layer.
    - If your theory proves incorrect, adjust your approach and test new theories at different layers.

**Example Scenario:**

- If Martha cannot access the database server:
    - Start by checking connectivity using the OSI model, ensuring that the layers involved in the communication are functioning correctly.
    - If problems exist at a lower layer, address them before considering higher-level issues.

## 3)**Test the Theory to Determine Cause**

In this step, you'll test the theory you've established regarding the cause of the issue. However, it's crucial to approach this cautiously without making any changes that could lead to complications.

**Key Steps:**

1. **Verify the Theory Without Making Changes:**
    - If you suspect the cause of an issue (e.g., a printer being turned off), verify it by checking the situation directly without making adjustments.
    - For example, check if the printer is powered on and connected without turning it on or off.
2. **Plan Next Steps:**
    - If your theory is confirmed (e.g., the printer is indeed off), prepare a resolution plan. However, refrain from acting immediately until you're clear on the repercussions.
3. **Reestablish a New Theory if Necessary:**
    - If your initial theory is not confirmed, return to the previous step to formulate a new probable cause based on the information gathered.
    - This may involve additional questioning, observation, or testing to identify alternative causes.
4. **Caution Before Acting:**
    - Exercise caution before taking any action. You might not have the authority to implement a fix, or there may be unforeseen consequences to your actions.
    - For example, if you find a padlocked server room, that indicates you cannot access the device, and there may be important reasons for the printer's status.
5. **Escalate When Needed:**
    - If the situation requires, escalate the issue. This can mean:
        - Informing other parties (e.g., IT management) about the problem for guidance.
        - Passing the issue to another authority who has control over the device or issue.
    - For instance, if there's a server issue that could affect critical operations, contact the relevant department manager (e.g., accounting) to discuss the implications before proceeding.
6. **Iterate as Necessary:**
    - Continue this process of theorizing and testing until you reach a confirmed theory that seems accurate. This might require multiple iterations.

## 4)Establish a Plan of Action and Identify Potential Effects

After formulating your theory regarding the problem, it’s crucial to create a detailed plan of action to resolve the issue effectively. This plan should outline the steps needed to fix the problem while considering potential effects, especially unintended consequences.

**Steps to Establish a Plan of Action:**

1. **Define the Action Steps:**
    - Clearly outline the specific steps you need to take to resolve the issue.
    - For example, if the problem is that a user can't access the database server, your action steps might include:
        - Check network connectivity between the user’s workstation and the database server.
        - Verify that the database server is powered on and operational.
        - Ensure the database service is running on the server.
2. **Document Complex Procedures:**
    - If the problem is complex or requires multiple steps, write down the entire procedure.
    - This documentation will serve as a guide during the troubleshooting process and help ensure you don’t overlook any crucial steps.
3. **Identify Required Resources:**
    - Determine the tools and resources you’ll need to implement the plan.
    - For instance, you might need network diagnostic tools, access to server management interfaces, or replacement hardware.
4. **Assess Potential Effects:**
    - Consider what effects your actions might have on the network and its users. Ask yourself:
        - Will this action cause downtime for other users?
        - Are there dependencies or critical services that could be disrupted?
        - If replacing a router, can you transfer all settings, or will it require a complete reconfiguration?
    - Document these potential effects to prepare for any challenges that may arise during implementation.
5. **Create Contingency Plans:**
    - Identify potential risks and outline contingency plans in case things don’t go as expected.
    - For example, if you plan to remove a switch, have a backup switch ready to minimize downtime.
6. **Communicate with Stakeholders:**
    - Inform affected users or stakeholders about the planned actions and any potential downtime. Clear communication can help manage expectations and reduce frustration.
    - For example, if users will lose access to certain resources while you implement the fix, let them know in advance.
7. **Review and Revise:**
    - Before proceeding, review your plan for any gaps or potential issues. Revise as necessary to ensure a smooth implementation.

**Example Action Plan**

**Problem:** Martha cannot access the database server.

**Action Steps:**

1. Check the user's network connection.
2. Verify the database server's power status.
3. Ensure the database service is running.
4. Test connectivity from another workstation.

**Potential Effects:**

- If the server is down, it may affect multiple users relying on the database.
- Changing network configurations could disrupt other services temporarily.

**Contingency Plans:**

- Have a backup database server available if the primary server is down for an extended period.
- Prepare to rollback changes if a new configuration causes further issues.

## 5)Implement the Solution or Escalate as Necessary

Once you have isolated the cause of the problem and established a solution, it’s time to implement the fix or escalate the issue if it falls outside your expertise or authority. Here’s a guide to help you through this crucial step.

**Steps to Implement the Solution**

1. **Choose the Best Solution:**
    - Determine the most effective fix based on your previous analysis and testing. This could involve:
        - Providing remote assistance to a user.
        - Installing a replacement part.
        - Applying a software patch or configuration change.
2. **Implement One Solution at a Time:**
    - Focus on one solution at a time to maintain clarity on what works and what doesn’t.
    - For example, if you suspect a faulty network cable, replace only that component before moving on to other possibilities.
3. **Document Your Actions:**
    - Keep a detailed record of what you do, including:
        - The specific solution implemented.
        - The date and time of the action.
        - Any observations or outcomes.
    - This documentation helps track progress and provides valuable insights for future troubleshooting.
4. **Test the Solution:**
    - After implementing the solution, thoroughly test to ensure the problem is resolved.
    - Try to recreate the issue to confirm that the fix was effective.
    - If the problem persists, reassess and consider alternative solutions or escalate as necessary.
5. **Educate the User:**
    - If applicable, explain to the user what you did to resolve the issue. This can empower them to troubleshoot minor problems in the future and reduces the likelihood of similar issues recurring.
6. **Escalate if Needed:**
    - If the solution requires expertise beyond your capabilities or falls under another team’s responsibility, escalate the issue.
    - Communicate clearly with the individual or team taking over, providing all relevant information and documentation about the problem and any actions taken.

## 6)Verify Full System Functionality and Implement Preventative Measures

After resolving a problem, it’s crucial to ensure that the entire system is functioning properly and to implement preventative measures to avoid similar issues in the future. Here’s how to go about this process effectively:

**Steps to Verify Full System Functionality**

1. **Check System Components:**
    - Review all components affected by the change to ensure they’re functioning as expected. For instance, if you replaced a network interface card (NIC), verify that the server can still communicate with other devices on the network.
2. **Test the Specific Issue:**
    - In the scenario with Martha, have her attempt to access the database while you are present. Confirm that she can open the database and that it responds correctly. This immediate testing helps identify any lingering issues.
3. **Evaluate Related Systems:**
    - Assess any systems that may be indirectly affected by the changes made. For example, if a user’s MAC address changed due to a NIC replacement, verify that their access rights and network management systems reflect this change.
4. **Monitor for Issues:**
    - Observe the system for a brief period after the fix to catch any unexpected behavior or issues that may arise from the changes made.

**Implementing Preventative Measures**

1. **Educate Users:**
    - Provide guidance to users on how to prevent future problems. In Martha’s case, you could offer tips on maintaining stable connections or handling common issues that may arise with database access.
2. **Install Software and Patches:**
    - If applicable, install software updates, patches, or additional security measures that can help prevent future occurrences of the same issue. Ensure that these updates do not disrupt existing functionalities.
3. **Document Changes:**
    - Keep a record of the changes made, including the rationale behind them, any updates installed, and how to handle similar issues in the future. This documentation can serve as a reference for both you and other team members.
4. **Review Security Settings:**
    - If changes to a user’s security settings were made, ensure that these do not inadvertently restrict access to other resources. Confirm that access controls are correctly configured and that users retain the necessary permissions.
5. **Conduct a System Check:**
    - Perform a general system check to ensure that all services, applications, and hardware components are functioning correctly. This could include testing network connections, verifying application performance, and confirming that no new issues have arisen.
6. **Feedback Loop:**
    - Encourage users to provide feedback about the changes and the resolution process. This can help identify any gaps in understanding or additional issues that may need addressing.

## 7)Document Findings, Actions, and Outcomes

!!!!!!!!!!!!!!!!!!!!!

Snips
Voltage event recorder