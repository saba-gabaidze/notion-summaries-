# 1.4 Explain the importance of using appropriate cryptographic
solutions.

# Public key infrastructure (PKI)

## **Public Key**

Shared openly for encrypting data and validating digital signatures. Used to securely send data (e.g., George encrypts data with Mary’s public key). File format: `.cer` (PKCS7).

## **Private Key**

 Kept secret and used to decrypt data and generate digital signatures. Only the private key can decrypt data encrypted with the corresponding public key. Used to prove data authenticity and prevent repudiation. File format: `.pfx` (PKCS12).

## **Key Escrow**

A trusted third party stores copies of cryptographic keys to ensure key recovery if the owner loses access (e.g., forgotten passphrase, hardware failure). Often stored using **Hardware Security Modules (HSMs)** for secure management and protection.

# Encryption

## **Level :**

## **Full-Disk Encryption (FDE)**

 Encrypts the entire storage device to protect data, often using a Trusted Platform Module (TPM) chip for key storage. Examples include self-encrypting drives (e.g., Opal drives) and software like VeraCrypt.

## **File Encryption**

 Protects individual files. For example, Encrypted File System (EFS) encrypts files with the key stored in the user’s profile

## **Volume Encryption**

BitLocker integrates with TPM to encrypt a system’s volume, securing data even if the storage is moved to another device.

## **Database Encryption**

 Secures sensitive data in databases, such as customer records or financial transactions, against unauthorized access.

## **Record-Level Encryption**

 Encrypts individual records within databases, improving data protection and integrity.

## **Transport Encryption**

Secures data in transit. Protocols like TLS (Transport Layer Security) ensure secure communication, with steps including handshake, encryption, transmission, and decryption.

# Key Encryption

## **Asymmetric Encryption**

 Involves two keys (public and private). The public key encrypts data, and the private key decrypts it. Examples: RSA, Diffie-Hellman, and ECC. It's slower for large data.

## **Symmetric Encryption**

 Uses one key to both encrypt and decrypt data, more efficient for large volumes. Examples: AES (Advanced Encryption Standard), DES (Data Encryption Standard), and 3DES (Triple DES).

## **Key Exchange**

The process of securely sharing cryptographic keys, such as through Diffie-Hellman.

## **Key Length**

Longer keys increase security by making it harder to crack the encryption.

## Algorithms

Encryption relies on algorithms that turn readable text (plaintext) into unreadable text (ciphertext). Algorithms like RSA and AES use complex math to make encryption secure and hard to crack with brute-force attacks.

## **Homomorphic**

 Allows computation on encrypted data without decryption, maintaining confidentiality throughout processing.

# Tools

## **TPM (Trusted Platform Module)**

- Hardware-based security chip.
- Manages cryptographic keys and ensures secure boot processes.
- Offers hardware authentication and encryption support.

## **HSM (Hardware Security Module)**

- Physical device for managing and storing cryptographic keys.
- Performs encryption/decryption in a highly secure environment.
- Used in finance, healthcare, and e-commerce for critical operations.

## **Key Management System (KMS)**

- Software for creating, storing, and managing cryptographic keys.
- Centralized control over key generation, distribution, rotation, and revocation.

## **Secure Enclave**

- Hardware-based feature in modern processors (e.g., Apple’s T2 chip).
- Provides isolated environments for secure operations like storing sensitive data and executing cryptographic tasks.

# **Obfuscation**

This technique makes code, data, or information harder to understand to protect against reverse engineering. It adds complexity to deter malicious actors from exploiting vulnerabilities.

## **Steganography**

Hides secret messages within innocuous files like images or audio to avoid detection. It’s used in covert communication and digital watermarking.

## **Tokenization**

Replaces sensitive data with unique tokens that have no value, reducing the risk of exposing actual data. Common in payment systems and data protection.

## **Data Masking**

Replaces sensitive data with fictitious values while maintaining the structure of the dataset. It’s used in testing environments and to share data securely without compromising privacy. Example: replacing patient info with fake identifiers for research purposes.

# **Hashing**

