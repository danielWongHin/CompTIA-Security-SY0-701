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

APIs mean Application Programming Interfaces. It works with microservices to act as the application by calling API

### Network Infrastructure

Network Infrastructure is the Backbone of modern organizations. It comprises hardware, software, services, and facilities for network support and management.

#### Physical Separation

- Security measures to protect sensitive information eg. Air gap between Switch A and Switch B; Web servers and database server are in the seperated rack.

- Devices must be connected to provide communication, eg. Direct connect, or another switch or router

- Isolates a system by physically disconnecting it from all networks

- Physical Segmentation:

    - Separate devices with multiple units or separate infrastructure

#### Logical segmentation with VLANs

- Logical segmentation establishes boundaries within a network to restrict access to certain areas

- It is implemented by using firewalls, VLANs, and network devices

- The devices cannot communicate between VLANs without a Layer 3 device / router

![Vlan](/images/domain_3/Vlan.png)

#### Software-defined Network (SDN)

- Revolutionary approach to network management

- Enables dynamic, programmatically efficient network configuration

- Improves network performance and monitoring

- Reduces complexity in static and inflexible network architectures

- Provides a centralized view of the entire network

- SDN Architecture

    - Decouples network control and forwarding functions

    - Three Distinct Planes:

        1. Infrastructure layer / Data plane
            
            - Process the network frames and packets

            - Forwarding, trunking, encrypting, NAT

            - Makes decisions based on protocols like IP and Ethernet

        2. Control layer / Control plane

            - Manages the actions of the data plane

            - Dictates traffic flow across the entire network

            - Routing tables, session tables, NAT tables
            
            - Dynamic routing protocol updates

        3. Application layer / Management plane
            
            - Configure and manage the device

            - SSH, browser, API

    ![sdn](/images/domain_3/sdn.png)

### On-Premise vs. Cloud Deployment

On-Premise is a traditional local infrastructure setup while Cloud deliver the computing services over the internet

#### On-premises security

You have the full control when everything is in-house. The local team can ensure everything is secure, but they can be expensive and difficult to staff. 

Local team maintains uptime and availability. eg. System checks can occur at any time. However, Security changes can take time, eg. New equipment, configurations, and additional costs

#### Centralized vs Decentralized Architectures

Centralized Architecture means all computing functions managed from a single location or authority

- Components

    - Central Server
    - Mainframe
    - Data Center

- Data and applications stored in one place, accessed via a network

- Benefits

    - **Efficiency and Control**:   High resource control and efficient resource allocation

    - **Consistency**:  Ensures uniform and accurate data across the organization

    - **Cost-effective**:   Reduced maintenance and infrastructure costs

- Risks

    - **Single Point of Failure**:  Server failure can disrupt the entire network

    - **Scalability Issues**:   Struggles to handle growth, leading to performance problems

    - **Security Risks**:   Attractive targets for cybercriminals; compromised server risks data and app security

Decentralized Architecture means computing functions distributed across multiple systems or locations. 

There is No single point of control; each node operates independently

- Benefits

    - **Resilience** can continue functioning despite individual node failures

    - **Scalability** easily scales with organization growth by adding new nodes

    - **Flexibility** supports remote work and distributed teams

- Risks

    - **Security Risks**:   Vulnerable to security threats, especially in remote work scenarios

    - **Management Challenges**:    Complex management, coordinating multiple nodes

    - **Data Inconsistency**:   Potential issues with data consistency and synchronization

_Use centralized systems for data accuracy and resource management priorities_

_ Use decentralized system for Resilience, flexibility, and rapid scaling need_

### Infrastructure Considerations

- **Availability**: System's ability to be accessed when needed eg. System Uptime

- **Resilience**: System's ability to recover from failures (MTTR)

- **Cost Consider** both upfront and long-term costs eg. Maintenance; Replacement; Tax

- **Responsiveness**: Speed at which the system can adapt to demand

- **Scalability**: System's ability to handle increased workloads

- **Ease of Deployment**: Cloud services are easier to set up than on-premise solutions

- **Risk Transference**: Some risks are transferred to the provider, but customers are responsible for security, eg. Cybersecurity insurance; Recover internal losses

