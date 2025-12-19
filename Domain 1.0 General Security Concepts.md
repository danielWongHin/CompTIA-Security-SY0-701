# Domain 1.0 General Security Concepts

## 1.1 Compare and contrast various types of security controls.

### Security Control Categories

- **_Technical controls_** enforce confidentiality, integrity, and availability in the digital space. eg. firewall rules, access control lists, intrusion prevention systems, and encryption.

- **_Operational controls_** include the processes that we put in place to manage technology in a secure manner. These include user access
  reviews, log monitoring, and vulnerability management.

- **_Managerial controls_** are procedural mechanisms that focus on the mechanics of the risk management process. eg. periodic risk assessments, security planning exercises, organization's change management, service acquisition, and project management practices.

- **_Physical controls_** are security controls that impact the physical world. eg. fences, perimeter lighting, locks, fire suppression systems, and burglar alarms.

### Security Control Types

- **_Preventive controls_** intend to stop a security issue before it occurs. eg. Firewalls and encryption

- **_Deterrent controls_** seek to prevent an attacker from attempting to violate security policies. eg. guard dogs and barbed wire fences

- **_Detective controls_** identify security events that have already occurred. eg. Intrusion detection systems

- **_Corrective controls_** remediate security issues that have already occurred. eg. Restoring backups after a ransomware attack

- **_Compensating controls_** are controls designed to mitigate the risk associated with exceptions made to a security policy

- **_Directive controls_** inform employees and others what they should do to achieve security objectives. eg. Policies and procedures

### Control Type Example

| Categories  | Control types example |                |                      |                               |                                 |                                  |
| ----------- | --------------------- | -------------- | -------------------- | ----------------------------- | ------------------------------- | -------------------------------- |
|             | Preventive            | Deterrent      | Detective            | Corrective                    | Compensating                    | Directive                        |
| Technical   | Firewall              | Splash Screen  | System Logs          | Backup recovery               | Block instead of patch          | File Storage Policies            |
| Managerial  | On-boarding policy    | Demotion       | Review login reports | Policies for reporting issues | Separation of duties            | Compliance Policies              |
| Operational | Guard Shack           | Reception desk | Property Patrols     | Contact Authorities           | Require Multiple Security Staff | Security Policy Training         |
| Physical    | Door lock             | Warning Signs  | Motion detectors     | Fire extinguisher             | Power Generator                 | Signed Authorized Personnel Only |

## 1.2 Summarize fundamental security concepts

### CIA and DAD Triad

![CIA](/images/domain_1/CIA_DAD.png)

### CIA Triad

- **_Confidentiality_**: Ensures that unauthorized individuals are not able to gain access to sensitive information (e.g., encryption, Access Control, MFA)

- **_Integrity_**: Ensures that there are no unauthorized modification to the information or system. (e.g., checksums, hashing, Certificates, Non-reputation)

- **_Availability_**: Ensures that information and resources are accessible when needed (e.g., redundancy measures, fault tolerance, patching)

**Non-reputation** means that someone who perform any action, cannot be denied. While not part of the CIA triad, is also an important
goal of some cybersecurity controls.

Digital signature can be used to prove the integrity and non-reputation

#### Create a digital signature

![digital_signature](/images/domain_1/create_signature.png)

#### Verify a digital signature

![Verify_digital_signature](/images/domain_1/verification_digital_signaure.png)

### DAD Triad

The DAD triad explains the three key threats to cybersecurity efforts: **disclosure**, **alteration**, and **denial**.

- Disclosure is the exposure of sensitive information to unauthorized individuals, otherwise known as **data loss**. Disclosure is a violation of the principle of confidentiality.

- Alteration is the unauthorized modification of information and is a violation of the principle of integrity.

- Denial is the disruption of an authorized user's legitimate access to information. Denial events violate the principle of availability.

