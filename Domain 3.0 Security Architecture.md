# Domain 3.0 Security Architecture

## 3.3. Compare and contrast concepts and strategies to protect data

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