- **Ease of Recovery**: Cloud services offer easy data recovery and backup solutions

- **Patch Availability**: Providers release patches for vulnerabilities automatically

- **Inability to Patch**: Compatibility issues or lack of control can hinder patching

- **Power**:  Cloud provider manages infrastructure, including power supply. Reduces customer costs and eliminates power management concerns

- **Compute**: Refers to computational resources, including CPUs, memory, and storage. Cloud providers offer various compute options to suit different needs

#### Virtualization and Containerization

Virtualization emulates servers, each with its own OS within a virtual machine

Containerization is a lightweight alternative, encapsulating apps with their OS environment

![VA_CA](/images/domain_3/VA_CA.png)

- Virtualization Vulnerabilities

    - Virtual Machine (VM) Escape:  Attackers break out of isolated VMs to access the hypervisor

    - Privilege Elevation:  Unauthorized elevation to higher-level users

    - Live VM Migration:    Attacker captures unencrypted data between servers

    - Resource Reuse:   Improper clearing of resources may expose sensitive data

- Containerization Technologies

    - Docker, Kubernetes, Red Hat OpenShift are popular containerization platforms

    - Revolutionized application deployment in cloud environments

- Securing Virtual Machines

    - Regularly update OS, applications, and apply security patches
    - Install antivirus solutions and software firewalls
    - Use strong passwords and implement security policies
    - Secure the hypervisor with manufacturer-released patches
    - Limit VM connections to physical machines and isolate infected VMs
    - Distribute VMs among multiple servers to prevent resource exhaustion
    - Monitor VMs to prevent "Virtualization Sprawl”
    - Enable encryption of VM files for data safety and confidentiality

#### Internet of Things (IoT)

IOT is a network of physical devices with sensors, software, and connectivity. It enables data exchange among connected objects.

IOT consists of the below devices:

- Hub/Control System

    - Central component connecting IoT devices

    - Collects, processes, analyzes data, and sends commands

    - Can be a physical device or software platform

- Smart Devices

    - Everyday objects enhanced with computing and internet capabilities

    - Sense environment, process data, and perform tasks autonomously, eg. Home automation

- Wearables

    - Subset of smart devices worn on the body
    
    - Monitor health, provide real-time information, and offer hands-free interface

- Sensors

    - Detect changes in environment, convert into data

    - Measure various parameters (temperature, motion, etc.)

    - Enable interaction and autonomous decisions in smart devices

IOT Risks:

- Weak Default Settings

    - Common security risk

    - Default usernames/passwords are easy targets for hackers

    - Changing defaults upon installation is essential

- Poorly Configured Network Services

    - Devices may have vulnerabilities due to open ports, unencrypted communications

    - Unnecessary services can increase attack surface

    - Keeping IoT devices on a separate network is recommended

#### ICS and SCADA

**Industrial Control Systems (ICS) are the systems**

- Used to monitor and control industrial processes, found in various industries like electrical, water, oil, gas, and data

- Distributed Control Systems (DCS)

    - Used in control production systems within a single location

- Programmable Logic Controllers (PLCs)

    - Used to control specific processes such as assembly lines and factories

**Supervisory Control and Data Acquisition (SCADA) Systems**

- Type of ICS designed for monitoring and controlling geographically dispersed industrial processes

- Common in industries like

    - Electric power generation, transmission, and distribution systems
    - Water treatment and distribution systems
    - Oil and gas pipeline monitoring and control systems

- Risks and Vulnerabilities

    - Unauthorized Access:  Unauthorized individuals can manipulate system operations without proper protection

    - Malware Attacks:  Vulnerable to disruptive malware attacks

    - Lack of Updates:  Running outdated software with unpatched vulnerabilities

    - Physical Threats: Susceptible to damage to hardware or infrastructure

- Securing ICS and SCADA Systems

    - Implement Strong Access Controls

        - Strong passwords
        - Two-factor authentication
        - Limited access to authorized personnel only

    - Regularly Update and Patch Systems

        - Keep systems updated to protect against known vulnerabilities

    - Use Firewall and Intrusion Detection Systems

        - Detect and prevent unauthorized access

    - Conduct Regular Security Audits

        - Identify and address potential vulnerabilities through routine assessments

    - Employee Training

        - Train employees on security awareness and response to potential threats

