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