The CIA and DAD triads are very useful tools for cybersecurity planning and risk analysis. Whenever you find yourself tasked with a broad goal of assessing the security controls used to protect an asset or the threats to an organization, you can turn to the CIA and DAD triads for guidance.

### Identity

Identities are the foundation of authentication and authorization. It refers to what you claimed to be. When a subject wants to use their identity, they need to use one of a number of common ways to assert or claim an identity

- **_Usernames_**

- **_Certificates_**, which can be stored on a system or paired with a storage device or security token and are often used to identify systems or devices as well as individuals.

- **_Tokens_**, a physical device that may generate a code, plug in via USB, or connect via Bluetooth or other means to present a certificate or other information

- **_SSH keys_**, which are cryptographic representations of identity that replace a username and password.

- **_Smartcards_** use an embedded chip.

### Authentication, Authorization, and Accounting (AAA)

- Authentication: Verify who you said you are

- Authorization: Verify what access do you have based on your identificaiton and authentication

- Acounting: Verify the resources used, eg. login time, data sent and received and logout time

### Authentication and Authorization

#### Authenticating people

![authenticate_people](/images/domain_1/Authenticate_people.png)

#### Authenticating systems

To authenticate the systems, we rely on **digitally signed certificate** on a device. Also other business process like VPN or Management software rely on the certificate validiate the end device.

#### Certificate authentication

An organization has a trusted certificate authority (CA), mostly maintain by their own. Then, the organization will creates a digitally signed certificate with their own CA. This certificate can now be included into the device as an authentication factor.

![certificate_authentication](/images/domain_1/certificate_authentication.png)

#### Authorization Model

After the authentication, applying the authorization model to user is important as shown below

1. Adds abstraction to reduce complexity and create clear relationship between user and resources

2. The administration is streamlined and able to support any number of users or resources

![authorization_model](/images/domain_1/authorization_model.png)

### Gap analysis

Cybersecurity professional conduct gap analysis to evaluate the security control. During the gap analysis, they will define the control objective for the organization. Gaps identified during a gap analysis should be treated as potential risks and remediated as time and resources permit.

To Start the analysis:

1. Works towards a known baseline, eg. internal sets of goals or formal standard

2. Determine the end goal, eg. NIST special publication 800-53; ISO/IEC 27001

3. Evaluate people and process to get a baseline and examine the current processes

4. Compare and evaluate the existing systems and identify the weaknesses.

5. The detailed analysis with examined broad security categories and break those into a smaller segments.

6. The analysis report will provide

   - The final comparison with baseline objective and clear view of current state
   - The path to get from crrent security to the desired goal. Eg. time, money, change control

### Zero Trust

Zero Trust presumes that there is no trust boundary and no network edge. Instead, each action is validated when requested as part of a continuous authentication process and access is only allowed after policies are checked, including elements like identity, permissions, system configuration and security status, threat intelligence data review, and security posture.

![zta](/images/domain_1/ZTA.png)

**_Subjects_** are the users, services, or systems that request access or attempt to use rights.

**_Policy Decision Point_** is where there is a process for making the authentication process.

**_Policy Engines_** make policy decisions based on both rules and external systems like threat intelligence, identity management, and SIEM devices

**_Policy Administrators_** are not individuals. Rather they are components that establish or remove the communication path between subjects and resources, including creating session-specific authentication tokens or credentials as needed.

**_Policy Enforcement_** Points communicate with Policy Administrators to forward requests from subjects and to receive instruction from the policy administrators about connections to allow or end.

To implement te zero-trust to the network, we will spit the network into two functional planes, **Data Plane** and **Control Plane**

#### Control Plane

Control Plane is where manages the actions of the data plane; define the policies and rules; determines how packets are forwarded. Eg. Routing Tables, Session Tables and Rules. It contains 4 components:

1. **_Adaptive identity_** (adaptive authentication), which leverages context-based authentication that considers data points such as where the user is logging in from, what device they are logging in from, and whether the device meets security and configuration requirements.

