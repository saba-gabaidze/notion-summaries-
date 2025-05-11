# &4.6  Given a scenario, implement and
maintain identity and access
management

# **Provisioning User Accounts**

Creation, management, and assignment of access rights based on job roles.

### **Create User Identities**

1.  Unique identifiers (e.g., username).

### **Assign Privileges**

1.  Define user access to resources.

### **Allocate Resources**

1.  Provide necessary tools and access for the role.

## **!!!!!!!Active Directory (AD)!!!!!!**

Centralized identity management and authentication in Microsoft environments.

## **{LDAP**

- Protocol used to manage directory objects.

## **X.500 Format**

- Storage format for directory objects, including DC, OU, and CN.

## **Distinguished Name (DN)**

- Full path identifier for objects.

## **Active Directory Structure**

### **DC (Domain Component)**

- Domain identifiers.

### **OU (Organizational Unit)**

- Groups related objects.

### **CN (Common Name)**

- Represents specific objects (users, computers).
- Example: `CN=Computer1, OU=Sales, DC=DomainA, DC=com`.

## **Kerberos Authentication**

### **Updated Sequence Number (USN)**

- A number assigned to Active Directory objects to maintain replication consistency.

### **Timestamp**

- Time when the object was created or last modified.

### **TGT (Ticket Granting Ticket)**

- [ ]  Issued for the user upon successful authentication and used to access other network resources.

## **ADSI Edit Tool}**

- **Purpose**: Tool to view and manage AD objects, edit attributes, and view structure.

![image.png](&4%206%20Given%20a%20scenario,%20implement%20and%20maintain%20iden%2018a9c4fd261480f18d99e15a1b7ddb1c/image.png)

## **New User Accounts**

### **Background Check & Identity Verification**

- required before account creation.

### **Authentication Methods**

- Username/password, smart card, or biometrics.

### **Access Levels**

- Based on job role (e.g., time-based restrictions).

### **Temporary Accounts**

- Expiry function disables access after a set date.

## **Kerberos**

### **Ticket Granting Ticket (TGT) Session**

- User sends credentials to **domain controller (KDC)**.
- KDC verifies identity and issues a **TGT (valid for 10 hours)**.
- TGT is used to request **service tickets** for resource access.

### **Mutual Authentication & SSO**:

- Once authenticated, users **do not need to log in again** for other services.
- Users exchange **service tickets** with resources for **mutual authentication**.

### **Time Synchronization Requirement**:

- All devices must be **within 5 minutes** of the domain controller’s clock.
- **Network Time Protocol (NTP) server** ensures time accuracy.

### **Security Benefits**

- **No password transmission** over the network.
- **Prevents pass-the-hash attacks** (unlike NTLM).
- **Encrypted tickets** prevent replay attacks.
- **NTLM vs. Kerberos**:
    - NTLM stores **MD4 password hashes** (vulnerable to attacks).
    - Kerberos stores **credentials securely in Active Directory (ntds.dit)**.
    - **Kerberos is the modern industry standard**; NTLM is outdated

## **Linux User Account Management**

### **User Account Creation:**

- `useradd <username>` → Creates a new user.
- `passwd <username>` → Sets the password.

### **User Information Storage:**

- `/etc/passwd` → Stores basic user info (username, UID, home directory, shell).
- `/etc/shadow` → Stores encrypted passwords (accessible only by root).

### **Security Best Practices:**

- Use **strong passwords**.
- Restrict access to `/etc/shadow`.
- Regularly **audit and remove inactive users**.

# **Deprovisioning User Accounts**

- **Definition**: Disabling or removing access to a user’s account when they no longer need access.
- **Purpose**: Secures data by blocking access to sensitive resources.
- **Procedure**:
    1. **Disable the account** to prevent login.
    2. **Reset the password** to block previous access.
    3. **Keep the account** for possible future access to data (e.g., emails).
- **Avoid Account Deletion**: Retain the account for reference or data recovery needs

# Permission assignments and
implications

Grants users specific rights and privileges based on their role.

## **Principle of Least Privilege (PoLP)**

- Users receive only the minimum permissions needed to perform their tasks.

## **Group-Based Access Control**

- Users are assigned to groups (e.g., IT, Sales) with shared permissions instead of assigning permissions individually.

## **Context-Aware Authentication**

### **Location** (IP geolocation, GPS)

### **Time** (non-standard login hours)

### **Device** (type, operating system)

### **Network** (corporate vs. public Wi-Fi)

### **Biometrics** (fingerprints, typing patterns)

## **Suspicious Login Practices**

### **Impossible Time Travel**

- Account logs in from two distant locations in an unrealistic time frame.

### **Risky Logins**