A one-way function that converts input data into a fixed-size hash value. Hashing ensures data integrity and strengthens password security. Common hashing algorithms include SHA1 and MD5. Hashing is used to verify data hasn't been altered and to protect passwords.

# **Salting**

Adds random data (salt) to passwords before hashing. This prevents attacks like rainbow table and brute-force by introducing unpredictability, making password cracking harder.

# **Digital Signatures**

 Cryptographic tool used to verify the authenticity, integrity, and non-repudiation of a document. The signer uses their private key to create a unique code (signature) tied to the document. The recipient uses the public key to verify it.

# **Key Stretching**

 Technique to make passwords harder to crack by making the hashing process slower. It uses methods like PBKDF2 and Bcrypt to increase computational effort for attackers.

# **Blockchain**

Blockchain is a decentralized digital ledger that originally powered Bitcoin but now extends to various sectors. Data is stored in blocks and distributed across many computers, making it nearly impossible to alter. To change data, you’d need to update every copy on the network, ensuring security.

Beyond cryptocurrencies, blockchain can be used to record financial, medical, and property transactions. Each block contains data and a hash, forming a chain. To add a block, computers solve a puzzle in a process called "proof of work." Once the block is accepted, it becomes part of the chain, ensuring the accuracy of the ledger.

For example, house deeds stored on the blockchain can be traced to verify ownership, providing a reliable and tamper-proof record.

# **Open Public Ledger**

- **Decentralization**: No single entity controls the ledger; it's distributed across multiple nodes in the network.
- **Security**: Difficult to tamper with due to decentralization and cryptographic measures.
- **Transaction Recording**: Transactions are broadcast, verified, and added to the ledger following blockchain rules.
- **Consensus Mechanisms**: Proof of work or proof of stake ensures all participants agree on transaction validity before adding to the ledger.
- **Immutable & Chronological**: Once validated, transactions are permanent and linked in chronological order, making them tamper-proof.
- **Transparency**: Anyone can verify transactions independently, ensuring trust and accountability.

# Certificates

## CA

Certificate Authority ensure secure online interactions by validating digital identities using cryptographic keys. They use root keys to sign certificates, forming a trust chain. There are:

- **Online CAs**: Fast, real-time key verification.
- **Offline CAs**: Isolated for security, away from online threats.
- **Public CAs**: Secure internet-accessible websites.
- **Private CAs**: Secure internal networks.

## **Root of Trust**

The root key is the foundation of trust in a PKI. It creates a self-signed root certificate that anchors the certificate chain. When a device checks a certificate, it verifies its authenticity by tracing it back to a trusted root certificate, ensuring secure and genuine communication.

**!Certificate Validity!**

## **CRL**

**Certicate Revocation Lists** 

- Lists of revoked, expired, or compromised certificates. CAs maintain and publish these. If a certificate’s serial number is on the list, it’s invalid.

## **OCSP**

**Online Certicate Status Protocol** 

- Faster than CRLs, it allows real-time certificate validation by querying the CA’s server for status (valid, revoked, or expired).

## **Self-Signed Certificates**

A self-signed certificate is created and signed by the same entity it is issued to. Unlike third-party CA certificates, it’s not verified by an external authority. These certificates can be used for internal servers, where the entity attests to its own identity.

## **Third-Party Certificates**

Third-party certificates are issued by CAs to verify the authenticity of websites or services. These certificates are globally trusted, unlike self-signed certificates. For secure online transactions, trusted third-party certificates are essential. Examples include DigiCert, GlobalSign, GeoTrust, and Thawte.

## **CSR**

**Certificate Signing Request** 

A CSR is generated when an individual or organization requests a digital certificate from a CA. It contains details like the entity’s name, domain, and public key. The CSR outlines the key elements needed to verify the requester’s identity and create a trusted certificate. The purpose of the certificate must also be specified.

## **Wildcard Certificate**

A wildcard certificate, like *.securityplus.training, covers multiple subdomains within the same domain. It can be installed on multiple servers (e.g., web and mail) under the same domain, reducing the cost of multiple certificates. It works for Fully Qualified Domain Names (FQDNs) such as web.securityplus.training and mail.securityplus.training, and can be used for additional se