2. **_Threat scope reduction_** (limited blast radius), is limiting the scope of what a subject can do as well or what access is permitted to a resource limits what can go wrong if an issue does occur. It relies on least privilege as well as identity- based network segmentation that is based on identity rather than tradition network-based segmentation based on things like an IP address, a network segment, or a VLAN.

3. **_Policy-driven access control_** rely on policies as they make decisions that are then enforced by the Policy Administrator and Policy Enforcement Points. It combines the adaptive identity with a predefined set of rules.

4. **_Policy Administrator_**, executes decisions made by a Policy Engine.

#### Data Plane

Data Plane is where process the frame, packets and network data. Eg. Processing, Forwarding, Trunking, Encrypting, NAT. The Data Plane includes:

1. Implicit trust zones, which allow use and movement once a subject is authenticated by a Zero Trust Policy Engine

   - eg. Untrusted zone -> Trusted Zone -> Internal Zone

2. Subjects and systems (subject/system), which are the devices and users that are seeking access

3. Policy Enforcement Points

### Physical Security

Measures to protect tangible assets (buildings, equipment, people) from harm or unauthorized access

#### Security Controls

- Fencing and Bollards

  - Fencing and bollards stand out as some of the most primitive tools that are employed to safeguard assets and people

- Brute Force Attacks

  - Type of attack where access to a system is gained by simply trying all of the possibilities until you break through

  - Eg. Forcible Entry; Tampering with security devices; Confronting security personnel; Rammingbarriers with vehicles

- Surveillance Systems

  - Organized strategy or setup designed to observe and report activities in a given area

    - Video Surveillance (CCTV) with Motion detection, Night vision, Facial recognition

    - Security Guards, Lighting, Sensors

- Access Control Vestibules

  - Double-door system that is designed with two doors that are electronically controlled to ensure that only one door can be open at a given time

  - Prevent piggybacking and tailgating

  - Access control vestibules are usually integrated with electronic badges and operated by a security guard at the entrance to a secure facility or office building

- Door Locks

  - Critical physical security control measure designed to restrict and regulate access to specific spaces or properties, preventing unauthorized intrusions and safeguarding sensitive data and individuals

  - Types of Locks:

    - Traditional Padlocks
    - Basic Door Locks
    - Modern Electronic Door Locks
    - Cipher Lock

  - Some electronic door locks use multiple factors, such as an identification number and fingerprint, to increase security

  - Secure entry areas in office buildings, often using electronic access systems with badges and PINs for authentication

- Access Badges

  - Radio Frequency Identification (RFID) and Near Field Communication (NFC) are popular technologies used for contactless authentication in various applications

  - The badges always included Picture, name, other detailed and usually electronically logged

### Deception and Disruption technology

1. **Honeypots** is a decoy systems to attract and deceive attackers. It will be a consetent battle between the attackers to find out the honeypot is a fake non-prod environment and trapped into the honeypot

2. **Honeynets** is a network of decoy systems (Honeypots) for observing complex attacks. It includes more than a single device to make it more realistic. Eg. Servers, Workstations, Routers, Swithes, firewalls

3. **Honeyfiles** is a decoy fles to detect unauthorized access or data breaches. It attracts the attacker with more "honey", like fake information or credential, eg. password.txt. When someone get access to the file, an alert might be sent.

4. **Honeytokens** is a fake data to alert administrators when accessed or used. For example, an fake, unused API credential stored into the public cloud share.

## 1.3 Explain the importance of change management processes and the impact to security.

### Change Management

Orchestrated strategy to transition teams, departments, and organizations from existing state to a more desirable future state.

It is necessary in modern business environments due to constant changes. Change is essential but requires:

- Precision
- Planning
- Structured approach

For example, Frequency, duration, installation process, rollback procedures

#### Challenge of Change

- Unplanned or poorly coordinated changes can lead to resistance and confusion

- Even seemingly simple changes, like software upgrades, can cause issues

- Existing processes become disrupted by changes, impacting efficiency