- Unusual device access triggers security alerts (e.g., logging into Dropbox from a new device).

# **Identity Proofing**

- **Definition**: The process of verifying a person’s identity to confirm authenticity and legitimacy.
- **Methods of Identity Proofing**:
    - **Government-issued documents** (passport, driver’s license, SSN)
    - **Biometric verification** (fingerprints, facial recognition)
    - **Knowledge-based authentication** (security questions, past addresses)
    - **Two-factor authentication (2FA)** (one-time passcodes, smart cards)
- **Role in Security**: A crucial step in the identity and access management (IAM) lifecycle to prevent unauthorized access.

# **Federation**

 enables identity sharing across organizations for authentication without merging IT infrastructures.

- **Used in** joint ventures and cloud authentication.

## **Authentication process**

### Users authenticate with unique attributes (email, employee ID, password).

### **SAML** protocol facilitates authentication.

### **Identity Provider (IdP)** validates credentials.

### **Service Provider (SP)** grants access after validation.

### A **cookie** enables seamless access to other services.

## **Types**

- **RADIUS Federation**: Wireless-based federation.
- **Shibboleth**: Open-source federation service.

# **Single Sign-On (SSO)**

allows users to access multiple applications with one set of credentials.

## Reduced login fatigue.

## Increased productivity and user experience.

## Centralized management for administrators.

## Single point of failure—compromise of SSO credentials grants access to all linked services.

---

## **Kerberos Authentication**

### **Key Distribution Center (KDC)**

- Includes Authentication Server (AS) and Ticket Granting Server (TGS).

### **Ticket Granting Ticket (TGT)**

- Issued after initial login, used to request Service Tickets. **Service Tickets**
- Grant access to specific services without re-authentication.

### Strong encryption for credential security.

## **Open Authorization (OAuth)**

Delegates limited access to resources without sharing passwords.

### **Authorization Server**

- **Authorization Server**: The OAuth provider (e.g., Google, Facebook) serves as the authorization server, which grants access tokens to users.

### **Access Token**

- Allows third-party services to access specific data on behalf of the user.

### **Delegation**

- Authenticate once, use a token for further access.
- **OAuth + OpenID Connect (OIDC):** OAuth handles authorization; OIDC handles authentication.

## **Security Assertion Markup Language (SAML)**

XML-based protocol for authentication and authorization data exchange, often used in SSO.

### **Identity Provider (IdP)**

- Authenticates users and issues SAML assertions.

### **Service Provider (SP)**

- Receives the SAML assertion and grants access.

### **SAML Assertion**

- Token containing credentials, attributes, and permissions.
- **Advantages:**
    - Secure, scalable authentication (SSO).
    - Federated Identity Management across domains.
    - Reduced password management and breaches.

# **Interoperability**

The ability of different platforms, systems, or technologies to work together or exchange information effectively.

- **Challenges**:
    
    ## Not all systems are interoperable (e.g., OAuth vs. Kerberos).
    
    ## Requires standardized protocols for seamless communication.
    
- Used to ensure compatibility between systems (e.g., HTTP/HTTPS, LDAP).
- Cloud networks often adopt frameworks to facilitate interoperability.

# **Attestation**

 Verification of attributes, conditions, or credentials of an entity by a trusted authority.

## **Certificates**

- Issued by **Certificate Authorities (CAs)** to confirm legitimacy and enable **secure encrypted communication**.

## **Tokens (OAuth)**

- Secure authentication method using **time-limited access tokens** instead of passwords.

## **Federation**

- Establishes **cross-domain trust** for **SSO** and resource sharing between organizations (e.g., **SAML, OAuth**).

## **Active Directory (AD)**

- Manages **user authentication, security policies, and access control** in Windows environments.

# !!!!!!Access Controls!!!!!

# **Mandatory Access Control (MAC)**

### **Strictest access control model** used in **high-security environments** (e.g., government, military).

### **Data classification levels**

- Top Secret, Secret, Confidential, Restricted.
- **User clearance levels** must match or exceed data classification.
- **Access decisions controlled by a central authority**—users **cannot change permissions**.

### **Data Owner**

- **Role:** Creates and classifies data.
- Sets policies for data access and handling.

---

### **Data Steward**

- **Role:** Ensures data accuracy, consistency, and reliability.
- Defines data quality standards.
- Establishes data governance policies.
- Provides guidance on data usage and best practices.

---

### **Data Custodian**

Manages technical aspects of data security and storage.

- Manages data storage, encryption, and backups.
- Implements data access controls.

---

### **Security Administrator**

- **Role:** Enforces security policies and manages access controls.
- Implements authentication mechanisms (e.g., MFA).
- Monitors and audits data access.
- Detects and responds to security threats.