#### Embedded System and Real-Time Operating System (RTOS)

**Embedded Systems**

- Specialized computing components designed for dedicated functions within larger devices. They integrate hardware and mechanical elements and are essential for various daily-use devices

**Real-Time Operating System (RTOS)**

- Designed for real-time applications that process data without significant delays

- Critical for time-sensitive applications like flight navigation and medical equipment

- Risks and Vulnerabilities in Embedded Systems

    - Hardware Failure

        - Prone to failure in harsh environments

    - Software Bugs

        - Can cause system malfunctions and safety risks

    - Security Vulnerabilities

        - Vulnerable to cyber-attacks and unauthorized access

    - Outdated Systems

        - Aging software and hardware can be more susceptible to attacks

- Key Security Strategies for Embedded Systems

    - Network Segmentation

        - Divide the network into segments to limit potential damage in case of a breach

    - Wrappers (e.g., IPSec)

        - Protect data during transfer by hiding data interception points

    - Firmware Code Control

        - Manage low-level software to maintain system integrity

    - Challenges in Patching

        - Updates face operational constraints; OTA updates demand meticulous planning and security measures

            - Over-the-Air (OTA) Updates:   Patches are delivered and installed remotely

## 3.2 Given a scenario, apply security principles to secure enterprise infrastructure.

### Secure Infrastructures

Services may require their own security technologies, eg. Firewalls, Honeypots, jump server, load balancers, sensors

#### Security Zones

Security Zones is isolate devices with similar security requirements. Each area of the network is associated with a zone,eg. Trusted, untrusted; internal, external; Inside, Internet, Servers, Databases, Screened

![security_zone](/images/domain_3/security_zone.png)

#### Attack Surface

Refers to points where unauthorized access or data extraction can occur. A larger attack surface increases the risk of vulnerabilities.

Identify and mitigate vulnerabilities to reduce the attack surface. Regularly assess and minimize the attack surface for network security

Can be minimized by

- Restricting Access

- Removing unnecessary software

- Disabling unused protocols

Think of threat vector as the "how" of an attack, whereas the attack surface is the "where" of the attack

#### Connectivity

- Choose connectivity methods that influence network performance, reliability, and security

- Wired (e.g., Ethernet) offers stability and speed but restricts mobility

- Wireless (e.g., Wi-Fi) provides flexibility but may suffer from interference and security issues

- Consider factors like scalability, speed, security, and budget constraints when choosing connectivity methods

- Network-level encryption, eg, IPsec tunnels, VPN connections

- Application-level encryption

### Intrusion Prevention

Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS) are used to Identifying trends and Showcasing signatures

#### Failure Mode

Choose between "fail-open" and "fail-closed" modes to handle device failures

- Fail-open: Allows traffic to pass during a failure, maintaining connectivity but reducing security

- Fail-closed: Blocks all traffic during a failure, prioritizing security over connectivity

The choice depends on the organization's security policy and the criticality of the network segment

#### Intrusion Prevention Systems (IPS)

- Logs, alerts, and takes action when it finds something suspicious or malicious

- Scans traffic to look for malicious activity and takes action to stop it

- Commonly **Active Monitoring**

![IPS](/images/domain_3/IPS.png)

#### Intrusion Detection System (IDS)

- Logs or alerts that it found something suspicious or malicious

- Three Types of Intrusion Detection Systems (IDS)
        
    - Network-based IDS (NIDS): Monitors the traffic coming in and out of a network

    - Host-based IDS (HIDS):   Looks at suspicious network traffic going to or from a single or endpoint
        
    - Wireless IDS (WIDS):  Detects attempts to cause a denial of a service on a wireless network

    - Commonly **Passive Monitoring**
    
- Intrusion detection systems operate either using signature-based or anomaly-based detection algorithms

    - Signature-based IDS:  Analyzes traffic based on defined signatures and can only recognize attacks based on previously identified attacks in its database eg. Pattern-matching, Stateful-matching

    - Anomaly-based IDS: Analyzes traffic and compares it to a normal baseline of traffic to determine whether a threat is occurring eg. Statistical, Protocol, Traffic, Rule or Heuristic, Application-based

    ![IDS](/images/domain_3/IDS.png)