- Sometimes extremely difficult to implement if the change management is not exist because it is hard to change corporate culture

#### Change Approval and Assessment Process

A formal process for managing change to avoid downtime, confusion and mistakes

1. Complete the request forms

2. Determine the purpose of the change

3. Identify the scope of the change

4. Schedule the date and time of the change

5. Determine affected system and the impact

6. Analyze the risk associated to the changes

7. Get approval from the change control board (CAB)

#### Change Approval and Assessment

- Changes must be approved and assessed

- Organizational processes and procedures for change approval

- Assessment evaluates value and potential disruptions

#### Ownership

- Individual or team responsible for initiating change request. They own the process but usually don't perform the actual change.

- The process updates are provided by the owner and it is their responsibility to ensure the process is followed and acceptable.

#### Stakeholders

- Individuals or teams with a vested interest in the proposed change. They might directly impacted or involved in assessment and implementation.

- These individuals or teams must be consulted. And their feedback and concerns should be considered.

#### Impact analysis

- Determin a risk value, ie. high, medium, low

- Assesses potential fallout, immediate effects, long-term impacts

- Identifies challenges and prepares for maximizing benefits

Example:

- The risk can be minor or far-reaching, like the fix breaks something else, or OS failures, or data corruption

- The risk if not making the change, like Security Vulnerability, Application Vulerability, Unexpected downtime

#### Sandbox Test Result

- Sandbox is a testing environment without any connection to the real-world or production environment.

- It uses to test and confirm before make a change to a production eg. Try the upgrade, Apply the patch.

- We can also check the backout plan to see if everythings can back to original if something does go wrong.

#### Backout Plan

- Pre-determined strategy to revert systems to their original state in case of issues during change implementation.

- Acts as a safety net for ensuring quick return to normal operations

Remark: Always have a backup

#### Scheduled Maintenance Window

- Designated timeframes for implementing changes

- Reduces potential disruptions to daily operations

- Allows flexibility for emergency changes

#### Standard Operating Procedures (SOPs)

Since the change management might affect anyone in the company, the process must be well-documented.

- Detailed step-by-step instructions for specific tasks and should be available on the intranet

- It ensures consistency, efficiency, and reduces errors in change implementation within the organization

- Should be updated over-time

### Technical Change Management

- Allow Lists and Deny Lists

  - **Allow List** specifies entities permitted to access a resource

  - **DenyList** lists entities prevented from accessing a resource

- Restricted Activities (What we can do during the change window)

  - Certain tasks labeled as 'restricted' due to their impact on system health or security

  - Verify proposed changes for any restricted activities

  - Preventdata breaches and operational disruptions by understanding restrictions

- Downtime

  - Any change,even minor, carries the risk of causing downtime

  - Estimate potential downtime and assess its negative effects against benefits

  - Schedule changes during maintenance windows to minimize impacts on end users, eg. non-production hours

  - If prevent any downtime is needed, secondary system is needed for switching during the change (part of the backout plan)

- Service and Application Restarts

  - Some changes,like installing security patches, require service or application restarts

- Dependencies

  - Interconnected systems create dependencies, where changes in one area affect others.

  - Mapping dependencies is crucial before implementing changes

- Legacy Applications

  - Older software or systems still in use due to functionality and user needs

  - Older software or systems still in use due to functionality and user needs

  - Minor updates can lead to malfunctions or crashes, so assess their compatibility.

- Documentation

  - Documentation can be outdated very quickly. Therefore, all accompanying documentation should be updated when implementing a change.

  - Updates should reflect the implementation of the change, from minor configurations to major network overhauls eg.

    - Updating diagrams to provide a visual representation of system architecture

    - Revising policies and procedures to address issues or improvements

    - Updating change requests and trouble tickets to reflect successful completion

- Version Control

  - Tracks and manages changes in documents, software, and other files eg. Router Configuration, Windows OS Patch, Application registry entries

  - Allows multiple users to collaborate and revert to previous versions when needed

  - Ensures changes do not create chaos and helps track project evolution

  - Preserves past iterations and ensures continuity and stability