## **Role-Based Access Control (RBAC)**

### Access is granted according to the specific roles within a department or organization.

- Only authorized personnel (e.g., finance department) can perform sensitive tasks, like signing checks.

## **Attribute-Based Access Control (ABAC)**

- Restricts access based on user attributes (e.g., job title, department), resource attributes (e.g., sensitivity level), and environment attributes (e.g., time of day, location).
- **Granular Control**: Provides fine-grained access control by considering multiple factors to determine who can access what, when, and under what circumstances.

### **User Attributes**

1.  Job title, department, security clearance, location, access time.

### **Resource Attributes**

1.  Classification, resource type.

### **Environment Attributes**

1. Time of day, device type, geographic location.

- **Job Title**: Software Developer → Match
- **Department**: IT → Match
- **Security Clearance**: Top Secret → Match
- **Location**: On-site → Match
- **Access Time**: 9 AM - 6 PM → Match
- **File Classification**: Restricted → Match
- **File Sensitivity Level**: High → Match

## **Discretionary Access Control (DAC)**

 Owner of the object (file or directory) controls who can access it and what actions they can perform (e.g., read, write, modify).

- **Access Control Lists (ACLs)**: Permissions are assigned using ACLs, specifying user access levels.

### **Owner**

- The person who owns the object and determines access.

### **ACL**

- List of permissions assigned to users (e.g., read, write, modify).

- **Mark**: Full access (read, write, modify).
- **Lisa**: Limited access (read, comment).
- **Client**: Read-only access.

## **Time-of-Day Restrictions**

- **Definition**: Policies that limit access to systems, data, or networks based on time.
- **Purpose**: To reduce the risk of unauthorized access outside of business hours.

## **Least Privilege**

### **Definition**

- Security principle where users are granted only the minimum access necessary to perform their job duties.

### **Purpose**

- To limit unnecessary access to sensitive data and systems, minimizing potential attack surfaces.

# !!!MFA!!!

## **Biometric Authentication**

### **Fingerprint Scanner**

- Used for smartphone access.

### **Retina Scanner**

- Identifies by blood vessel patterns in the retina.

### **Iris Scanner**

- Verifies identity by comparing iris patterns.

### **Voice Recognition**

- Authenticates based on speech patterns.

### **Facial Recognition**

- Analyzes facial features; advanced versions use infrared technology.

### **Vein Pattern Recognition**

- Uses palm blood vessel patterns for authentication.

### **Gait Analysis**

- Identifies by the unique way an individual walks.
- **Error Metrics**
    
    ### **False Acceptance Rate (FAR)**
    
    - Measures the rate of unauthorized access.
    
    ### **False Rejection Rate (FRR)**
    
    - Measures the rate of legitimate users being rejected.
    
    ### **Crossover Error Rate (CER)**
    
    - The point where FAR and FRR are equal; lower CER indicates fewer errors.

## **Hard Authentication**

### Requires physical devices or objects in the user's possession for authentication.

### Tokens or certificates are generated within a trusted cryptomodule and are never transmitted.

### **Smart Cards**

- [ ]  **Size**: Similar to credit card.
- [ ]  **Authentication**: PIN-based, stores cryptographic keys.
- [ ]  **Uses**: Secure access to workstations, financial transactions, government IDs.

### **Key Fobs**

- [ ]  **Types**: OTP-based, NFC/RFID-based.
- [ ]  **Function**: Generates one-time passwords or enables contactless authentication.
- [ ]  **Uses**: Physical access, VPNs, online banking.

### **Security Keys**

- [ ]  **Highly Resistant to Phishing**: Provides protection beyond passwords or PINs.
- [ ]  **YubiKey**: Example of a security key, FIPS 140-2 validated, NIST-800-63-3 compliant.
- [ ]  **AAL3**: Highest assurance level, used for high-security applications (e.g., finance departments).

## **SSH Keys**

- A secure, passwordless authentication method using a pair of cryptographic keys.
    - **Private Key**: Stored securely on the admin’s device.
    - **Public Key**: Stored on the server for authentication.
- [ ]  **Benefits**: More secure than passwords, enables passwordless login.
- [ ]  **Key Generation**: Use `ssh-keygen -t rsa -b 4096` to create the key pair.
- [ ]  **Copy Public Key to Server**: Use `ssh-copy-id username@<servername>` to add the public key to the server’s authorized keys.
- **Test Authentication**: Login via `ssh username@<servername>` to verify passwordless access.
- **Admin Access**: Admins can use `ssh root@<server>` for remote root access

# **Soft Authentication**

