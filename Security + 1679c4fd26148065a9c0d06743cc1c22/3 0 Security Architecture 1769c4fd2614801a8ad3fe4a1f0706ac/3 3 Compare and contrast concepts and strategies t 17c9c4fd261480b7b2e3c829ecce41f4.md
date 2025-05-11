# 3.3 Compare and contrast concepts and strategies to protect data.

# Data types!!!

**Data Types and Regulations**

1. **Regulated Data:** Data subject to specific laws and regulations.

## **Personally Identifiable Information (PII)**

 Unique data about a person (e.g., SSN, biometric data, email).

## **Protected Health Information (PHI)**

 Health data (e.g., medical history, test results).

## **Financial Data**

 Bank account details, credit card info, transaction records.

## **Legal Data**

Data regarding legal proceedings (e.g., court cases).

## **Intellectual Property (IP)**

 Trade secrets, patents, and copyrighted material protected by IP laws.

## **Consumer Data**

 Purchase histories, preferences, and online behavior regulated by privacy laws.

## **Government Data**

 Highly regulated data for internal or authorized external use, with strict disposal rules.

## **Trade Secrets**

 Confidential business information requiring legal (NDAs) and technical protections.

## **Customer Data**

Sensitive data about customers, critical for business trust and regulated by privacy laws.

## **Proprietary Data**

Company-specific data like research or product development.

## **Biometric Data**

 Fingerprints, facial recognition, and similar data types.

**Data Classifications:!!!!**

## **Human-readable Data**

- Text, images, and audio. Secured via encryption.

## **Non-human-readable Data**

- Binary, machine language, and encrypted data. Protected using cryptography and secure key management.

regulations:

1. **GDPR (EU):** Guards personal data rights and privacy.
2. **HIPAA (US):** Secures health information privacy.
3. **CCPA (California):** Empowers consumer data rights.
4. **SOX (US):** Ensures financial transparency for public companies.
5. **GLBA (US):** Imposes privacy/security rules on financial institutions.
6. **Data Protection Act (UK):** Regulates personal data handling and privacy.

# Data Classifications

## **Sensitive Data**

- Privileged information that could cause harm if exposed.
- Includes personal, financial, or confidential details requiring strong protection.

## **Confidential Data**

- Includes R&D and legal data, protected by laws like attorney-client privilege.
- Disclosure could harm the organization, and access requires special authorization.

## **Public Data**

- Freely available information, such as news or brochures, with no access restrictions.

## **Private Data**

- Personal data individuals want to keep undisclosed.
- Exposure could result in critical damage and is confined to trusted parties.

## **Restricted Data**

- Data with strict limitations on access, use, or distribution.
- Includes legally or policy-restricted information requiring heightened security.

## **Critical Data**

- Essential for operations, such as backups or encryption keys.
- Loss or corruption could lead to operational failure and requires encryption for security.

## Governmental vs. Non-Governmental Classifications

- **Governmental:**
    - Top Secret → Secret → Confidential → Unclassified
- **Non-Governmental:**
    - Confidential/Proprietary → Private → Sensitive → Public
- Higher classifications correspond to greater potential damage from data breaches.

# General Data Considerations

## **Data States**

### **Data at Rest**

- Data stored on devices or servers, not actively in use. It is static but vulnerable to breaches if unprotected.

### **Data in Transit**

Data being transmitted across networks or communication channels. Protected by encryption protocols like TLS, SSL, or HTTPS.

### **Data in Use**

 Data actively processed in memory (RAM). It is volatile and erased when the system shuts down or crashes (e.g., BSOD).

## **Data Sovereignty**

- Data is subject to the laws of the region where it was created. It cannot be moved across regions, even for backups, impacting cloud providers and multinational companies.

## **Geolocation**

- Identifies the physical origin of a data request or user authentication, helping verify access legitimacy. Essential for online banking, two-factor authentication, and remote access.

# Methods to Secure Data

## **Geographic Restrictions**

- Limits data access based on geographic location. Useful for complying with regional regulations but may challenge remote work and global teams.

## **Encryption**

- Converts readable data (plaintext) into unreadable data (ciphertext), protected by a decryption key. This is a fundamental defense against unauthorized access.

## **Hashing**

- Converts data into a fixed-length string that can't be reverse-engineered. Used for data integrity, especially in storing passwords and verifying file consistency. Common algorithms include MD5, SHA-1, SHA-256, SHA-512, and SHA-3.

## **Masking**

- Hides sensitive data by replacing it with fake or anonymized data while maintaining the original format. Used for protecting details like social security numbers.

## **Tokenization**

- Replaces sensitive data with a randomly generated token, while securely storing the actual data in a protected vault. Common in payment processing systems.

## **Obfuscation**

- Makes data or source code harder to understand or steal by adding complexity. Techniques include XOR and ROT13:
- **XOR:** Logical operation that compares two binary values and outputs based on specific rules.
- **ROT13:** A cipher that rotates letters by 13 places in the alphabet.

## **Segmentation**

- Divides a network or system into isolated segments to limit lateral movement in case of a breach.

## **Permission Restrictions**

- Controls access and modification of data based on user roles, ensuring only authorized personnel can interact with sensitive information.