## 1.4 Explain the importance of using appropriate cryptographic solutions

### Public Key Infrastructure

- An entire system involving hardware, software, policies, procedures, and people based on **asymmetric encryption**.

- Facilitates secure data transfer, authentication, and encrypted communications eg. Used in HTTPS connections on websites

#### Symmetric encryption

- A single key which perform the encryption and decryption. You will need another key if goes out

- The symmetric encryption doesn't scale very well as the difficulty of distribution. However, it is very fast to use as it has less overhead than asymeetric key. It often combined with asymmetric encryption

#### Asymmetric encryption

- It is a public key cryptography, ie. two keys (public and private key).

- The **private key** should keep as secret while the **public key** should available to anyone

- The private should be the only key that can decrypt the data encrypted by the public key.

- Key Generation will build both public and private keys which requires lots of randomization, large prime number and maths

  - Everyone can have the public key but only the owner can have the private key

  - ![key_generation](/images/domain_1/key_generation.png)

- Asymmetric Encryption:

  - ![asymmetric_encryption](/images/domain_1/asymmetric_encryption.png)

#### Key Escrow

- Storage of cryptographic keys in a secure, third-party location (escrow)

- Enables key retrieval in cases of key loss or for legal investigations

- Relevance in PKI

  - In PKI,key escrow ensures that encrypted data is not permanently inaccessible
  - Useful when individuals or organizations lose access to their encryption keys

- Security Concerns
  - Malicious access to escrowed keys could lead to data decryption
  - Requires stringent security measures and access controls

### Encrpting Data

#### Data at rest

- Protect data on storage devices eg. SSD, hard drive, USB drive, cloud storage, etc.

- Full-disk and partition/volume encryption eg. BitLocker, FileVault, etc

- File encryption eg. EFS (Encrypting File System), third-party utilities

#### Database encryption

- Encrypts data stored in a database at column, row, or table levels and the transmission of that data

- **Transparent encryption**: Encrypt all database information with a symmetric key

- **Record-level encryption**: Encrypt individual columns or use separate symmetric keys for each column

#### Transport encryption

- Protect data traversing the network

- Example:

  - Browsers can communicate using HTTPS

    - **HTTPS**: Encrypting in the application

  - Client-based VPN using SSL/TLS

    - **VPN**: Encrypts all data transmitted over the network, regardless of the application

    - **SSL/TLS**: Secure communication over networks, widely used in web browsing and email

  - Site-to-site VPN using IPsec

    - **IPsec**: Secures IP communications by authenticating and encrypting IP packets

  #### Encryption algorithms

- The proper “formula” must be used during encryption and decryption and both sides should be decided on the algorithm before encrypting the data (use thesame algorithm)

- The common factors are decided between algorithms are Security level, speed, complexity of implementation, etc

- Example of encryption algorithm: DES, AES, RSA or ECC

- The algorithm is usually a known entity but the only thing you don’t know is the key (like the door lock). So **keep your key private**

- The key determines the output

  - Encrypted data

  - Hash value

  - Digital signature

#### Key lengths

- Larger keys tend to be more secure because it can prevent brute-force attacks and

- In Symmetric encryption, 128-bit or larger symmetric keys are common to see.

- In Asymmetric encryption, complex calculations of prime numbers are applied and key lengths of 3,072 bits or larger are common to see

#### Key stretching

- Technique that is used to mitigate a weaker key by creating longer, more secure keys (at least 128 bits), so that the time needed to crack the key can be increased

- Used in systems like Wi-Fi Protected Access, Wi-Fi Protected Access version 2, and Pretty Good Privacy

- Eg. Hash a password. Hash the hash of the password

### Key Exchange

- A logistical challenge onhow do you share an encryption key across an insecure medium without physically transferring the key