- **Definition**: Software-based authentication relying on something the user knows or is inherent to them (e.g., passwords, PINs, biometrics).
- **Characteristics**:
    - Intangible: Data can be transmitted or captured digitally.
    - Convenient: No need for physical devices.
    - Vulnerable: Susceptible to phishing, keylogging, and data interception.

### **One-Time Password (OTP)**

- Temporary, short-lived passwords sent to the user (via SMS, email, or authenticator app).
- Expiry: 10-15 minutes (or 30-60 seconds).
- **Use**: Online banking, e-commerce, VPN logins.

### **2. Biometric Authentication**

- **Based on**: Physical traits (fingerprints, facial recognition, retina scans).

### **3. Knowledge-Based Authentication (KBA)**

- **Based on**: User’s knowledge (answers to security questions, PINs).
- [ ]  Static: Pre-set answers (e.g., mother’s maiden name).
- [ ]  Dynamic: User-specific questions (e.g., recent transactions).

## **Factors of Authentication**

### **Something You Know**: Knowledge-based info (e.g., username, password, PIN).

### **Something You Have**: Physical objects (e.g., tokens, smart cards, key fobs).

### **Something You Are**: Biometric data (e.g., fingerprints, retina scans, voice).

### **Something You Do**: Behavioral actions (e.g., keystroke dynamics, gait analysis).

### **Somewhere You Are**: Location-based (e.g., GPS, IP address).

---

**Types of Authentication**

### **Single Factor Authentication (SFA)**: Uses only one factor (e.g., password).

### **Two-Factor Authentication (2FA)**: Combines two factors from different categories (e.g., password + token).

### **Multi-Factor Authentication (MFA)**: Combines three or more factors (e.g., smart card + PIN + reader action).

---

## **Tokens**

Cryptographic utilities used to securely store and transmit confidential data for authentication and authorization.

### **RSA SecurID**

- **Type**: Hardware token
- **Function**: Generates a time-sensitive code for authentication, providing secure two-factor authentication.

### **Google Authenticator**

- **Type**: Software token
- **Function**: Generates dynamic, time-based codes as secondary authentication.

# Password Concepts

## Password best practices

### **Length**

- Longer passwords (12–16+ characters) are more secure.

### **Complexity**

- Use at least three of the following: lowercase, uppercase, numbers, special characters.

### **Reuse**

Password reuse policies prevent using old passwords across different accounts to They stop people from recycling passwords that might have been compromised.

### **Password Age**

- [ ]  **Minimum password age**
- Prevents frequent changes to bypass history.
- [ ]  **Maximum password age**
- Ensures passwords are updated periodically.

### **National Institute of Standards and Technology(NIST) Best Practices**

- Use **passphrases** (long, easy-to-remember sentences) instead of short complex passwords.
- **No forced periodic password changes** unless compromised.
- Allow **password managers and copy-pasting** for better security.
- Check new passwords against **breached databases**.

### **Account Lockout Policy**

- **Failed attempts threshold:** 3–5 incorrect attempts before lockout.

## Password Managers

### Software apps for storing and recalling passwords securely.

### **Password Vault**

- Stores all account passwords for easy access.

### **Cloud-Based**

- Accessible from any device, even away from home.

### **Master Password**

- Controls access to the password manager, usually randomly generated

## **Passwordless Authentication**

- Eliminates traditional passwords for enhanced security.

### **Authentication Methods**

- Uses biometrics, smart cards, SSH keys, and security keys.
- **Examples**: Touch ID, Face ID, smart cards, SSH keys with certificates.

# **Privileged Access Management (PAM)**

## Restricts and protects admin, privileged, service, and root accounts.

## **Ephemeral Credentials**

- Single-use, admin access for specific task

## **Temporary Admin Rights**

- Users get limited admin access via a **Kerberos ticket**, which expires after use.

## **Bastion Forest**

- Secure area where admin accounts are stored, separated from regular user accounts.

## **Identity Manager (IM)**

- Confirms user identity, enforces MFA, and grants admin access based on authorization.

## **Tracking & Auditing**

- PAM logs all privileged access and actions for security monitoring.

## **PAM Tools**

### **Just-in-Time (JIT) Permissions**

- Temporary privilege elevation granted **only when needed**, auto-revoked after use.
- Reduces long-term access risks and limits attack exposure.
- Access approved via workflow, logged for auditing.

### **Password Vaulting**

- Stores privileged credentials in a **secure vault**, removing them from Active Directory.
- Access granted only when authorized; passwords can be auto-injected without user visibility.
- Supports **session recording** and **password rotation** for security.

### **Ephemeral Credentials**

- **One-time-use credentials** that expire after a short period.
- Eliminates long-term credential exposure and prevents reuse.
- Ideal for temporary cloud, API, or admin access.