### Network Appliances

#### Jump Server

Secure gateways for system administrators to access devices in different security zones. 

- Control access and reduce the attack surface area

- Offer protection against downtime and data breaches

- Simplify logging and auditing

- Speed up incident response during cyber-attacks

- Streamline system management and maintenance

- Host essential tools and scripts

- Monitor system health for performance and security

#### Proxy Servers

Act as intermediaries between clients and servers

- Provide content caching, requests filtering, and login management

- Enhance request speed and reduce bandwidth usage

- Add a security layer and enforce network utilization policies

- Protect against DDoS attacks

- Facilitate load balancing and user authentication

- Handle data encryption and ensure compliance with data sovereignty laws

**Forward Proxy/Internal Proxy**

- Commonly used to protect and control user access to the Internet

**Reverse Proxy**

- Inbound traffic from the Internet to your internal service

**Open Proxy**

- A third-party, uncontrolled proxy. Often used to circumvent existing security controls

**Application proxies**

- Most proxies in use are application proxies, The proxy understands the way the application works and only know one application eg. HTTP

- Many proxies are multipurpose proxies. eg. HTTP, HTTPS, FTP, etc.

#### Load Balancing

- Distributes workloads across multiple resources

- Optimizes resource use, throughput, and response time

- Prevents overloading of any single resource

- Incoming requests are directed to capable servers

#### Active/active and Active/Passive load balancing 

Active/active load balancing

- Configurable load: Manage across servers

- TCP offload: Protocol overhead

- SSL offload: Encryption/Decryption

- Caching: Fast response

- Prioritization: QoS

- Content switching: Application-centric balancing

Active/passive load balancing

- Some servers are active while others are standby

- If an active server fails, the passive server takes its place

#### Sensors and collectors

- Aggregate information from network devices

- Built-in sensors, separate devices

- Integrated into switches, routers, servers, firewalls, etc.

Example of Sensors: Intrusion prevention systems, firewall logs,authentication logs, web server access logs, database transaction logs, email logs

Example collectors: Proprietary consoles (IPS, firewall), SIEM consoles, syslog servers

Many SIEMs include a correlation engine to compare diverse sensor data

#### Port Security

- A network switch feature that restricts device access to specific ports based on MAC addresses

- Enhances network security by preventing unauthorized devices from connecting

#### EAP (Extensible Authentication Protocol)

- A framework for various authentication methods

- Many different ways to authenticate based on RFC standards eg. EAP-MD5, EAP-TLS, EAP-TTLS, EAP-FAST, PEAP, EAP-LEAP

- EAP integrates with 802.1X.

#### IEEE 802.1X

- Port-based Network Access Control mechanism based on the IEEE 802.1x standard

- Modern NAC solutions build on 802.1x, enhancing features and capabilities

- 802.1X prevents access to the network until the authentication succeeds

- Used in conjunction with an authentication database eg. RADIUS, LDAP, TACACS+, Kerberos, etc.

- IEEE 802.1X and EAP

    - Supplicant - the client

    - Authenticator - The device that provides access

    - Authentication server - Validates the client credentials

#### Firewall Types

**Firewall**

- A network security device or software that monitors and controls network traffic based on security rules

- Dedicated devices for using Access Control Lists (ACLs) to protect networks

- Protects networks from unauthorized access and potential threats