- Out-of-band key exchange: Send the symmetric key without over the ‘net, eg. Telephone, courier, in-person, etc.

- In-band key exchange: Exchange the key on internet. It requires protect the key with additional encryption like using **asymmetric encryption to deliver a symmetric key**

#### Real-time encryption/decryption

- For fast security without compromising the security part

- We can share a symmetric session key using asymmetric encryption, eg. Session Key

  - Client encrypts a random or symmetric key with a server’s public key

  - The server decrypts this shared key and uses it to encrypt data

#### Symmetric key from asymmetric keys

- Use public and private key cryptography to create a symmetric key

![Sym_Key_from_Asy_Key](/images/domain_1/Sym_Key_from_Asy_Key.png)

```text
Server:
  Public Key  →  Shared
  Private Key →  Secret

Client:
  Generates Symmetric Key
        ↓
  Encrypts it with Server's Public Key
        ↓
  Sends it to Server
        ↓
Server:
  Decrypts with Private Key

➡ Secure shared secret established
```

### Encryption Technologies

#### Trusted Platform Module (TPM)

- A Dedicated microcontroller for hardware-level security to protect digital secrets through integrated cryptographic keys

- Any Cryptographic fuctions like Random number generator, key generators can provide by the TPM in a single device.

- It contains a persistent memory which allow unique keys burned in during manufacturing

- Can store the keys locally, for example, securely store BitLocker keys in the system

- Enhances device security by preventing unauthorized access

#### Hardware Security Module (HSM)

- HSM used in large environments to securely store thousands of cryptographic keys

- Ideal for mission-critical scenarios like financial transactions

- Ensures key security and regulatory compliance and secure the key backup/storage in hardware

- For real-time Encryption and decryption, cryptographic accelerators can be added to offload the CPU overhead from other devices

#### Key management system

- A management system to manage many different keys for many different services

- It manages all keys from a centralized manager from one console and separates the encryption keys from the data, often provided as third-party software

  1.  Create keys for a specific service or cloud provider (SSL/TLS, SSH, etc.)
  2.  Associate keys with specific users
  3.  Rotate keys on regular intervals
  4.  Log key use and important events

#### Challenge on maintaining the privacy of our data

1. Our data is located in many different places

2. Attackers are always finding new techniques

3. Our data is changing constantly

#### Secure Enclaves

- Coprocessor integrated into the main processor of some devices which isolated from the main processor for secure data processing and storage

- Safeguards sensitive data like biometric information

- Enhances device security by preventing unauthorized access

- It provides extensive security feature

  - Has its own boot ROM
  - Monitors the system boot process
  - True random number generator
  - Real-time memory encryption
  - Root cryptographic keys
  - Performs AES encryption in hardware

#### Obfuscation

The process of making something unclear and much more difficult to understand. It requires various techniques, including encryption, masking, and pseudonyms. It is possible to understand if you know how to read

- Steganography

  - Conceals a message within another to hide its very existence

  - The message is invisible but it’s really there

  - Primary goal is to prevent the suspicion that there’s any hidden data at all

  - Used alongside encryption for added security

  - Common steganography techniques

    1. Network based - Embed messages in TCP packets
    2. Use an image - Embed the message in the image itself
    3. Invisible watermarks - Yellow dots on printers

- Tokenization

  - Replace sensitive data with a non-sensitive placeholder

  - Reduces exposure of sensitive data during transactions For example:

    - Credit Card processing, Use a temporary token during payment and even the card numbers are captured, the attackers can't use them later

  - Since the original data and token aren’t mathematically related, this isn't require encryption or hashing to send or store the data

  ![tokenization](/images/domain_1/tokenization.png)

- Data Masking (Data Obfuscation)

  - Hide some of the original data

  - Protects PII

  - May only be hidden from view

    - The data may still be intact in storage
    - Control the view based on permissions

  - Many different techniques can be applied later eg. Substituting, shuffling, encrypting, masking out, etc.

  ### Hashing and Digital Signatures

  #### Hashing

