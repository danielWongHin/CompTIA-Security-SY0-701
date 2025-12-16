# Domain 1.0 General Security Concepts

## 1.1 Compare and contrast various types of security controls. 

### Security Control Categories

- **_Technical controls_** enforce confidentiality, integrity, and availability in the digital space. eg. firewall rules, access control lists, intrusion prevention systems, and encryption.

- **_Operational controls_** include the processes that we put in place to manage technology in a secure manner. These include user access
reviews, log monitoring, and vulnerability management.

- **_Managerial controls_** are procedural mechanisms that focus on the mechanics of the risk management process. eg.  periodic risk assessments, security planning exercises, organization's change management, service acquisition, and project management practices.

- **_Physical controls_** are security controls that impact the physical world. eg. fences, perimeter lighting, locks, fire suppression systems, and burglar alarms.

### Security Control Types

- **_Preventive controls_** intend to stop a security issue before it occurs. eg. Firewalls and encryption 

- **_Deterrent controls_** seek to prevent an attacker from attempting to violate security policies. eg. guard dogs and barbed wire fences

- **_Detective controls_** identify security events that have already occurred. eg. Intrusion detection systems

- **_Corrective controls_** remediate security issues that have already occurred. eg. Restoring backups after a ransomware attack

- **_Compensating controls_** are controls designed to mitigate the risk associated with exceptions made to a security policy

- **_Directive controls_** inform employees and others what they should do to achieve security objectives. eg. Policies and procedures

### Control Type Example

| Categories | Control types example |  |  |  |  |  |
|-------|----------------------------|-------|-------|-------|-------|-------|
|       |  Preventive     | Deterrent      |  Detective     |  Corrective     |  Compensating     |    Directive   |
|     Technical  |    Firewall   |   Splash Screen    |  System Logs     |  Backup recovery     |   Block instead of patch    |    File Storage Policies   |
|   Managerial    |   On-boarding policy    |    Demotion   |   Review login reports    |  Policies for reporting issues     |  Separation of duties     |    Compliance Policies   |
|   Operational    |    Guard Shack   |     Reception desk  |   Property Patrols    |    Contact Authorities   |   Require Multiple Security Staff    |    Security Policy Training   |
|    Physical   |    Door lock   |   Warning Signs    |     Motion detectors  |   Fire extinguisher    |    Power Generator   |   Signed Authorized Personnel Only    |


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

4. **_Policy Administrator_**,  executes decisions made by a Policy Engine.

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

    - Eg. Forcible Entry; Tampering with security devices; Confronting security personnel;  Rammingbarriers with vehicles

 - Surveillance Systems

    - Organized strategy or setup designed to observe and report activities in a given area

        -  Video Surveillance (CCTV) with Motion detection, Night vision, Facial recognition 

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

## 1.3 Explain the importance of change management processes  and the impact to security. 

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