- There are different types of firewalls:

    - Packet Filtering Firewalls

        - Inspect packet headers for IP addresses and port numbers

        - Limited in inspection, operates at Layer 4 (Transport Layer)

    - Stateful Firewalls
        
        - Track connections and requests, allowing return traffic for outbound requests

        - Operates at Layer 4, with improved awareness of connection state

    - Proxy Firewalls

        - Make connections on behalf of endpoints, enhancing security

        - Two Types of Proxy FirewallscSession layer(Layer 5) and Application layer (Layer 7)

    - Kernel Proxy Firewalls

        - Minimal impact on network performance, full inspection of packets at every layer
        
        - Placed close to the system they protect

    - Layer based Firewalls
        
        - Layer 4 Firewall, Operates at the transport layer

            - Filters traffic based on port numbers and protocol data
        
        - Layer 7 Firewall, Operates at the application layer

            - Inspects, filters, and controls traffic based on content and data characteristics

    - Unified Threat Management (UTM) Firewall
        
        - Combines multiple security functions in a single device
        
        - Functions include:

            - firewall, intrusion prevention, antivirus, Spam filter, Router, Switch and IDS/IPS

        - Reduces the number of devices
        
        - Are a single point of failure

        - UTMs use separate individual engine

            - NGFW uses a single engine

    - Next Generation Firewall (NGFW)
        
        - Application-aware
            
            - distinguish between different types of traffic

        - Conduct deep packet inspection and use signature-based intrusion protection

        - Operate fast within minimal network performance impact

            - Offer full-stack traffic visibility

        - Can integrate with other security products

            - Can be a problem if organizations become reliant on a single vendor due to firewall configurations tailored to one product line

    - Web Application Firewall (WAF)
        
        - Focuses on inspecting HTTP traffic
        
        - Prevents common web application attacks like cross-site scripting and SQL injections
        
        - Can be placed
            
            - In-line (live attack prevention)

                - Device sits between the network firewall and the web servers
            
            - Out of band (detection)

                - Device receives a mirrored copy of web server traffic

#### Secure Communication

- Virtual Private Networks (VPNs)

    - Extend private networks across public networks
    
    - Allow remote users to securely connect to an organization's network

    - Can be configured as site-to-site, client-to-site, or clientless VPNs

- Encrypted tunnel

    - Keep data private across the public Internet； Encryption is the key

    - Encrypt your data - Add new headers and trailers

    - Decrypt on the other side - Original data is delivered

- Types of VPN

    - Site-to-Site VPN

        - Connects two sites cost-effectively
        - Replaces expensive leased lines
        - Utilizes a VPN tunnel over the public internet           
        - Encrypts and secures data between sites
        - Slower, but more secure

    - Client-to-Site VPN

        - Connects a single host (e.g., laptop) to the central office
        - Ideal for remote user access to the central network
        - Options for full tunnel and split tunnel configurations

    - Clientless VPN
            
        - Uses a web browser to establish secure, remote-access VPN
        - No need for dedicated software or hardware client
        - Utilizes HTTPS and TLS protocols for secure connections to websites
    
    - SSL/TLS VPN (Secure Sockets Layer VPN)

        - Uses common SSL/TLS protocol (tcp/443), Therefore, no firewall issues

        - Usually remote access communication

        - No requirement for digital certificates or shared passwords (like IPSec), but we can use those if liked

        - Can be run from a browser or from a (usually light) VPN client across many operation system

        - On-demand access from a remote device: Software connects to a VPN concentrator, Some software can be configured as always-on

        ![ssl_tls_vpn](/images/domain_3/ssl_tls_vpn.png)
    
    - Site-to-site IPsec VPN

        - Always-on

        - Firewalls often act as VPN concentrators; Probably already have firewalls in place

        ![ipsec_vpn](/images/domain_3/ipsec_vpn.png)
    
    - SD-WAN (Software-Defined Wide Area Network)

        - A virtualized approach to managing and optimizing wide area network connections

        - Efficiently routes traffic between remote sites, data centers, and cloud environments

        - It can increased agility, security, and efficiency for geographically distributed workforces

        - Software-based architecture with control extracted from underlying hardware

        - Utilizes centralized control function for intelligent traffic routing

        - Use Cases

            - Ideal for enterprises with multiple branch offices moving towards cloud-based services eg. IaaS, PaaS, SaaS
    
    - Secure Access Service Edge (SASE)

        - A network architecture combining network security and WAN capabilities in a single cloud-based service

        - used to addresse challenges of securing and connecting users and data across distributed locations

        - Utilizes software-defined networking (SDN) for security and networking services from the cloud

        - Components

            - Firewalls
            - VPNs
            - Zero-trust network access
            - Cloud Access Security Brokers (CASBs)

        - Delivered through a common set of policy and management platforms

        ![sase](/images/domain_3/sase.png)

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