- **Hashing** is a One-way cryptographic function that produces a unique message digest from an input. It uses to verify a downloaded document is the same as the original (Integrity).
- It can create a digital signature for Authentication, non-repudiation, and integrity.

- A hash Example:

  - Input: hello

    SHA-256 Hash: 2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824

    Input: Hello (Note the capital 'H')

    SHA-256 Hash: 185f8db32271fe25f561a6fc938b2e264306ec304eda518007d1764826381969

- Common Hashing Algorithms

  - MD5 (Message Digest Algorithm 5)

    - Creates a 128-bit hash value
    - Limited unique values, leading to collisions
    - Not recommended for security-critical applications due to vulnerabilities

  - SHA (Secure Hash Algorithm) Family

    - SHA-1

      - Produces a 160-bit hash digest, less prone to collisions than MD5

    - SHA-2

      - Offers longer hash digests (SHA-224, SHA-256, SHA-348, SHA-512)

    - SHA-3
      - Uses 224-bit to 512-bit hash digests, more secure, 120 rounds of computations

  - RIPEMD (RACE Integrity Primitive Evaluation Message Digest)

  - HMAC (Hash-based Message Authentication Code)

- Collision

  - The hash should be unique and different inputs should never create the same hash. If they do, it’s a collision (eg. MD5)

- Practical hashing example

  - Verify a downloaded file by compare the downloaded file hash with the posted hash value

  - Instead of storing the password, store a salted hash and compare hashes during the authentication process

#### Salting

- Salt is a random data added to a password when hashing. The salt is commonly stored with the password

- Each user gets a different random hash and the same password creates a different hash

- Rainbow tables won’t work with salted hashes as additional random value added to the original password

- This slows down the brute force process

- Example:

```
  User 1 (Alice):
  Password: MyP@ss123
  Salt: abcde
  Combined: abcdeMyP@ss123
  Hash (SHA-256): f1b2c3d4... (a unique hash)

  User 2 (Bob):
  Password: MyP@ss123 (Same password!)
  Salt: xyz98 (Different salt)
  Combined: xyz98MyP@ss123
  Hash (SHA-256): e8d7c6b5... (A different, unique hash)
```

#### Digital Signature

- Created by first hashing a particular message or communication that you want to digitally sign, and then it encrypts that hash digest with the user’s private key using asymmetric encryption

- Everyone can verify with the public key and any changes in the message will invalidate the signature

- Proves the message was not changed (Integrity)

- Prove the source of the message (Authentication)

- Make sure the signature isn’t fake (Non-repudiation)

- Non-repudiation is important for three main reasons

  - To confirm the authenticity of digital transactions

  - To ensure the integrity of critical communications

  - To provide accountability in digital processes

  ![digital_signature](/images/domain_1/digital_signature.png)

  #### Blockchain

  - _Blockchain_

  - Shared immutable ledger for transactions and asset tracking

    - Builds trust and transparency

    - Widely associated with cryptocurrencies like Bitcoin

    - Is essentially a really long series of information with each block containing information in it

      - Each block has the hash for the block before it

    - Block Structure

      - Chain of blocks, each containing

        - Previous block's hash
        - Timestamp
        - Root transactions (hashes of individual transactions)

      - Blocks are linked together in a chronological order

    - _Public Ledger_

      - Secure and anonymous record-keeping system
      - Maintains participants' identities
      - Tracks cryptocurrency balances
      - Records all genuine transactions in a network

  - Blockchain Applications

    - _Smart Contracts_

  - Self-executing contracts with code-defined terms

  - Execute actions automatically when conditions are met

    - Transparent, tamper-proof, and trust-enhancing

    - Commercial Uses

      - Companies like IBM promote blockchain for commercial purposes
      - Permissioned blockchain used for business transactions
      - Enhances trust and transparency with immutable public ledger

    - _Supply Chain Management_

      - Transparency and traceability in the supply chain
      - Immutable records of product origin, handling, and distribution
      - Ensures compliance and quality control

  - Broad Implications of Blockchain

    - Versatility

      - Beyond finance and cryptocurrencies
      - Applications across various industries
      - Promises transparency, efficiency, and trust

    - Decentralization

      - Key feature of blockchain
      - Eliminates need for central authorities
      - Empowers peer-to-peer networks

    - Immutable Ledger

      - Ensures data integrity
      - Records cannot be altered or deleted
      - Reinforces trust in transactions and information

    - Digital Evolution

      - Blockchain's impact on technology and industries

