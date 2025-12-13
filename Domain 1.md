# Domain 1.0 General Security Concepts

## Implementing Security Controls

### Gap analysis

Cybersecurity professional conduct gap analysis to evaluate the security control. During the gap analysis, they will define the control objective for the organization. Gaps identified during a gap analysis should be treated as potential risks and remediated as time and resources permit.

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

## CIA and DAD Triad

![CIA](/images/CIA_DAD.png)

### CIA Triad

- **_Confidentiality_**: Ensures that unauthorized individuals are not able to gain access to sensitive information (e.g., encryption)
- **_Integrity_**: Ensures that there are no unauthorized modification to the information or system. (e.g., checksums)
- **_Availability_**: Ensures that information and resources are accessible when needed (e.g., redundancy measures)


**Non-reputation** means that someone who perform any action, cannot be denied. While not part of the CIA triad, is also an important
goal of some cybersecurity controls.

### DAD Triad

The DAD triad explains the three key threats to cybersecurity efforts: **disclosure**, **alteration**, and **denial**.

- Disclosure is the exposure of sensitive information to unauthorized individuals, otherwise known as **data loss**. Disclosure is a violation of the principle of confidentiality.

- Alteration is the unauthorized modification of information and is a violation of the principle of integrity. 

- Denial is the disruption of an authorized user's legitimate access to information. Denial events violate the principle of availability.


The CIA and DAD triads are very useful tools for cybersecurity planning and risk analysis. Whenever you find yourself tasked with a broad goal of assessing the security controls used to protect an asset or the threats to an organization, you can turn to the CIA and DAD triads for guidance.


## Data Breach

Data breaches have significant and diverse impacts on organizations. When an organization suffers a data breach, the resulting data loss often results in both direct and indirect damages. The impacts of a security incident may be wide-ranging, depending on the nature of the incident and the type of organization affected.

| Risks   | Description |
| :--------------- | :------- |
| Financial    | The risk of monetary damage to the organization as the result of a data breach (direct/ indirect)|
| Reputational | The negative publicity surrounding asecurity breach causes the loss of goodwill among customers, employees, suppliers, and other stakeholders.     |
| Strategic    | The risk that an organization will become less effective in meeting its major goals and objectives    |
| Operational    |  The risk to the organization's ability to carry out its day-to-day functions |
| Compliance | Occurs when a security breach causes an organization to run afoul of legal or regulatory requirements.|

>Be careful of the **Identity Theft**.
>
>Risks often cross categories



## Data Protection

Security professionals spend significant amounts of their time focusing on the protection of sensitive data. Data must be protected in three states.

- Data at rest is stored data that resides on hard drives, tapes, in the cloud, or on other storage media, etc. This data is prone to theft by
insiders or external attackers who gain access to systems and are able to browse through their contents.

- Data in transit is data that is in motion/transit over a network. When data travels on an untrusted network, it is open to eavesdropping attacks by anyone with access to those networks.

- Data in use is data that is actively in use by a computer system. This includes the data stored in memory while processing takes place. An attacker with control of the system may be able to read the contents of memory and steal sensitive information.

We can use different security controls to safeguard data in all of these states

| Security Control              | Descritpion | Example |
| :---------------------------  | :-------  | :-------|
| Data Encryption               | uses mathematical algorithms to protect information both while it is in transit over a network and while it resides on systems.   | Cryptography and the PKI |
| Data Loss Prevention          | helps organizations enforce information handling policies and procedures to prevent data loss and theft.    | Block the transmission include sensitive information or unsecure |
| Data Minimization             | seek to reduce risk by reducing the amount of sensitive information that we maintain on a regular basis.|Destroy data when it is no longer necessary; Hashing, Tokenization, Masking|
| Access Restrictions           | security measures that limit the ability of individuals or systems to access sensitive information or resources | Geographic restrictions; Permission restrictions |
| Segmentation and Isolation    | limit the access to sensitive systems based on their network location. | Seperate network for sensitive data or isolate the network from public| 
