# Domain 3.0 Security Architecture

## 3.1. Compare and contrast security implications of different architecture models.

### Cloud Infrastructure

- IaaS
- PaaS
- SaaS

Most cloud providers provide a matrix of responsibilities depends on different cloud provider

![cloud_respon](/images/domain_3/cloud_respon.png)

#### Hybrid Consideration

Hybrid Cloud means having more than one public or private cloud provider. 

Since they are not connected, the network protection might be mismatched, eg:

- Authentication cross platform
- Firewall Configuration
- Server Setting

Also the security monitoring might be different due to the diverse ans cloud-specific log format from providers.

Improper configuration of data sharing between cloud providers can lead to data leakage.

#### Third-party vendors in the cloud

There are third-party vendors in the cloud providing Infrastructure technologies to the Cloud-base technologieseg. Third-party firewall infront of the cloud-based application. 

Therefore, to provide the security control, we need to:

- Ongoing vendor risk assessments

- Include third-party impact for incident response

- Constant monitoring

#### Infrastructure as a code (IAC)

IAC can define the cloud infrastructure by code. Versioning and State management can be used to manage the infrastructure.

### Serverless architecture

Serverless computing doesn't mean no servers; it shifts server management away from developers

It relies on cloud service providers to handle server management, databases, and some application logic

Function as a Service (FaaS):

- Apps are separated into individual, autonomous functions

- Relies on cloud service providers to handle server management, databases, and some application logic, however Developer still creates the server-side logic

- Developers write and deploy individual functions triggered by events

- All OS security concerns are at the third-party

Benefits of Serverless:

- Reduced operational costs, Pay only for compute time used, no charges when code is idle

- Automatic scaling

- Focus on core product

- Faster time to market

Challenges and Risks:

- Vendor Lock-in and service provider dependencies

### Microervices and APIs

Architectural style for breaking down large applications into small, independent services

Each microservice runs as a unique process and communicates through a well-defined, lightweight mechanism. This contrasts with traditional monolithic architecture, where all components are tightly interconnected.

Each service in the microservice architecture is self-contained and able to run independently

![mono_micro](/images/domain_3/mono_micro.png)

Advantages of Microservices:

| Advantage | Description |
| ----------- | ----------- |
| Scalability | Services can be scaled independently based on demand |
| Flexibility | Microservices can use different technologies and be managed by different teams |
| Resilience | Isolation reduces the risk of system-wide failures |
| Faster Deployments and Updates | Independent deployment and updates allow for agility and reduced deployment risk |


Challenges of Microservices:

| Disadvantage | Description |
| ----------- | ----------- |
| Complexity | Managing multiple services involves inter-service communication, data consistency, and distributed system testing |
| Data Management | Each microservice can have its own database, leading to data consistency challenges |
| Network Latency| Increased inter-service communication can result in network latency and slower response times |
| Security | The distributed nature of microservices increases the attack surface, requiring robust security measures |

### Network Infrastructure


## 3.3. Compare and contrast concepts and strategies to protect data

### Data Breach

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



### Data Protection

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