- Potential to reshape traditional systems

  - Offers transparency, efficiency, and trust in the digital era

### Digital certificates

- Digital Certificates is a digitally signed electronic documents

- Binds a public key with a digital signature and other details about the key holder

- Used for individuals, servers, workstations, or devices with **X.509 Standard format**

- A digital signature adds trust eg. PKI uses Certificate Authorities for additional trust, Web of Trust adds other users for additional trust

- Certificate creation can be built into the OS for you own organization eg. Windows Domain services

#### What’s in a digital certificate?

- Certificate details

  - Serial number
  - Version
  - Signature Algorithm
  - Issuer
  - Name of the cert holder
  - Public key
  - Extensions

#### Key Concepts of digital certificate?

- Root of Trust

  - Highest level of trust in certificate validation

  - Trusted third-party providers like Verisign, Google, etc.

  - Forms a certification path for trust

- Certificate Authority (CA)

  - Trusted third party that issues digital certificates

  - Certificates contain CA's information and digital signature

  - Validates and manages certificates

- Third-party certificate authorities

  - Built-in to your browser

  - When purchase your web site certificate, as long as the certificate is install into the browser, It will be trusted by everyone’s browser

  - CA is responsible for vetting the request. They will confirm the certificate owner (The trust part built-in to the CA)

- Registration Authority (RA)

  - Requests identifying information from the user and forwards certificate request up to the CA to create a digital certificate

  - Collects user information for certificates

  - Assists in the certificate issuance process

- Certificate Signing Request (CSR)

  - A block of encoded text with information about the entity requesting the certificate

  - Includes the public key

  - Submitted to CA for certificate issuance

  - Private key remains secure with the requester

  ![csr](/images/domain_1/csr.png)

      1. Create a key pair, then send the public key to the CA to be signed
      2. The CA validates the request
      3. CA digitally signs the cert and returns it to the applicant

- Private certificate authorities

  - Private Certificate Authorities (CAs) are internal, self-hosted systems for issuing digital certificates within an organization's private network

  - Use when your own internal web server or application only connected inside your network.

  - In-house CA, we needed to install your own CA software inside your organization, and the public certificate will be installed to all the computer's inside your company.

    eg. Windows Certificate Services, OpenCA

- Certificate Revocation List (CRL)

  - Maintained by CAs and listed of all digital certificates that the certificate authority has already revoked

  - It changes all the time so we needed to check the list before validating a certificate

- Online Certificate Status Protocol (OCSP)

  - Determines certificate revocation status or any digital certificate using the certificate's serial number

  - The browser can check certificate revocation by using OCSP

- OCSP Stapling

  - Alternative to OCSP which allows the certificate holder to get the OCSP record from the server at regular intervals

  - Includes OCSP record in the SSL/TLS handshake, digitally signed by the CA

  - Speeds up the secure tunnel creation

#### Types of Digital Certificates

- Self-Signed Certificates

  - Digital certificate that is signed by the same entity whose identity it certifies

  - Provides encryption but lacks third-party trust

  - Used in testing or closed systems

- Wildcard Certificate

  - Allows multiple subdomains to use the same certificate

  - Easier management, cost-effective for subdomains

  - But Compromise affects all subdomains

- Third-Party Certificates

  - Digital certificate issued and signed by trusted certificate authorities (CAs)

  - Trusted by browsers and systems

  - Preferred for public-facing websites
