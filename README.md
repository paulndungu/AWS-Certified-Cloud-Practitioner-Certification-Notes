# AWS Certified Cloud Practitioner Certification - My Notes

## Deployment Models for Cloud Computing

- Cloud-Based Deployment
- On-Premises Deployment
- Hybrid Deployment


## Benefits of Cloud Computing

- **Trade upfront/capital(CAPEX) expense for/with variable/operational(OPEX) expense**
    - Instead of having to invest heavily in data centers and servers before you know how you’re going to use them, you can pay only when you consume computing resources, and pay only for how much you consume.
- **Stop spending money to run and maintain data centers**
    - Focus on projects that differentiate your business, not the infrastructure. Cloud computing lets you focus on your own customers, rather than on the heavy lifting of racking, stacking, and powering servers.
- **Stop guessing capacity**
    - Eliminate guessing on your infrastructure capacity needs. When you make a capacity decision prior to deploying an application, you often end up either sitting on expensive idle resources or dealing with limited capacity.
    - With cloud computing, these problems go away. You can access as much or as little capacity as you need and scale up and down as required with only a few minutes’ notice.
- **Benefit from massive economies of scale**
    - By using cloud computing, you can achieve a lower variable cost than you can get on your own. Because usage from hundreds of thousands of customers is aggregated in the cloud, providers such as AWS can achieve higher economies of scale, which translates into lower pay as-you-go price.
- **Increase speed and agility**
    - In a cloud computing environment, new IT resources are only a click away, which means that you reduce the time to make those resources available to your developers from weeks to just minutes.
    - This results in a dramatic increase in agility for the organization since the cost and time it takes to experiment and develop is significantly lower.
- **Go global in minutes**
    - Easily deploy your application in multiple regions around the world with just a few clicks. This means you can provide lower latency and a better experience for your customers at minimal cost.

## Design principles AWS in the cloud

- Perform operations as code
- Make frequent, small
- reversible changes
- Refine operations procedures frequently
- Anticipate failure
- learn from ops failures

## AWS Shared Responsibility Model

![Image1](./images/img1.png)

![Image2](./images/img2.png)


## Amazon EC2 Instance Types

- **General Purpose instances**:
    - Balanced computing, memory, and networking.
    - Suitable for web servers, dev environments, and medium databases.
- **Compute-optimized instances**:
    - High vCPUs to memory ratio.
    - Ideal for scientific modeling, batch processing, gaming server
- **Memory-optimized instances**:
    - Designed for large in-memory processing.
    - Perfect for in-memory databases and real-time big data analytics.
- **Accelerated computing instances**:
    - Uses hardware accelerators like GPUs.
    - Targeted at machine learning, video processing, high-performance computing.
- **Storage optimized instances**:
    - High sequential read/write access.
    - Great for distributed file systems and data warehousing.


## AWS EC2 Instance Store

Provides temporary block-level storage for your EC2 instances. This storage is located on disks that are physically attached to the host computer. Instance store is ideal for temporary storage of information that changes frequently, such as buffers, caches, scratch data, and other temporary content. It can also be used to store temporary data that you replicate across a fleet of instances, such as a load-balanced pool of web servers. While it can be used for high-speed storage, it is not specifically optimized for caching


## Amazon EC2 Pricing
![image](https://github.com/user-attachments/assets/ca57aea6-6436-4324-b135-a2ea87674e90)


### On-Demand

- It is ideal for short-term, irregular workloads that cannot be interrupted
- No upfront costs or minimum contract apply
- Pay-as-you-go pricing model

### Reserved instances

![image](https://github.com/user-attachments/assets/ca7ce68f-4fbd-4e16-b4a2-8aa65e677369)

- Standard Reserved Instance- you should know the EC2 instance type and size you need for your applications and in which AWS Region you plan to run them and you are required to state instance type and size, OS, tenancy (default or dedicated)
- Convertible Reserved Instance- used if you need to run your EC2 instances in different Availability Zones or different instance types. You trade in a deeper discount when you require flexibility to run your EC2 instances and at the end of the term you can continue using the Amazon EC2 instance without interruption. However, you will now be charged On-Demand rates until you terminate the instance or purchase a new reserve instance matching the previous instance attributes
![image](https://github.com/user-attachments/assets/9cdb5545-18bb-4e82-917f-0bc099b84ab9)
### EC2 Instance saving plans

- Commitment Duration and Flexibility
- Instance Family and Sizes
- Instance Flexibility
- Regional and Zonal Options
- Shared Usage
- 1-year or 3-year term

### Spot instance

- Interruptions are possible
- 90% discount

### Dedicated host

![Image3](./images/img3.png)

- Isolation and Compliance
- Instance Placement Control
- Instance Type Flexibility
- Cost Predictability
- Visibility and Reporting

![image](https://github.com/user-attachments/assets/945b746f-ae63-4b36-85ca-1314a334933f)



## AWS Services

- **AWS Management Console**:
    - Web-based user interface.
    - Allows users to manage AWS services through a browser.
    - Intuitive graphical interface with organized dashboard.
    - Suitable for those who prefer a GUI-based interaction.
- **AWS CLI (Command Line Interface)**:
    - Provides direct commands for AWS services.
    - Can be used on Windows, Mac, and Linux.
    - Suitable for scripting and automation.
    - Offers deep functionality and control over services.
- **AWS SDK (Software Development Kit)**:
    - Provides libraries in multiple programming languages.
    - Enables developers to integrate AWS services into their applications.
    - Contains tools, documentation, and sample code.
    - Allows for application-level management and automation of AWS resources.

## AWS Cloud9

- It is a cloud-based integrated development environment (IDE).
- Provides access via browser to write, run and debug code.
- It comes integrated with AWS services and it is possible to manage AWS resources directly from the Cloud9 IDE.


## VPC

- **Internet Gateway (IGW)**:
    - Allows you to create a VPN connection between a private network, like your on-premises data center or internal corporate network to your VPC. This is used when a VPC has           internal private resources and we want to restrict access to these resources only to entities coming from an approved network
    - Connects a VPC to the internet.
    - Allows instances in the VPC to directly communicate with the internet.
    - Essential for a public subnet in a VPC to send/receive traffic to/from the internet.
- **Virtual Private Gateway (VGW)**:
    - Endpoint for connecting a VPC to a VPN or AWS Direct Connect.
    - Establishes connectivity between AWS and on-premises data centers or other remote networks.
- **VPC Peering**:
    - Allows direct network connectivity between two VPCs.
    - VPCs can be in the same AWS account or different accounts.
    - Ensures private, high-speed communication between VPCs without routing traffic through the internet.
- **AWS Direct Connect**:
    - Dedicated network connection from on-premises to AWS.
    - Bypasses the public internet for more consistent network performance.
    - Can reduce network costs, increase bandwidth, and provide a more consistent network experience than internet-based connections.
    - without public internet
- **NAT Gateway**:
    - Allows instances in a private subnet to initiate outbound traffic to the internet.
    - Prevents unsolicited inbound traffic from reaching those instances.
    - Used for scenarios where instances need to download patches, updates, etc., but should not be directly accessed from the internet.
    - Managed by AWS
- **NAT Gateway vs NAT Instance**
    ![Image4](./images/img4.png)

    

## Subnets

- A **private subnet** is a segment of an Amazon Virtual Private Cloud (VPC) that does not have direct internet access, making it suitable for hosting resources requiring enhanced security or internal communication within the VPC.
- A **public subnet** is a segment of an Amazon Virtual Private Cloud (VPC) that is accessible from the internet, allowing resources deployed within it to have direct internet connectivity, making it suitable for web servers or applications that require external access.


## Security Groups vs Network ACLs (NACL)

![Image5](./images/img5.png)


## Security Group

- Instance-Level Security
- Stateful
- Allow Rules Only
- No Rule Numbers
- Dynamic and Easy
- Permissive to Restrictive
- **Services:** EC2, RDS, ElastiCache, Redshift, DocumentDB, Lambda, Neptune, EFS, Elastic MapReduce, WorkSpaces, AppStream, Glue, Snow Family, ELB, VPC Endpoints
- **Security groups accept IP address, IP address range, and security group ID as either source or destination of inbound or outbound rules.**

## Network ACLs (NACL)

- Traffic Filtering
- Stateless
- Ordered Rules
- Numerical Rule Numbers
- Subnet Association
- **Services:** S3, EC2, RDS, RedShift, ElastiCache, EFS, DocumentDB, Neptune, EMR, VPC Endpoints

## Amazon Elastic Block Store (EBS)

- EBS provides block-level storage for EC2 instances.
- Offers various volume types for different IOPS (Input/Output Operations Per Second) requirements.
- Volume data is automatically replicated to several physical drives, increasing durability.
- EBS snapshots provide data protection by creating backups (snapshots) in S3.
- Has the ability to optionally enlarge or change volumes. (auto scale)
- **Amazon EBS pricing includes three factors: volumes, snapshots, data transfer**
- **It is not a regional service**

## Amazon Elastic File System (EFS)

- Fully managed, scalable, and highly available file storage service designed to be used with AWS Cloud services and on-premises resources
- Can be shared simultaneously by multiple EC2 instances, making it suitable for multi-server workloads.
- It is elastic and the storage capacity automatically increases or decreases according to your files.
- It has high durability and usability; files are automatically replicated across multiple Availability Zones.
- It comes with POSIX-compliant file system semantics, which makes it suitable for many applications.
- It is a regional service.
- Costs each write and read.


## AWS S3 Storage Classes

![Image6](./images/img6.png)

![Image7](./images/img7.png)


**S3 Standard:**

- Designed for frequently accessed data stored in a minimum of three Availability Zones. Due to its high availability for objects, it is a good choice for content distribution and 
  data analytics. It has a higher cost than other storage classes intended for infrequently accessed data and archival storage
- General-purpose storage class.
- Provides high durability and fast data access.
- Suitable for frequently accessed and frequently updated data.
- Stores data in a minimum of three Availability Zones
- Host static website

**S3 Standard-Infrequent Access (S3 Standard-IA):**

- Used for data that is accessed infrequently but requires rapid access when needed. It's a perfect place to store backups, disaster recovery files or any object that requires       long-term storage
- Ideal for infrequently accessed data
- Similar to Amazon S3 Standard but has a lower storage price and higher retrieval price
- Requires a minimum storage duration of 30 days.
- Long-term storage, backup

**S3 One Zone-Infrequent Access (S3 One Zone-IA):**

- Unlike S3 Standard and S3 Standard-IA, which store data in a minimum of three Availability Zones, S3 One Zone-IA stores data in a single Availability Zone and is to be 
  considered if you want to save costs on storage and you can easily reproduce your data in the event of an Availability Zone failure
- Stores data in a single AWS Availability Zone for cost savings.
- Suitable for less frequently accessed data.
- Requires a minimum storage duration of 30 days.
- Can be preferred for backups or data that can be recreated.

**S3 Intelligent-Tiering:**

- Amazon S3 monitors an objects access patterns and if it isn’t accessed for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier which is S3 
  Standard-IA. If you access an object in the S3 Standard-IA Amazon S3 automatically moves it to the frequent access tier which is S3 Standard
- Ideal for data with unknown or changing access patterns
- Requires a small monthly monitoring and automation fee per object

**S3 Glacier Instant Retrieval:**

- Retrieve objects stored in the S3 Glacier Instant Retrieval storage class within milliseconds, with the same performance as S3 Standard. Works well for archived data that 
  requires immediate access
- Used for archiving purposes.
- Provides fast data retrieval but at a higher cost.
- Works well for archived data that requires immediate access
- Can retrieve objects within a few milliseconds

**S3 Glacier Flexible Retrieval:**

- Used to archive data that we need to be stored over a long period of time and doesn’t need to be retrieved very rapidly (1 minute to 12 hours). You can simply move data to it or 
  create vaults and then populate them with archives. If you have compliance requirements around retaining data e.g. for a certain period of time, you can employ an S3 Glacier 
  vault
- Low-cost storage designed for data archiving
- Able to retrieve objects within a few minutes to hours

**S3 Glacier Deep Archive:**

- Supports long-term retention and digital preservation for data that might be accessed once or twice in a year. The objects stored are replicated and stored across at least three 
  geographically dispersed AZs and it’s the lowest-cost storage in the AWS Cloud
- Lowest-cost archival storage class.
- Suitable for long-term archiving and rarely accessed data.
- Provides data retrieval within 12 to 48 hours.

**S3 Outposts:**

- S3 run on-premises using AWS Outposts service.
- Provides access to AWS services in your local data center.
- Offers local storage to keep storage costs low.

<aside>
💡 Amazon S3 Transfer Acceleration helps to read and write data to Amazon S3 over long geographic distances with low latency.
</aside>


## S3 pricing is based on four factors

1. Total amount of data (in GB) stored on S3
2. Storage class (S3 Standard, S3 Intelligent-Tiering, S3 Standard-Infrequent Access, S3 One Zone-IA, S3 Glacier, or S3 Glacier Deep Archive)
3. Amount of data transferred out of AWS from S3
4. Number of requests to S3



## Amazon S3 Policies

![Image8](./images/img8.png)

- **Action***: Specifies S3 operations that are allowed or denied (e.g. s3:PutObject, s3:GetObject).
- **Effect***: Indicates the permission decision; usually takes the values "Allow" or "Deny".
- **Resource**: Identifies the S3 resources (bucket or object) to which permission is applied or not.
- **Principal**: Specifies the AWS accounts or users to which the permission policy applies.
- **Sid (Optional)** – Include an optional statement ID to differentiate between your statements.
- **Condition (Optional)** – Specify the circumstances under which the policy grants permission.

## Amazon Relational Database Service (RDS)

- Managed Databases
- **Multiple Database Engines:** It supports various database engines like MySQL, PostgreSQL, Oracle, SQL Server, and MariaDB.
- **Automated Backups:** enabling point-in-time recovery.
- **Scalability:** Easily scale compute and storage resources to handle increased demand.
- **High Availability:** Multi-AZ deployment provides failover capability for enhanced availability.
- AWS managed Amazon Relational Database Service (Amazon RDS) instance performance is better than a customer managed database instance

**AWS is responsible for:**

- Managing the underlying infrastructure and foundation services.
- Managing the operating system.
- Database setup.
- Patching and backups.

**The customer is still responsible for:**

- Protecting the data stored in databases (through encryption and IAM access control).
- Managing the database settings that are specific to the application.
- Building the relational schema.
- Network traffic protection.

## AWS Database Migration Service (DMS)

- AWS DMS allows you to easily move your databases to the AWS cloud, from AWS to other platforms, or between different database types.
- Supports both heterogeneous (e.g., Oracle to MySQL) and homogeneous (e.g., MySQL to MySQL) database migrations.
- It allows you to migrate with minimal interruption by ensuring that your source database continues to operate during migration.
- It also facilitates data synchronization between the source and target database by continuously replicating database data.
- When used with AWS Schema Conversion Tool, it helps you automatically convert database schemas from one database platform to another.

## **AWS Identity and Access Management (IAM)**

IAM gives you the flexibility to configure access based on your company’s specific operational and security needs. You do this by using a combination of IAM features, which are explored in detail in this lesson:

- IAM users, groups, and roles
- IAM policies
- Multi-factor authentication
1. **User**:
    - Directly associated with an identity in an AWS account.
    - It can directly access AWS services with its own access keys and passwords.
    - Usually created for real people or applications.
    - These users can be assigned specific permissions or certain policies can be applied to them.
    - For example, you can create an AWS user for an application and give that user access only to the S3 bucket.
2. **User Group**:
    - Used to organize and manage multiple AWS users.
    - Ideal for grouping users with common permissions.
    - A policy or permission assigned to a group is automatically assigned to all users in that group.
    - For example, if you want to give the same access permissions to all developers, you can group them in a single "Developer" group.
3. **Role**:
    - It is not directly associated with an ID or password, so it cannot be used to log in directly.
    - It is used to transfer permissions to another AWS service or user for a certain period of time.
    - It is frequently used to grant applications running on EC2 instances access to AWS services that these instances need.
    - When an AWS service needs access to another service, a role is used to provide this access securely.
    - For example, if you want an EC2 instance to write data to the S3 bucket, you can create a role for this EC2 instance and grant S3 write permissions to this role.


## Root User

- Create, manage, and close AWS accounts.
- Create and manage IAM (Identity and Access Management) users and groups.
- Create and manage IAM roles.
- Provide full access to all AWS services and resources.
- Manage billing, payments, and account details.
- Modify security settings and IAM policies.
- Manage security and auditing services like AWS CloudTrail and AWS Config.
- Change account name


## AWS Artifact

- AWS Artifact aims to provide access to **security and compliance documentation** and reports for AWS accounts. You can use these documents to support security controls and compliance requirements.
- AWS Soc & PCI reports download


## AWS GuardDuty

- GuardDuty is used to automatically detect **malicious activities and threats** in your AWS accounts.
- Monitors security threats using **anomaly-based detection** techniques and provides **real-time** alerts.
- Can detect threats such as identity theft, network attacks and behavioral analysis.
- Quickly detects potential threats with threat data and behavioral analysis.

![image](https://github.com/user-attachments/assets/e704d342-78ce-40ca-a302-4040773553e0)


## AWS Shield

- Prevents DDOS attack
- AWS Shield which protects against Distributed Denial of Service (DDoS) attacks is available globally on Amazon CloudFront Edge Locations.
- Amazon EC2, Elastic Load Balancing (ELB), Amazon CloudFront, Amazon Route 53, AWS Global Accelerator provide automatic ddos protection.

## AWS WAF

- Web Application Protection
- Rule Creation
- Rate Limiting
- Managed Rules
- Real-time Metric
- Global Reach
- Block IP Addresses
- SQL Injection
- Provides protection at Layer 7

![image](https://github.com/user-attachments/assets/76a4b0ca-192c-48fe-83db-c96f253662d0)

## Layers

- **Layer 3** - Layer 3 is the Network layer and this layer decides which physical path data will take when it moves on the network. AWS Shield offers protection at this layer.
- **Layer 4** - Layer 4 is the Transport layer and this layer data transmission occurs using TCP or UDP protocols. AWS Shield offers protection at this layer.
- **Layer 7 -** HTTP and HTTPS requests are part of the Application layer, which is layer 7.

## Customer Compliance Center

- AWS answers to key compliance questions
- An overview of AWS risk and compliance
- An auditing security checklist

## Amazon CloudWatch

- Monitoring and management service for AWS resources.
- Collects and tracks metrics, logs, and events.
- Provides insights into application and infrastructure performance.
- Enables automated actions based on defined alarms.
- Amazon CloudWatch logs are encrypted by default using AWS Key Management Service (KMS).
- CloudWatch Logs allows you to collect and store logs from your AWS infrastructure in a central location, Logs Streams represent source-based sequential streams of these logs. CloudWatch Logs Insights is a query and analysis tool that makes it easier for you to dive deeper into these logs and analyze them.


## AWS CloudTrail

- Logging and auditing service for AWS accounts.
- Records API calls and actions made within your account.
- Provides a trail of events for security and compliance analysis.
- Helps in tracking changes, identifying potential security risks, and troubleshooting.

![image](https://github.com/user-attachments/assets/1598b7ae-fd0b-4296-8d7b-b4063768112b)


## AWS Trusted Advisor

- Provides best practice recommendations to help optimize your AWS resources.
- Offers control in four categories: cost optimization, performance, security and fault tolerance.
- Helps reduce operating costs, improve performance and keep systems safe.
- Provides the ability to directly perform suggested actions by clicking on specific suggestions.
- Provides some basic checking for free for all AWS customers, but Business or Enterprise support plans may be needed for further advice.
- Detects security vulnerabilities.
- Helps you optimize your AWS accounts to reduce costs.
- Monitors service quotas and warns when they are exceeded.
- Can monitor in real time and give suggestions.

## AWS Billing Dashboard

- Compare your current month-to-date balance with the previous month, and get a forecast of the next month based on current usage.
- View month-to-date spending by service.
- View Free Tier usage by service.
- Access Cost Explorer and create budgets.
- Purchase and manage Savings Plans.

## AWS **Consolidated Billing**

- One bill
- Easy tracking
- No extra fee
- **Combined usage** – You can combine the usage across all accounts in the organization to share the volume pricing discounts, Reserved Instance discounts, and Savings Plans. This can result in a lower charge for your project, department, or company than with individual standalone accounts.

## AWS Budgets

- Monitoring and cost management service in AWS.
- Helps track and manage spending on AWS resources.
- Set custom spending limits and receive alerts when thresholds are reached.
- Provides real-time insights into usage, costs, and forecasts.
- Enables proactive cost control and optimization.

## AWS Pricing Calculator

- Online tool to estimate AWS service costs.
- Helps plan and budget for AWS usage.
- Offers a user-friendly interface to configure services and resources.
- Provides cost breakdowns based on selected configurations.
- Allows comparison of different pricing options.
- Aids in understanding potential expenses before deploying resources.

## AWS Cost and Usage Report (CUR)

- The **Cost and Usage Report** is your one-stop shop for accessing the most granular data about your AWS costs and usage. You can also load your cost and usage information into Amazon Athena, Amazon Redshift, AWS QuickSight, or a tool of your choice.
- Access comprehensive AWS cost and usage information
- Track your Amazon EC2 Reserved Instance (RI) usage
- Leverage strategic data integrations
- Usage and view the discounted RI rate
- Used to analyze AWS costs and usage in detail.
- Can create hourly detailed reports and store these reports in S3 bucket.
- Helps you track, analyze and plan AWS costs.
- Allows analysis by tags.

## AWS Cost Explorer

- **Cost analysis and visualization tool in AWS.**
- Provides detailed insights into AWS usage and spending.
- Allows filtering and grouping of cost data based on various dimensions.
- Offers historical and forecasted cost information.
- Helps in optimizing costs and making informed decisions.
- **Comments about the future by looking at the past.**
- Monthly expenses can be visualized
- Can calculate estimated expenses for 12 months with high accuracy

## AWS Support Plans

![Image9](./images/img9.png)

![Image10](./images/img10.png)

![image](https://github.com/user-attachments/assets/14ee71cb-d0e3-4692-a834-2ef3348d7dd0)


### Basic Support

- **Customer Service and Communities** - 24x7 access to customer service, [documentation](https://docs.aws.amazon.com/), [whitepapers](https://aws.amazon.com/whitepapers/), and [AWS re:Post.](https://www.repost.aws/)
- **[AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/)** Access to core Trusted Advisor [checks](https://docs.aws.amazon.com/awssupport/latest/user/trusted-advisor-check-reference.html) and guidance to provision your resources following best practices to increase performance and improve security.
- **[AWS Personal Health Dashboard](https://aws.amazon.com/premiumsupport/technology/personal-health-dashboard/)** - A personalized view of the health of AWS services, and alerts when your resources are impacted.
- No Technical support

### Developer Support

- Best practice guidance
- Client-side diagnostic tools
- Building-block architecture support, which consists of guidance for how to use AWS offerings, features, and services together
- Technical support within business days (12 hour response time)
- Technical support through Chat

### Business Support

- Use-case guidance to identify AWS offerings, features, and services that can best support your specific needs
- All AWS Trusted Advisor checks
- Limited support for third-party software, such as common operating systems and application stack components
- Technical support with 24/7 phone and email access (1 hour response time)
- Unlimited access to AWS Consultants
- AWS Business Priority Support Plan (ISM)
- Technical support through phone calls

### Enterprise On-Ramp Support

- A pool of Technical Account Managers to provide proactive guidance and coordinate access to programs and AWS experts
- A Cost Optimization workshop (one per year)
- A Concierge support team for billing and account assistance
- Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard
- Consultative review and architecture guidance (one per year)
- Infrastructure Event Management support (one per year)
- Support automation workflows
- 30 minutes or less response time for business-critical issues


### Enterprise Support

- A designated Technical Account Manager to provide proactive guidance and coordinate access to programs and AWS experts
- A Concierge support team for billing and account assistance
- Operations Reviews and tools to monitor health
- Training and Game Days to drive innovation
- Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard
- Consultative review and architecture guidance
- Infrastructure Event Management support
- Cost Optimization Workshop and tools
- Support automation workflows
- 15 minutes or less response time for business-critical issues
- Technical Account Manager (TAM)
- Enfrastructure Event Management (IEM) 


## Infrastructure Event Management (IEM)

- AWS's dedicated support service for large-scale events or application launches.
- AWS support engineers work closely to support the customer's AWS infrastructure in the planning, preparation and operation phases.
- Assists in scaling, configuring and optimizing infrastructure to maximize the success of the event.
- Provides in-depth monitoring and reporting during and after the incident.
- Designed specifically for launches of critical workloads or major promotions and events.


## Technical Account Manager (TAM)

- Dedicated technical advisor in AWS.
- Offers personalized support and guidance for strategic accounts.
- Helps with architectural design, optimization, and best practices.
- Assists in troubleshooting, performance improvements, and issue resolution.
- Acts as a liaison between customers and AWS support teams.
- Aims to enhance the customer's AWS experience and success.


## AWS Marketplace

AWS Marketplace is a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS.


## AWS Cloud Adoption Framework (CAF)

![Image11](./images/img11.png)

![Image12](./images/img12.png)


1. **Business Perspective:**
     - Purpose: Understand how business value is created and determine how cloud adoption contributes to the organization's business goals.
     - Focus Points: Business objectives, risk management, opportunities and ROI (return on investment).
2. **People Perspective:**
     - Purpose: Aligning the organization's skills and capacities with cloud services.
     - Focus Points: Training, defining new roles, building teams and continuing education and learning.
3. **Governance Perspective:**
     - Purpose: Aligning business processes and IT governance with cloud services.
     - Focus Points: Risk management, cost reduction, license management, compliance, process improvements and control mechanisms.
4. **Platform Perspective:**
     - Purpose: Design and implement cloud infrastructure and architecture in line with business needs and objectives.
     - Focus Points: Infrastructure design, service selection, architectural best practices and application migration.
5. **Security Perspective:**
     - Purpose: Meeting security and compliance requirements.
     - Focus Points: Identity and access management, data protection, network security and compliance requirements.
6. **Operations Perspective:**
     - Purpose: To manage and operate cloud resources and services effectively and efficiently.
     - Focus Points: Automation, monitoring, reporting, incident management, and continuous integration and continuous delivery (CI/CD) processes.
     -Observability
     - Event management (AIOps)
     - Incident and problem management
     - Change and release management
     - Performance and capacity management
     - Configuration management
     - Patch management
     - Availability and continuity management
     - Application management

## **6 strategies for migration**

**Rehosting** 

- Migrating applications to the Cloud as is, with minor changes.
- Also known as "lift and shift."
- Moving applications as-is to the cloud.
- Minimal changes to the application.
- Provides quick migration with minimal disruption.

**Replatforming:**

- Leveraging performance and scalability by integrating applications with the cloud. Code changes can also be made here.
- Making some optimizations during migration.
- Adapting applications to take advantage of cloud services.
- May involve some code or configuration changes.
- Improves application performance and scalability.

**Refactoring/Re-architecting:**

- Go cloud-native for maximum scalability. This involves extensive code and architectural changes.
- Redesigning applications to be cloud-native.
- Extensive code changes and architecture modifications.
- Utilizes cloud services and modern best practices.
- Offers maximum scalability, efficiency, and innovation.

**Repurchasing:**

- Replacing existing software with cloud alternatives. Manage applications with less hassle by creating SaaS.
- Replacing existing software with cloud-based alternatives.
- Adopting software-as-a-service (SaaS) solutions.
- Requires minimal development effort.
- Often results in improved features and reduced maintenance.

**Retaining:**

- Keeping existing applications in their current state because they are legacy.
- Keeping certain applications in their current state.
- Typically for applications not suitable for migration.
- Could involve legacy or proprietary software.

**Retiring:**

- Gradually removing unneeded services to reduce operational load and budget.
- Phasing out applications or services.
- Discontinuing resources that are no longer needed.
- Helps streamline operations and reduce costs.

## **AWS Snow Family Members**
  Powerful tool for customers who need to transfer large amounts of data into or out of AWS securely and efficiently. The rule of thumb to follow with snow is that if it takes more than a week to transfer data over a network, use snow family devices.

**AWS Snowcone:**

![image](https://github.com/user-attachments/assets/2be878f1-eddf-44ad-8aa6-7aa322908a78)


- Small, rugged, and portable edge computing and data transfer device.
- Designed for collecting, processing, and transporting data from remote or disconnected environments.
- Suitable for scenarios with limited space and power constraints.
- Provides data encryption and secure transfer to AWS.
- It features 2 CPUs, 4 GB of memory, and up to 14 TB of usable storage.****

**AWS Snowball:**

![image](https://github.com/user-attachments/assets/73700d16-fceb-4eaa-8fab-4f37cecc20a9)


- Data migration and transport device for large amounts of data.
- Available in two sizes: Snowball and Snowball Edge.
- Helps transfer data physically to and from AWS data centers.
- Suitable for offline data transfers and overcoming network limitations.
- Storage: 80 TB
- Compute: 40 vCPUs, and 80 GiB
- **Snowball Edge Storage Optimized ⇒** well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs.
- **Snowball Edge Compute Optimized ⇒** provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks.

**AWS Snowmobile:**

- Massive data migration solution for exabyte-scale datasets.
- Uses a shipping container-sized data transfer truck.
- Transfers large datasets to AWS securely and efficiently.
- Designed for extremely large-scale data transfer needs.
- You can transfer up to 100 petabytes of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.****

## AWS AI

- Amazon CodeWhisperer ⇒ Get code recommendations while writing code and identify security issues in your code.
- Amazon Transcribe ⇒ Convert speech to text.
- Amazon Polly ⇒ Text to Speech
- Amazon Fraud Detector ⇒ Identify potentially fraudulent online activities.
- Amazon Lex ⇒ Build voice and text chatbots
- Amazon Personalize ⇒ Allows developers to quickly build and deploy curated recommendations and intelligent user segmentation at scale using machine learning (ML).
- AWS Rekognition ⇒ Computer Vision which focuses on enabling computers to identify and understand objects and people in images and videos
- Amazon **Comprehend** is a natural language processing (NLP) service offered by Amazon Web Services (AWS). This service analyzes text data, making it easy to gain in-depth information about content and use this data in various applications
- **Amazon Kendra** is a machine learning-powered enterprise search service from AWS. This service allows companies to easily discover their content through natural language searches.

## **The AWS Well-Architected Pillars Framework**

![Image13](./images/img13.png)

### Operational excellence

- The operational excellence pillar includes the ability to run and monitor systems to deliver business value and to continually 
improve supporting processes and procedures. Key topics include automating changes, responding to events, and defining standards 
to manage daily operations.
- Perform operations as code
- Make frequent, small, reversible changes
- Refine operations procedures frequently
- Anticipate failure
- Learn from all operational failures
- IaaS

### Security


- The security pillar includes the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies. Key topics include confidentiality and integrity of data, managing user permissions, and establishing controls to detect security events.
- Implement a strong identity foundation
- Enable traceability
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Keep people away from data
- Prepare for security events

### Reliability

- The reliability pillar includes the ability of a system to recover from infrastructure or service disruptions, dynamically acquire computing resources to meet demand, and mitigate disruptions such as misconfigurations or transient network issues. Key topics include distributed system design, recovery planning, and adapting to changing requirements.
- Recover from infrastructure or service disruptions
- Dynamically acquire computing resources to meet demand
- Mitigate disruptions such as misconfigurations or transient network issues
- Testing recovery procedures
- Scaling horizontally
- Increase aggregate system availability
- Automatically recovering from failure
- Stop guessing capacity

### Performance Efficiency

- The performance efficiency pillar includes the ability to use computing resources efficiently to meet system requirements. Key topics include selecting the right resource types and sizes based on workload requirements, monitoring performance, and making informed decisions to maintain efficiency as business needs evolve. Key topics include selecting resource types and sizes optimized for workload requirements, monitoring performance, and maintaining efficiency as business needs evolve.
- Architecture includes experimenting more often
- Using serverless architectures
- Designing systems to be able to go global in minutes
- Go global in minutes
- Experiment more often

### Cost Optimization

- The cost optimization pillar includes the ability to avoid or eliminate unneeded cost or sub-optimal resources. Key topics include understanding spending over time and controlling fund allocation, selecting resources of the right type and quantity, and scaling to meet business needs without overspending.
- Adopt a consumption model
- Analyzing and attributing expenditure
- Using managed services to reduce the cost of ownership
- Implement cloud financial management

### Sustainability

- The discipline of sustainability addresses the long-term environmental, economic, and societal impact of your business activities. Your business or organization can have negative environmental impacts like direct or indirect carbon emissions, unrecyclable waste, and damage to shared resources like clean water. When building cloud workloads, the practice of sustainability is understanding the impacts of the services used, quantifying impacts through the entire workload lifecycle, and applying design principles and best practices to reduce these impacts. Key topics include a shared responsibility model for sustainability, understanding impact, and maximizing utilization to minimize required resources and reduce downstream impacts. 
- Understand your impact
- Establish sustainability goals
- Maximize utilization
- Anticipate and adopt new, more efficient hardware and software offerings
- Use managed services
- Reduce the downstream impact of your cloud workloads

## AWS Professional Services

- AWS Professional Services provides consulting and support services to help customers achieve specific business outcomes using AWS's cloud services. This service offers bespoke consulting services to help businesses optimize their migration to AWS, build new solutions in accordance with best practice guidelines, and learn how to best use AWS infrastructure. In addition to public cloud adoption, AWS Professional Services contributes to several specialized practice areas for payment.

## AWS Concierge Support

1. **Customized Support:** Provides customers with one-on-one guidance and advice on using AWS's cloud services.
2. Focused on Business Needs
3. Proactive Recommendations
4. Special Events and Trainings
5. Customer Relationship Management

## AWS Enterprise Support

1. **Comprehensive Support:** Provides support for large and complex AWS infrastructures of large enterprises.
2. 7/24 Technical Support
3. Infrastructure Event Management (IEM)
4. Technical Consultancy
5. Education and Learning
6. Access to Advanced Tools
7. AWS concierge (resource dedicated to a answering billing and account questions) is provided


## AWS Config

- Detects configuration changes and incompatibilities in AWS resources, thus facilitating security and compliance management.
- Saves changes in real time.
- Stores saved configurations in AWS S3.
- Visually presents the relationships between resources.
- Indicates resources that do not comply with the specified rules.
- Sends change alerts and notifications.
- Constantly checks for security and compliance.
- Allows reviewing historical configuration history.
- Accessed via AWS Management Console, AWS CLI, or SDKs.
- Generates configuration history reports for the desired time interval.

![image](https://github.com/user-attachments/assets/46ca22d0-38a4-4124-b0fd-671d7aa22929)



## AWS CloudEndure

- It is a disaster recovery solution offered by AWS.
- Replicates applications to cloud environments, different clouds or different regions within the same cloud.
- Offers low RTO (Target Recovery Time) and RPO (Target Recovery Point).
- Replicates application data in real time.
- Automatically converts different source types.


## AWS Security Hub

- It is AWS's central security and compliance service.
- Aggregates security alerts and check results from multiple AWS services.
- Automates security and compliance checking across AWS accounts.
- Provides information from predefined compliance standards.
- Provides users with a comprehensive view of security threats and vulnerabilities.
- Has the ability to prioritize alerts and findings.
- Works integrated with other AWS security services.
- Can react to events with customizable and automatable responses.
- Continuously monitors the security status of assets in AWS.
- Shows the security profile in your AWS environment in a central dashboard.
![image](https://github.com/user-attachments/assets/a277eced-279b-4eb2-a14d-33ddadd487f1)



## AWS Proton

- Amazon Proton is AWS's fully managed deployment service for container-based and serverless applications.
- It facilitates collaboration between application owners and deployment engineers, making tasks such as creating deployment templates and automated service deployment simple and repeatable.
- Enables fast and secure deployments by automating live updates and configurations of applications and infrastructure.


## AWS Batch

- Automatically plans and executes large-scale batch processing tasks.
- Dynamically scales jobs with different CPU and memory requirements.
- It is a regional service.
- Supports cost-optimized resource allocation, i.e. selects the most appropriate EC2 resource type at affordable cost.
- It works integrated with AWS, so it can easily interact with other services.
- Automatically retries failed jobs, ensuring workloads are completed.
- Provides cost savings by using Spot Instances, so jobs can be run more economically.


## AWS Systems Manager

- Allows you to view and manage your AWS resources in a central interface.
- Capable of automatically executing operational tasks (e.g. automatic deployment of the patch).
- Provides secure access to remote EC2 instances, no password or SSH key required.
- With its configuration management feature, it allows you to protect and maintain the desired configurations.
- You can get detailed information about the systems with the ability to collect inventory at any time.
- You can automate the patching of the OS used in an EC2 instance
- Streamlines automation tasks between Amazon EC2 and on-premises machines.

![image](https://github.com/user-attachments/assets/93f61c31-7252-4042-a02e-4cdd0b7e9307)


## AWS Systems Manager - Parameter Store

- Securely stores and manages configuration data, passwords and other confidential information in a central location.
- Tracks configuration changes thanks to the version control feature.
- Provides authentication and authorization by integrating with AWS Identity and Access Management (IAM).
- Integrates with AWS Key Management Service (KMS) and ensures encryption of sensitive data.
- Allows applications and services to dynamically pull configuration data.
- Provides easy integration with other services within the AWS ecosystem.


## AWS Systems Manager - Session Manager

- Allows you to connect to EC2 instances and on-premises machines directly from the AWS Management Console without a browser-based management console or routing tools such as SSH or RDP.
- It simplifies system administrators' interaction with instances in a secure and auditable manner.
- You can record all session activities and access these records via AWS CloudTrail, providing audit traceability.
- You can control which instances users and roles can interact with with AWS Identity and Access Management (IAM) policies.
- Allows users to securely access the machine without needing open SSH/RDP ports or any other means of routing.


## AWS Systems Manager - Patch Manager

AWS Systems Manager helps you select and deploy operating system and software patches automatically across large groups of Amazon EC2 or on-premises instances. Through patch baselines, you can set rules to auto-approve select categories of patches to be installed, such as operating system or high severity patches. Systems Manager helps ensure that your software is up-to-date and meets your compliance policies.

## AWS Load Balancer

1. **Application Load Balancer (ALB)**:
     - It operates at Layer 7 (Application Layer) and is best for balancing HTTP/HTTPS traffic.
     - Application Load Balancer (ALB) supports HTTPS by default for encrypted connections.
     - Example: When your web application needs to redirect to different microservices, you can perform URL path based redirection using ALB.
2. **Network Load Balancer (NLB)**:
     - It operates at Layer 4 (Transport Layer) and is designed for TCP, UDP and TLS traffic with high performance and ultra-low latencies.
     - Example: If you have a TCP or UDP service with very high demand (e.g. an MMO game server), you can balance traffic to different server instances with NLB.
3. **Classic Load Balancer (CLB)**:
     - It can work on both layer 4 (Transport Layer) and layer 7 (Application Layer), but it is an old technology and its use in new projects is not recommended.
     - Example: If you are moving a legacy application to AWS and need a load balancer without changing your existing configuration, you can use CLB.
4. **Gateway Load Balancer (GWLB)**:
     - It operates at layer 3 (Network Layer) and is designed for network services such as virtual network equipment (VNE).
     - Example: If you have an on-premises firewall or other network equipment and plan to move them to AWS, you can route traffic to these virtual network equipment with GWLB.


## AWS GreenGrass

1. AWS Greengrass is a service designed to run cloud capabilities on local devices.
2. Greengrass enables devices to run Lambda functions locally, synchronize data, and securely communicate with each other.
3. It also supports data storage and messaging capabilities locally to be able to analyze data collected from devices and send it back to the cloud

![img14](./images/img14.png)

## AWS Partner Network (APN) Technology Partners

💡 **APN Technology Partners** provide software solutions that are either hosted on or integrated with the AWS platform. Technology Partners include Independent Software Vendors (ISVs), SaaS, PaaS, developer tools, management, and security vendors.

- They represent technology-based companies; such as software manufacturers, platform providers and companies offering SaaS, PaaS, IoT and security solutions.
- They develop technological products and services that complement or extend the solutions AWS offers to customers.
- They offer applications and integration tools specific to AWS infrastructure.
- They often offer their solutions to customers on AWS Marketplace.
- They have the ability to create products with deep integration with AWS.
- Technology Partners often increase their compatibility with AWS through the APN Navigate program.

## AWS Partner Network (APN) Consulting Partners

💡 **APN Consulting Partners** are professional services firms that help customers of all sizes design, architect, migrate, or build new applications on AWS. Consulting Partners include System Integrators (SIs), Strategic Consultancies, Resellers, Digital Agencies, Managed Service Providers (MSPs), and Value-Added Resellers (VARs).

- Represents companies that provide professional services; system integrators, consulting firms, agencies and other companies providing IT consulting services.
- They assist customers in using AWS; this may include services such as onboarding, training, migration and project management.
- They are experts in the implementation and integration of AWS solutions.
- They guide customers in optimizing and managing AWS costs.

## AWS Inspector

- AWS Inspector is a service that automatically evaluates the security and compliance of your applications on AWS.
- This service scans your applications and identifies potential security vulnerabilities and compatibility issues.
- Creates reports and makes suggestions about detected vulnerabilities and incompatibilities.

## AWS Athena

1. It is a serverless query service; so no infrastructure management is required.
2. It allows running SQL queries on data stored in S3.
3. The payment structure is based on the amount of data crawled by the query being run.
4. It integrates with Presto and offers ANSI SQL support, so you can create complex queries.
5. Supports CSV, JSON, ORC ...
6. It can integrate with AWS Glue, so you get data cataloging and management capabilities.

## AWS Cognito User Pool

1. Provides login and registration functions for users.
2. Allows to include social identity providers and SAML-based identities.
3. Used to manage personal details, passwords and groups.
4. Supports security features such as multi-factor authentication (MFA) and password policies.
5. Provides authentication and authorization information with JWT tokens.

## AWS Cognito Identity Pool

1. Provides temporary AWS identities to authenticated and unauthenticated users.
2. Supports merging identities from various identity providers.
3. Provides users with direct access to AWS services.
4. Cognito User Pools accept identities from social identity providers and private identity providers.
5. Offers integration with IAM roles for role-based access control.
6. Supports login with providers such as Google, Facebook.

## AWS Single Sign-On (SSO)

1. Provides access to AWS and business applications with a single sign-on.
2. Manages user access and authorization in a central location.
3. Provides SSO capabilities across multiple AWS accounts and business applications.
4. Integrates with AWS Organizations and can configure SSO for accounts across the entire organization.
5. Supports integration with third-party identity providers such as Azure AD.

## AWS AppSync

1. It is a GraphQL service that facilitates data querying and manipulation for your applications.
2. Offers real-time data synchronization and offline access features.
3. Integrates with various data sources (RDS, DynamoDB, Lambda).
4. It can automatically create data schemas and generate compatible queries.
5. Optimizes cost thanks to the pay-per-request model.

## Services permitted for testing

AWS customers are allowed to carry out security assessments and penetration tests against their AWS infrastructure without prior approval for 15 services (no need to memorize these services):

- Amazon EC2 instances, WAF, NAT Gateways, and Elastic Load Balancers
- Amazon RDS
- Amazon CloudFront
- Amazon Aurora
- Amazon API Gateways
- AWS AppSync- fully managed service that allows you to build scalable GraphQL APIs. It provides a way to query and manipulate data using GraphQL queries and mutations.
- AWS Lambda and Lambda Edge functions
- Amazon Lightsail resources
- Amazon Elastic Beanstalk environments
- Amazon Elastic Container Service
- AWS Fargate
- Amazon Elasticsearch
- Amazon FSx
- Amazon Transit Gateway
- S3 hosted applications (targeting S3 buckets is strictly prohibited)

## AWS Global Services

1. Amazon Route 53
2. AWS Identity and Access Management (IAM)
3. AWS CloudFront
4. AWS WAF (Web Application Firewall)
5. AWS Shield
6. AWS Organizations
7. AWS Certificate Manager- service that lets you easily provision, manage, and deploy SSL/TLS certificates for use with AWS services and your internal connected resources. it is used to secure websites, internal commincations and for IoT Device Security. It features:
    Automatic certificate provisioning, certificate renewal and certificate renewing 
    Intergration with various AWS services such as Elastic Load Balancing, Amazon CloudFront, and AWS Elastic Beanstalk
    ACM can issue both public certificates for securing internet-facing resources and private certificates for securing internal resources.
9. Amazon WorkSpaces- fully managed, secure Desktop-as-a-Service (DaaS) solution. It allows you to provision Windows or Linux desktops in just a few minutes and quickly scale to provide thousands of desktops to workers across the globe. It is secure with data encrypted both at rest and in transit, easily scalable as you can scale up or down based on the number of users and it intergrates with other services such as AWS Directory Service for user management and Amazon WorkDocs for file storage and sharing. Common use cases:
    Remote work. Enables employees to access their desktops from anywhere, ensuring business continuity
    Quickly provision desktops for temporary or seasonal workers without the need for physical hardware.
    Bring Your Own Device. Provide employees with isolated and scalable environments

## AWS Zonal Services

1. Amazon EC2
2. Amazon RDS
3. Amazon Elastic Block Store (EBS)
4. Amazon ElastiCache- fully managed in-memory data store and cache service that supports Redis (Known for its rich set of features, including support for complex data structures, persistence, replication, and high availability. It’s ideal for use cases like real-time analytics, messaging, and caching) and Memcached ( simpler, high-performance, distributed memory object caching system. It’s great for use cases that require simple key-value stores, such as caching database query results, session stores, and more). It improves the performance of web applications by allowing you to retrieve information from fast, managed, in-memory caches instead of relying entirely on slower disk-based databases. It can be automatially scaled depending on demand, is highly available and it supports backup and recovery with point-in-time recovery. This service provides an in-memory data store and cache, which can significantly reduce the load on your databases by storing frequently accessed data
5. Amazon VPC
6. Amazon Redshift- fully managed, petabyte-scale data warehouse service in the cloud. It allows you to run complex queries against structured data using SQL-based tools and business intelligence applications. It is easily scalable as you can scale your Redshift cluster up or down based on your performance and storage needs, it seamlessly intergrates with AWS services such as S3, DynamoDB and Kinesis for data ingestion and processing, it has automated Backups and Restores through snapshots and backups to S3 and it secure as has support for VPC and IAM and performs ecnryption at rest and in transit

## Decouple From the Data Center  Benefits

- **Decrease your TCO**: Eliminate many of the costs related to building and maintaining a data center or colocation deployment. Pay for only the resources you consume.
- **Reduce complexity**: Reduce the need to manage infrastructure, investigate licensing issues, or divert resources.
- **Adjust capacity on the fly**: Add or reduce resources, depending on seasonal business needs, using infrastructure that is secure, reliable, and broadly accessible.
- **Reduce time to market**: Design and develop new IT projects faster.
- **Deploy quickly, even worldwide**: Deploy applications across multiple geographic areas.
- **Increase efficiencies**: Use automation to reduce or eliminate IT management activities that waste time and resources.
- **Innovate more:** Spin up a new server and try out an idea. Each project moves through the funnel more quickly because the cloud makes it faster (and cheaper) to deploy, test, and launch new products and services.
- **Spend your resources strategically:** Switch to a DevOps model to free your IT staff from operations and maintenance that can be handled by the cloud services provider.
- **Enhance security:** Spend less time conducting security reviews on infrastructure. Mature cloud providers have teams of people who focus on security, offering best practices to ensure you’re compliant, no matter what your industry.

## AWS Serverless Services

1. AWS Lambda
2. Amazon API Gateway- fully managed service that enables you to create, publish, maintain, monitor, and secure APIs at any scale. It acts as a front door for applications to access data, business logic, or functionality from your backend services. It commonly used for Exposing backend services to the internet, Building serverless applications with AWS Lambda and Creating APIs for mobile and web applications. Key Features:
    API Creation and Management. You can create RESTful APIs, WebSocket APIs, and HTTP APIs.
    It automatically scales to handle a large numbers of API requests
    Supports authentication and authorization through AWS IAM, Lambda authorizers, and Amazon Cognito.
    Integrates with Amazon CloudWatch for logging and monitoring API performance.
4. AWS Step Functions- fully managed service that makes it easy to coordinate the components of distributed applications and microservices using visual workflows. Helps you build and orchestrate complex workflows and state machines in a downward step like way. Integrates with AWS services such as AWS Lambda, Amazon S3, Amazon SNS, and more. Its common use cases are Orchestrating microservices and serverless applications, Managing complex workflows and batch processing, and Implementing business processes and data pipelines. Used to perform a sequence/ automate tasks in a specific order
5. Amazon DynamoDB
6. Amazon S3
7. Amazon EventBridge- serverless events (operations and occurences e.g, EC2 carrying out computation tasks) message bus service (similar to topics in SNS and is where messages are published and received by recipient) that makes it easy to connect applications using events. It enables you to build event-driven architectures by routing events between services based on rules. You can route events from various sources to targets such as AWS Lambda, Step Functions, route messages and more. Common use cases are in Building event-driven applications and microservices, Implementing event-driven architectures with decoupled components and Integrating third-party SaaS applications with AWS services.
8. Amazon SNS (Simple Notification Service)
9. Amazon SQS (Simple Queue Service)- message queuing service that enables decoupling and scaling of microservices, distributed systems, and serverless applications. It is not designed for caching data.
10. AWS AppRunner- fully managed service that makes it easy to deploy containerized web applications and APIs at scale. It handles the infrastructure management, scaling, and operations needed to run containerized applications. It has automatic scaling and CI/CD intergration. Commonly used to Deploy web applications and APIs without managing servers, run containerized applications with automatic scaling and load balancing.
Building modern applications with continuous integration and deployment.
11. AWS Fargate- serverless compute engine for containers that works with Amazon ECS and Amazon EKS. It allows you to run containers without managing the underlying server infrastructure. It has automatic scaling. Commonly used for Running microservices and containerized applications without managing infrastructure, Implementing batch processing and data pipelines with containers and Running scalable and highly available containerized workloads.


![image](https://github.com/user-attachments/assets/f12edfb9-bb6d-4563-a60a-a63589612386)
![image](https://github.com/user-attachments/assets/c02ae2a1-fd0c-470b-9910-5125b3aab168)
## AWS CodeCommit

![image](https://github.com/user-attachments/assets/737529d9-13ec-4bfb-b89a-e5b5285f3fe0)

- Private Git based repository service.
- Provides secure and high-scale code storage.
- Integrated with AWS authentication and authorization.
- Uses triggers to track code changes.
- It runs on AWS infrastructure, which provides access to codes with low latency.

## AWS CodeStar

- AWS CodeStar is a development service that makes it easy to build the resources and CI/CD toolchain needed to quickly develop applications.
- Coding → Building > Testing → Deploying
- Provides code templates for projects and works integrated with AWS services.
- Facilitates collaboration among team members, offering capabilities to review and share code.
- Provides the opportunity to monitor the general status, activities and processes of the project in a visual interface.
- You can use AWS CodeStar and AWS Cloud9 to develop, build, and deploy a serverless web application
- Each AWS CodeStar project includes development tools, including AWS CodePipeline, AWS CodeCommit, AWS CodeBuild, and AWS CodeDeploy, that can be used on their own and with existing AWS applications

## AWS CodeDeploy

- Automatically deploys applications to services on AWS.
- Applies updates slowly, reducing the error rate.
- Updates workloads on EC2, AWS Fargate, AWS Lambda and on-premises servers.
- Supports blue/green distribution strategies.
- Enables monitoring and automatic retrieval of distribution processes.

## AWS CodeBuild

- It is a fully managed continuous integration service.
- Automatically builds, tests and packages source code.
- It uses custom build images on Docker.
- Compatible with different programming languages, platforms and tools.
- It is run in a new virtual environment where each build is isolated.

## AWS CodePipeline

- It is a continuous integration and continuous delivery (CI/CD) service.
- Enables code changes to be automatically compiled, tested and deployed to the product environment.
- Can integrate with different AWS services (e.g. CodeBuild or CodeDeploy) and third-party tools.
- AWS CodePipeline uses Amazon CloudWatch Events to detect changes in CodeCommit repositories used as a source for a pipeline

## AWS CodeGuru

- Code review and performance profiling service.
- Provides suggestions to improve the performance of applications.
- Identifies the most costly lines of applications.
- It is based on machine learning models long used at Amazon.
- Identifies code errors and risks with automatic code reviews.

## **Amazon S3 Lifecycle Policy**

1. Sets automation rules for S3 objects.
2. Allows objects to be moved or deleted after a certain period of time.
3. Used to optimize data storage costs.
4. Can automatically move items from standard S3 storage to Glacier or a cheaper storage class.
5. It frees up storage space by automatically deleting objects after a certain period of time.
6. Difference between Amazon S3 Lifecycle Policy and S3 Intelligent-Tiering:

![image](https://github.com/user-attachments/assets/fb98db58-9865-437f-b34e-321156c68a33)



## **AWS Storage Gateway**

1. It acts as a bridge between cloud-based and on-premises storage.
2. On-premises allows applications to use AWS cloud storage.
3. Offers three storage types: file gateway, volume gateway and tape gateway.
4. It is used in scenarios such as backup, archiving and data analysis.
5. Provides access to stored data with low latency.

## **AWS DataSync **

1. Its a fully managed service that simplifies, automates, and accelerates the process of moving data between on-premises storage and AWS storage services.
2. Automates the transfer of data between on-premises storage and AWS services like Amazon S3, Amazon EFS, and Amazon FSx


## **AWS Transfer Family**

1. Its a fully managed service that enables secure file transfers into and out of AWS storage services like Amazon S3 and Amazon EFS.
2. Supports Secure File Transfer Protocol (SFTP), File Transfer Protocol over SSL (FTPS) and File Transfer Protocol (FTP).
3. Provides integration with AWS scalable storage services.
4. It offers integration with AWS Identity and Access Management (IAM) for authentication.
5. Increases security with the ability to run in private VPC environments.

## AWS Chime

- AWS's communications service, used for video and audio meetings.
- Provides secure and high-quality audio/video conferencing, chat and content sharing.
- Accessible from any device and offers SDKs for integration.
- Priced according to users' usage; No prior commitment required.

## Service Types

![img15](./images/img15.png)

### **IaaS (Infrastructure as a Service)**

- Provides access to basic computing resources over the internet.
- Example AWS Services: EC2, Amazon S3, VPC.

### **PaaS (Platform as a Service)**

- Provides a platform that allows developers to create, distribute and run their applications.
- Example AWS Services: AWS Elastic Beanstalk, AWS App Runner, AWS OpsWorks.

### **SaaS (Software as a Service)**

- Completed applications delivered to users over the Internet and typically accessed through a web browser.
- Example AWS Services: Amazon Chime, AWS WorkDocs, Amazon Connect.

### **FaaS (Function as a Service)**

- It is a serverless computing model, allowing users to distribute individual functions.
- Example AWS Service: AWS Lambda.

## **AWS Lightsail**

- AWS Lightsail is a cloud computing service that allows users to quickly and easily launch virtual private servers.
- It's easier to predict costs thanks to optimized plans that come with a fixed monthly fee.
- Provides the ability to quickly launch projects with pre-configured application and development stacks.
- Private IP address provides easy access to basic features such as fixed storage, data transfer, DNS management.
- Wordpress, MySQL, Virtual Private Server, block and object storage, load balancer, CDN

## **AWS Glue**

- AWS Glue is a serverless, fully managed service for simplifying the process of discovering, preparing, and integrating data from various sources for analytics, machine learning, and application development. Basically performing ETL (Extract, Transform, Load) operations in the cloud.
- It has the ability to automatically discover data sources and create data catalogs.
- Provides direct integration with popular data stores, thus facilitating data mobility.
- It has a serverless structure and does not require any extra effort in scaling and server management.

## **AWS Macie**

- Data security service that uses machine learning and pattern matching to help you automatically discover, classify, and protect sensitive data stored in Amazon S3.
- Helps meet requirements such as compliance with personal data protection regulations.
- Powered by machine learning, this service provides insights into data at risk.
- It has the ability to identify suspicious or risky activities by analyzing user activities and API calls.

## **AWS Control Tower**

- AWS Control Tower enables you to automatically apply best practices when creating and managing multiple accounts and workloads on AWS.
- Essentially simplifies the setup and management of multi-account AWS environments.
- Allows you to create new accounts securely and compliantly using predefined "blueprints" for organizations.
- Makes it easy to track and control how users and teams use AWS services and resources.

## **AWS OpsWorks**

- Configuration management service that helps you set up, deploy, and manage applications in the cloud or on-premises. It uses Chef and Puppet to automate how servers are configured, deployed, and managed across your Amazon EC2 instances or on-premises compute environments.
- Start by creating a stack (collections of resources that you want to manage together. Think of a stack as the entire infrastructure for a specific application) in the OpsWorks console to contain all the resources needed for your application then add layers (different components of your application, such as a web server or application server and each layer can have its own configuration and set of instances) to your stack to represent different parts of your application and then add instances to run the software defined in your layers. Finally, deploy your applications to the instances in your layers. OpsWorks uses Chef recipes or Puppet manifests to automate the deployment process.
- Allows you to define how software will be installed, configured, and how tasks will be managed based on specific lifecycle events.
- The service is particularly suitable for those who want to automate configuration, management and deployment for complex application architectures.

## **AWS Transit Gateway**

- AWS Transit Gateway allows you to connect different Amazon VPCs and on-premise networks through a centralized routing service.
- It can connect thousands of VPCs and on-premises networks through a single gateway, thus it has advanced security and routing features such as monitoring traffic on your network connections and defining routing policies.
- Provides a simple and scalable solution for managing large numbers of VPCs and network connections in your organization.


## **AWS Gateways**
![image](https://github.com/user-attachments/assets/331593ce-efcb-4e84-aba4-6cfff893df31)

![image](https://github.com/user-attachments/assets/6461a74a-3be6-4327-b8f0-e2e8f6de5455)

![image](https://github.com/user-attachments/assets/6d55623c-5e30-4b66-baa4-eb362d1beae9)


## **AWS Pinpoint**

- AWS Pinpoint is a service designed to improve user interaction and communication; It analyzes users' in-app activities and helps you create targeted campaigns.
- Allows you to interact with users across various channels such as email, SMS, in-app notifications and push notifications.
- Real-time analytics features allow you to monitor and optimize user behavior and campaign effectiveness.
- Helps you increase user engagement and improve user conversion rates by creating customized messages.

## **AWS Secrets Manager**

1. Service designed to help you manage, retrieve, and rotate secrets such as database credentials, API keys, and other sensitive information
2. Securely stores your secrets using encryption keys managed by AWS Key Management Service (KMS) where they are encrypted at rest and in transit.
3. You can monitor the usage of secrets and receive alerts for any suspicious activity through intergrating with AWS CloudTrail to log all API calls, providing a detailed audit trail.
4. Periodically updating the credentials or sensitive information stored in a secret

## **AWS Service Catalog**

1. Makes it easier for organizations to define and deploy approved IT services.
2. It allows controlling the version management and lifecycle management of IT services from a central location.
3. Enables users to create AWS resources by selecting from pre-approved product and service catalogs.
4. Offers the ability to manage templates and services from a central location to optimize costs and compliance

## **AWS Service Control Policy (SCP)**

1. Provides the ability to limit permissions to AWS accounts within the organization.
2. When defined at the top level of AWS Organization, it affects all child accounts.
3. It offers the opportunity to define permissions as whitelist or blacklist.
4. When used to limit access permissions to AWS resources, SCPs combine with IAM policies to create effective permissions.

## **AWS CloudHSM**

1. Cloud-based hardware security module that allows you to generate and use your own encryption keys on AWS
2. You have full control over your HSMs, including the ability to generate, store, import, export, and manage cryptographic keys. This includes session keys, token keys, symmetric keys, and asymmetric key pairs.
3. AWS CloudHSM uses single-tenant HSMs that are FIPS 140-2 Level 3 validated, ensuring a high level of security for your cryptographic operations and meeting of regulatory and compliance requirements by providing a secure environment for key management and cryptographic operations
4. Offers customers a private, isolated HSM access.
5. You can monitor and manage your HSMs using AWS CloudTrail, Amazon CloudWatch, and other AWS management tools
6.  Ideal for managing encryption keys for applications that require high security and compliance, performing cryptographic operations such as encryption, decryption, and digital signing and meeting of regulatory requirements for data protection and key management

## **AWS Key Management Service (KMS)**

- KMS is a service that allows customers to manage their cryptographic keys and encrypt data using these keys. With KMS you can create, rotate, manage and use keys. KMS is used to provide data encryption in AWS services and applications.

## **AWS Elastic MapReduce (EMR)**

1. It is a scalable cloud computing platform for big data processing tasks.
2. It can analyze data using popular frameworks such as Apache Hadoop and Apache Spark.
3. Optimizes costs for data analysis by easily scaling workloads.
4. It can process petabytes of data quickly and securely.

## **AWS Security Team**

1. Used to communicate with AWS's security expert team.
2. Can be used to provide information about possible security breaches, weaknesses or suspicious activities.
3. Provides rapid response and resolution to critical security issues.

## **AWS Concierge team**

1. AWS Enterprise Support is a dedicated support service for its customers.
2. Used to get AWS-specific architectural advice or in-depth technical information.
3. This team provides guidance on how to best use AWS solutions.

## **AWS Abuse team**

1. Used to report issues regarding misuse of AWS resources or violations of the AWS Terms of Service.
2. May be used to report spam, phishing or other malicious activity.
3. Provides rapid response and intervention.

## **AWS Customer Service team**

1. The first point of contact for general AWS support and customer service.
2. Used for billing, account issues, or general questions about how to use AWS.
3. Provides service to ensure customer satisfaction.

## AWS Health Dashboard

- Comprehensive tool designed to provide real-time alerts and insights into the health of your AWS environment
- It comes in two main components: the AWS Health Dashboard and the AWS Personal Health Dashboard.
- Provides a global view of the health of AWS services and shows current and historical information about the status of AWS services in all regions. It is accessible to all AWS customers and includes both the Service Health Dashboard and Personal Health Dashboard.
- Proactive Notifications
- Detailed Troubleshooting Guidance

## **AWS CloudFormation**

1. It is a service that allows users to model and tune AWS resources.
2. Allows you to distribute and structure collections of resources automatically and consistently through templates.
3. Change sets feature is used to see template changes; so you can see what will change before confirming the changes.
4. It carries out resource creation, updating and deletion processes in an automatic, secure and traceable manner.

**Benefits**

1. CloudFormation allows you to model your entire infrastructure in a text file. This template becomes the single source of truth for your infrastructure. This helps you to standardize infrastructure components used across your organization, enabling configuration compliance and faster troubleshooting.
2. AWS CloudFormation provisions your resources in a safe, repeatable manner, allowing you to build and rebuild your infrastructure and applications, without having to perform manual actions or write custom scripts. CloudFormation takes care of determining the right operations to perform when managing your stack, and rolls back changes automatically if errors are detected.
3. Codifying your infrastructure allows you to treat your infrastructure as just code. You can author it with any code editor, check it into a version control system, and review the files with team members before deploying into production.
4. CloudFormation allows you to model and provision, in an automated and secure manner, all the resources needed for your applications across all regions and accounts.

## AWS Compute Services / Resource

1. Amazon EC2 (Elastic Compute Cloud)
2. AWS Lambda
3. AWS Elastic Beanstalk- fully managed service that makes it easy for developers to deploy and manage applications in the AWS Cloud without worrying about the underlying infrastructure. Elastic Beanstalk handles the deployment, scaling, monitoring, and load balancing of your applications automatically, allowing you to focus on writing code
4. Amazon EC2 Auto Scaling
5. Amazon Lightsail
6. AWS Batch
7. AWS Fargate- serverless compute engine for containers that works with both Amazon Elastic Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS). It allows you to run containers without needing to manage the underlying infrastructure. With Fargate, you focus on building and running applications while AWS manages the compute resources.
8. AWS Outposts
9. AWS ECS
10. AWS Serverless Application Repository
11. AWS Wavelength- designed to bring AWS compute and storage services to the edge of the 5G network, closer to end-users and devices. This allows developers to build applications that require ultra-low latency by deploying them within the telecommunication providers' data centers at the edge of the 5G network.
12. AWS Local Zones
13. EC2 Image Builder- simplifies the creation, maintenance, and deployment of customized and secure Amazon Machine Images (AMIs) for Amazon EC2 instances. It automates the process of building, testing, and distributing AMIs, ensuring that they are up-to-date, compliant, and configured according to your specifications.

## CapEx - OpEx

Capital expenditures (CapEx) are a company's major, long-term expenses, while operating expenses (OpEx) are a company's day-to-day expenses. Examples of CapEx include physical assets such as buildings, equipment, and machinery. Examples of OpEx include employee salaries, rent, utilities, and property taxes.

**CapEx (Capital Expenditure):**

- It refers to expenses made for long-term investments.
- For example, upfront expenses incurred to purchase company assets such as physical servers, data centers, network equipment.
- By using AWS, you can minimize such large capital expenditures because you do not need to make large upfront investments for physical infrastructure.

**OpEx (Operational Expenditure):**

- It refers to expenses incurred for daily business operations.
- Recurrent expenses such as electricity, maintenance, licenses and personnel costs.
- When using AWS, spending on managing your infrastructure can turn into OpEx because you only pay for what you use and can scale as per requirements.


## EC2 instance pricing varies depending on many variables

- The buying option (On-demand, Savings Plans, Reserved, Spot, Dedicated)
- Selected instance type
- Selected Region
- Number of instances
- Load balancing
- Allocated Elastic IP Addresses
- Auto scaling

## AWS Services Reserve Include

- EC2
- DynamoDB
- ElastiCache
- RDS
- RedShift

## **Amazon Simple Storage Service (S3) Pricing**

- **Storage class** – e.g., Standard or IA.
- **Storage quantity** – data volume stored in your buckets on a per GB basis.
- **Number of requests** – the number and type of requests, e.g., GET, PUT, POST, LIST, COPY.
- **Lifecycle transitions requests** – moving data between storage classes.
- **Data transfer** – data transferred out of an S3 region is charged.

## **AWS Partner Paths**

**1- Software Path**

The Software Path is for organizations that develop software that runs on or is integrated with AWS.

**2- Hardware Path**

The Hardware Path is for organizations that develop hardware devices that work with AWS.

**3- Services Path**

The Services Path is for organizations that deliver consulting, professional, managed, and value-added resale services.

**4- Training Path**

The Training Path is for organizations that sell, deliver, or incorporate AWS training.

**5- Distribution Path**

The Distribution Path is for organizations that recruit, onboard, and support their partners to resell and develop AWS solutions.

## AWS Outposts

1. AWS Outposts brings Amazon Web Services (AWS) cloud infrastructure, services, APIs, and tools to your own data center and lets you run them locally.
2. Provides a consistent hybrid experience both in the cloud and in your own data center.
3. It offers high data processing, data storage and analysis capabilities locally with AWS's wide range of services.

## **Amazon Cloud Directory**

1. **Description:**
     - Amazon Cloud Directory is a service that provides a scalable and flexible directory structure for a wide range of hierarchy-based data applications. It allows you to create multidimensional indexes and establish relationships between these indexes.
2. **Highlights:**
     - **Flexibility:** Ability to create custom indexes with flexible schemas for applications with multiple hierarchies.
     - **Scalability:** Scalable structure with large amount of objects and relationships.
     - **Fine-Grained Access Control:** Ability to set detailed policies to control access to content.
     - **History Tracking:** Ability to track the version history of objects and relationships within the directory.
    

## Amazon AppStream 2.0

1. Fully managed, secure application streaming service that allows you to stream desktop applications to users without requiring the applications to be installed on their local devices. This service enables users to access applications from any location and on any device, including Windows, macOS, Chromebooks, and Linux devices, by streaming the applications from the AWS cloud.
2. Amazon AppStream 2.0 is an AWS service used to publish applications on the cloud and provide access to users through their browsers.
3. It is ideal for organizations looking to support remote work, deliver software as a service, or provide access to specialized applications without the need for local installation
4. This service allows users to use applications from different devices without the need to install any software.
5. Thanks to the scalability offered, it offers seamless performance to many users at the same time.

## Amazon WorkSpaces

1. Fully managed, secure Desktop-as-a-Service (DaaS) solution. It allows you to provision Windows or Linux desktops in just a few minutes and quickly scale to provide thousands of desktops to workers across the globe. It is secure with data encrypted both at rest and in transit, easily scalable as you can scale up or down based on the number of users and it intergrates with other services such as AWS Directory Service for user management and Amazon WorkDocs for file storage and sharing..
2. Users can access these virtual desktops securely from any device.
3. It is used for businesses to manage and scale employees' computers in a centralized and secure manner.

## Amazon QuickSight

1. Cloud-based business intelligence (BI) service that enables you to visualize your data, perform analysis, and generate insights quickly and easily. It allows you to create and share interactive dashboards, reports, and visualizations, helping you make data-driven decisions. QuickSight is fully managed by AWS, meaning you don’t need to manage any infrastructure, and it can scale automatically to accommodate any number of users
2. QuickSight can connect to a wide range of data sources, including AWS services like Amazon S3, RDS, Redshift, and Athena, as well as on-premises databases, SaaS applications, and other third-party data sources.
3. Dashboards and reports created in QuickSight can be easily shared with others, either within your organization or with external stakeholders. You can set up permissions to control who can view or edit the content

## AWS Global Accelerator

1. Networking service that improves the availability and performance of your applications by directing traffic through the global AWS network infrastructure through static IP addresses that act as a fixed entry point to your application endpoints, such as Amazon EC2 instances, load balancers, or Amazon S3 buckets, across multiple AWS regions. Global Accelerator automatically routes traffic to the optimal endpoint based on health, geography, and routing policies, helping to minimize latency and maximize availability
5. AWS Global Accelerator is a good fit for non-HTTP use cases

## AWS DataPipeline

1. Amazon Data Pipeline is a web service designed to automate the movement and transformation of data.
2. This service has the ability to plan and manage data movement and transformation at regular intervals.
3. Users can define data processing workflows and automatically run these workflows at specific time intervals.

## Amazon PrivateLink

1. Amazon PrivateLink enables you to access AWS services, AWS Marketplace applications, and AWS-supported services through private connections.
2. This service keeps traffic data privately and securely in your Amazon VPC without circulating it across the internet.
3. Users can thus connect to their VPCs and on-premises environments privately and securely.

## **Amazon Detective**

- Managed security service provided by AWS that helps you analyze, investigate, and quickly identify the root cause of potential security issues or suspicious activities within your AWS environment. It automatically collects and organizes data from various AWS sources, making it easier for security teams to conduct thorough investigations without the need for manual data collection or complex queries.
- Amazon Detective automatically ingests data from various AWS services, such as AWS CloudTrail logs, Amazon VPC Flow Logs, and AWS GuardDuty findings.
- Detective integrates with other AWS security services like AWS GuardDuty, AWS Security Hub, and Amazon Macie. GuardDuty findings can be directly investigated within Detective, allowing for seamless transitions between detection and investigation

## **AWS Directory Service**

- AWS Directory Service allows organizations to manage Active Directory or LDAP-based directory services in the AWS cloud environment. This service is used to control access to organizations' cloud resources, facilitate authentication, and manage their users (Microsoft Active Directory).
- AWS Directory Service for Microsoft Active Directory, also known as AWS Microsoft AD, uses secure Windows trusts to enable users to sign in to the AWS Management Console, AWS Command Line Interface (CLI), and Windows applications running on AWS using their existing corporate Microsoft Active Directory credentials.

## **AWS Service Quotas**

- Sets limits and quotas for the use of AWS services.
- It is necessary to prevent excessive use of resources and maintain service quality.
- Helps you consider these constraints when scaling or designing your workloads.
- Offers customized quotas for each service and the possibility of increasing them on demand.
- AWS Management Console allows you to make quota requests using the AWS CLI or APIs.

## AWS Infrastructure Automation Tools

- **AWS CloudFormation**
- **AWS OpsWorks**
- **AWS Elastic Beanstalk**
- **AWS CodeStar**
- **AWS Systems Manager**
- **AWS CodeDeploy**
- **AWS Proton**
- **AWS Fargate**

## AWS Site-to-Site VPN

- AWS Site-to-Site VPN is a service that allows companies to establish a private and secure network connection between their data centers and Amazon Virtual Private Cloud (Amazon VPC). This connection is made reliably and securely over the internet using IPsec VPN tunnels.
- Virtual Private Gateway (VGW), Transit Gateway, Customer Gateway

##AmazonFSx

Amazon FSx is a fully managed service by AWS that provides file storage for workloads that require high-performance and scalable storage. Amazon FSx offers different types of file systems optimized for various use cases.

1. **Amazon FSx for Windows File Server**:
     - **Windows File Systems**: It is a fully managed, scalable and Windows compatible file storage service.
     - **SMB Protocol**: Supports the SMB (Server Message Block) protocol, which facilitates direct integration with Windows-based applications.
     - **AD Integration**: Integrates with Microsoft Active Directory, so you can use your existing authentication and access controls.
     - **Data Backup and Restore**: Provides automatic backup and easy restore features.
2. **Amazon FSx for Lustre**:
     - **High Performance**: Lustre is a popular open source file system designed for high-performance computing (HPC) workloads.
     - **For Big Data and HPC**: Ideal for HPC applications such as big data analysis, machine learning, financial modelling.
     - **Amazon S3 Integration**: FSx for Luster can directly integrate with Amazon S3. This allows you to process data from S3 directly in Luster.
     - **Scalability**: It offers scalable and extremely fast storage capacity according to your needs.
    

## AWS Application Discovery Service

- AWS Application Discovery Service is designed for businesses planning to migrate from on-premises data centers to AWS. This service automatically identifies applications, servers and their dependencies running on your existing infrastructure. This allows you to carry out the migration process in a more conscious, organized and smooth way.

## Amazon VPC Flow Logs

- Amazon VPC Flow Logs is a feature for monitoring traffic through network interfaces within Amazon Virtual Private Cloud (VPC). This traffic can be over Elastic Network Interfaces (ENI), between VPC peering connections, or over VPN connections between AWS and the customer.

## Amazon SWF

- Amazon Simple Workflow Service (Amazon SWF) is a service from AWS that helps coordinate workflow and provide state management for applications. SWF is designed for interoperable, multi-step applications with distributed components and services.

## AWS Organizations

- Centrally manage policies across multiple AWS accounts
- Govern access to AWS services, resources and regions
- Automate was account creation and management
- Consolidate billing across multiple AWS accounts
- Control access to AWS services.

## VPC Endpoint
![image](https://github.com/user-attachments/assets/2c6cb74b-8cdb-45cd-9439-967560c95f86)

AWS VPC (Virtual Private Cloud) Endpoint is a feature that provides a private connection to AWS services and VPC private resources directly from your VPC. This ensures that your access to AWS services is through Amazon's private network and not over the internet.

## VPC Endpoint Gateway

VPC Endpoint Gateway allows you to access some of Amazon's services (especially Amazon S3 and Amazon DynamoDB) from within Amazon VPC via a direct private network connection. This means accessing these services without using an internet gateway, NAT device, VPN connection, or AWS Direct Connect.

## VPC Interface Endpoint

VPC Interface Endpoint is a private network port within AWS VPC. This endpoint acts as a private Elastic Network Interface (ENI) inside your Amazon VPC and is associated with a private IP address. This allows you to establish a private connection with specific AWS services and VPC endpoint services.

## AWS Managed Key

- **AWS managed key** - AWS managed keys are KMS keys in your account that are created, managed, and used on your behalf by an AWS service integrated with AWS KMS.

## AWS Owned Key

- AWS owned keys are a collection of KMS keys that an AWS service owns and manages for use in multiple AWS accounts. Although AWS owned keys are not in your AWS account, an AWS service can use an AWS owned key to protect the resources in your account.

## DDoS Attack Protection for Web Applications

- ELB
- CloudFront
- Route 53
- Global Accelerator

## AWS Application Migration Service (MGN)

- AWS Application Migration Service makes it easy for organizations to quickly, securely and seamlessly migrate to AWS, accelerating modernization projects and reducing overall cost.

## AWS Database Migration Service (DMS)

- AWS DMS helps organizations accelerate database migration projects, reduce risk, and minimize disruption during migration. This is invaluable for companies looking to move workloads to AWS, consolidate, or switch database platforms.

## AWS Migration Hub

- AWS Migration Hub helps you maintain integrity and visibility while running multiple migration projects simultaneously. This is valuable for organizations that want to manage their migration processes simply, quickly and effectively.

## AWS CloudFront Use Cases

- Static asset caching
- Live & on-demand video streaming
- Security
- Customizable content delivery with Lambda@Edge
- Dynamic content & API acceleration
- Software distribution

## To estimate the costs of an Amazon CloudFront

- Traffic Distribution
- Requests
- Data Transfer Out

## AWS Professional Services

- AWS Professional Services combines deep expertise and practice to help organizations accelerate their cloud journeys, reduce risk, and leverage best practices.
- Dedicated Technical Account Manager (TAM)
- Fast Response Times
- Infrastructure Event Management (IEM)
- Education and Educational Resources
- Access to AWS's Extensive Tools

## AWS Concierge Support

- AWS Concierge Support provides guidance and consultancy services on technological issues and special projects outside of AWS. This is particularly valuable for maximizing technology investments and adopting best practices for non-AWS technologies.
- Technology Consultancy
- Personalized Support
- Integration Help
- Strategic planning
- Project Management


## To help secure your AWS resources, follow the best practices in using your AWS Identity and Access Management (IAM) service

- Lock Away Your AWS Account Root User Access Keys
- Create Individual IAM Users
- Use Groups to Assign Permissions to IAM Users
- Grant Least Privilege
- Get Started Using Permissions with AWS Managed Policies
- Use Customer Managed Policies Instead of Inline Policies
- Use Access Levels to Review IAM Permissions
- Configure a Strong Password Policy for Your Users
- Enable MFA
- Use Roles for Applications That Run on Amazon EC2 Instances
- Use Roles to Delegate Permissions
- Do Not Share Access Keys
- Rotate Credentials Regularly
- Remove Unnecessary Credentials
- Use Policy Conditions for Extra Security
- Monitor Activity in Your AWS Account

## Security in the cloud

1- **Implement a strong identity foundation**
2- **Enable traceability**
3- **Apply security at all layers**
4- **Automate security best practices**
5- **Protect data in transit and at rest**
6- **Keep people away from data**
7- **Prepare for security events**

## When you want to reduce the costs of Amazon EBS consider the following

- Delete Unattached Amazon EBS Volumes
- Resize or Change the EBS Volume Type
- Delete Stale Amazon EBS Snapshots

## Three options to control access to an Amazon S3 Bucket

- IAM Policies
- Bucket Policies
- Bucket ACLs

## The AWS Marketplace provides value to buyers in several ways

- It simplifies software licensing and procurement with flexible pricing options and multiple deployment methods. Flexible pricing options include free trial, hourly, monthly, annual, multi-year, and BYOL.
- Customers can quickly launch pre-configured software with just a few clicks, and choose software solutions in AMI and SaaS formats, as well as other formats.
- It ensures that products are scanned periodically for known vulnerabilities, malware, default passwords, and other security-related concerns.

## Amazon Elastic Transcoder

- Amazon Elastic Transcoder is a media transcoding service. It is designed to be a highly scalable, easy-to-use, and cost-effective way to convert (or transcode) media files from their source format into versions that will play back on devices like smartphones, tablets, and PCs.

## AWS Acceptable Use Policy (AUP)

- The AWS Acceptable Use Policy describes prohibited uses of the web services offered by AWS. For example, any activities that are illegal, that violate the rights of others, or that may be harmful to others are prohibited. If a customer violates the policy or authorizes or helps others to do so, AWS may suspend or terminate their use of the services.

## AWS Free Security Resources

- AWS Security Blog
- Whitepapers
- AWS Developer Forums
- Articles and Tutorials
- Security Bulletins
- Compliance Resources and Testimonials.

## AWS Federation

With Federation, you can use single sign-on (SSO) to access your AWS accounts using credentials from your corporate directory. Federation uses open standards, such as Security Assertion Markup Language 2.0 (SAML), to exchange identity and security information between an identity provider (IdP) and an application.

AWS offers multiple options for federating your identities in AWS:

- AWS Identity and Access Management (IAM)
- AWS IAM Identity Center (Successor to AWS Single Sign-On)
- AWS Directory Service

## AWS Compute Optimizer

AWS Compute Optimizer recommends optimal AWS resources for your workloads to reduce costs and improve performance by using machine learning to analyze historical utilization metrics. Over-provisioning resources can lead to unnecessary infrastructure costs, and under-provisioning resources can lead to poor application performance. Compute Optimizer helps you choose optimal configurations for three types of AWS resources: Amazon EC2 instances, Amazon EBS volumes, and AWS Lambda functions, based on your utilization data.

## Customer Managed Key (CMK)

The KMS keys that you create are customer managed keys. Customer managed keys are KMS keys in your AWS account that you create, own, and manage. You have full control over these KMS keys, including establishing and maintaining their key policies, IAM policies, and grants, enabling and disabling them, rotating their cryptographic material, adding tags, creating aliases that refer to the KMS keys, and scheduling the KMS keys for deletion.

## Amazon Eventbridge

Amazon EventBridge is a service that provides real-time access to changes in data in AWS services, your own applications, and software as a service (SaaS) applications without writing code. Amazon EventBridge Scheduler is a serverless task scheduler that simplifies creating, executing, and managing millions of schedules across AWS services without provisioning or managing underlying infrastructure.

## AWS Local Zones

AWS Local Zones enable AWS to position its services close to users outside of large geographic regions (Regions), enabling users to deliver their applications to end users with low latency. Local Zones are connected to an AWS region (Region), but are close to the user's geographic location.

## AWS **Service Health Dashboard**

Service Health Dashboard is the single place to learn about the availability and operations of AWS services. You can view the overall status of AWS services, and you can sign in to view personalized communications about your particular AWS account or organization.

## AWS **Account Health Dashboard**

Account Health Dashboard, alerts are triggered by changes in the health of your AWS resources, giving you event visibility, and guidance to help quickly diagnose and resolve issues.

## Route 53 - **Choosing a routing policy**

- **Simple routing policy** – Use for a single resource that performs a given function for your domain, for example, a web server that serves content for the example.com website. You can use simple routing to create records in a private hosted zone.
- **Failover routing policy** – Use when you want to configure active-passive failover. You can use failover routing to create records in a private hosted zone.
- **Geolocation routing policy** – Use when you want to route traffic based on the location of your users. You can use geolocation routing to create records in a private hosted zone.
- **Geoproximity routing policy** – Use when you want to route traffic based on the location of your resources and, optionally, shift traffic from resources in one location to resources in another location.
- **Latency routing policy** – Use when you have resources in multiple AWS Regions and you want to route traffic to the Region that provides the best latency. You can use latency routing to create records in a private hosted zone.
- **IP-based routing policy** – Use when you want to route traffic based on the location of your users, and have the IP addresses that the traffic originates from.
- **Multivalue answer routing policy** – Use when you want Route 53 to respond to DNS queries with up to eight healthy records selected at random. You can use multivalue answer routing to create records in a private hosted zone.
- **Weighted routing policy** – Use to route traffic to multiple resources in proportions that you specify. You can use weighted routing to create records in a private hosted zone.

## AWS Market Advantages

- Speed
- Agility
- Flexible pricing
- Control and governance

## AWS Cloud Foundations

Cloud Foundations provides a guided path to help customers deploy, configure, and secure their new workloads while ensuring they are ready for on-going operations in the cloud. Cloud Foundations helps customers navigate through the decisions they need to make through curated AWS Services, AWS Solutions, Partner Solutions, and Guidance.

## AWS Security Token Service (AWS STS)

AWS Security Token Service (STS) is a web service offered by AWS for authentication and authorization. AWS STS provides short-term credentials to users or systems. This service is largely used for the need to provide temporary access to AWS resources.

## TCO Calculator

TCO Calculator is a tool that helps businesses better understand the potential cost savings of migrating to the cloud and compare current infrastructure costs to AWS cloud costs.

## AWS CodeArtifact

AWS CodeArtifact is a fully managed dependency management service provided by Amazon Web Services (AWS). This service makes it easy to store, share and distribute your code dependencies, packages and container images in a central location.

## Amazon Kinesis Data Streams

Amazon Kinesis Data Streams (KDS) is a service from Amazon Web Services (AWS) to easily collect, process, and analyze real-time big data streams.

## AWS IoT Core

AWS IoT Core is a management service from Amazon Web Services (AWS) for Internet of Things (IoT) applications. It securely collects, processes and routes data from IoT devices.

## AWS OpsHub

AWS OpsHub is a service that provides a user-friendly graphical user interface (GUI) to manage AWS Snowball devices. It allows you to create and manage Snowball jobs, track the status of your jobs, and download and upload data to and from Snowball devices.

## QuickSight Q

Amazon QuickSight Q is a query service that is a component of Amazon QuickSight. QuickSight Q is a tool you can use to explore, analyze and query your data. This service has a user-friendly interface to help you better understand your data.

## AWS Well-Architected Tool

It helps customers evaluate compliance with best practices when designing, building, and operating their AWS infrastructure. This tool is designed based on the AWS Well-Architected framework.

## Amazon Quantum Ledger Database (Amazon QLDB)

Amazon Quantum Ledger Database (Amazon QLDB) is a fully managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log owned by a central trusted authority. Amazon QLDB can be used to track each and every application data change and maintains a complete and verifiable history of changes over time.

## Amazon Timestream

Amazon Timestream is a fast, scalable, and serverless time series database service for IoT and operational applications that makes it easy to store and analyze trillions of events per day up to 1,000 times faster and at as little as 1/10th the cost of relational databases. Amazon Timestream saves you time and costs in managing the lifecycle of time series data by keeping recent data in memory and moving historical data to a cost-optimized storage tier based upon user-defined policies.


## Extra Notes

-When a service is said to be fully managed it means that it handles routine administrative tasks such as setup, configuration, patching, and backups.

-AWS provides several services that allow you to extend your on-premises architecture to the AWS Cloud. These services help integrate on-premises resources with AWS, enabling hybrid cloud architectures. Key services include:

    AWS Direct Connect:
   - **Description**: AWS Direct Connect provides a dedicated network connection from your premises to AWS. It helps establish a private, low-latency connection between your data centers and AWS, which can reduce network costs and increase bandwidth throughput.
   - **Use Case**: Suitable for enterprises that need consistent, high-speed, and secure connectivity to AWS.

    AWS VPN:
   - **Description**: AWS VPN enables you to establish a secure and encrypted connection between your on-premises network or a user's device and the AWS cloud. It consists of two services: AWS Site-to-Site VPN and AWS Client VPN.
   - **Use Case**: Ideal for extending your on-premises network to AWS securely and cost-effectively, or providing remote access to your AWS resources.

    AWS Storage Gateway:
   - **Description**: AWS Storage Gateway is a hybrid cloud storage service that enables your on-premises applications to seamlessly use AWS cloud storage. It supports three types of gateways: File Gateway, Tape Gateway, and Volume Gateway.
   - **Use Case**: Useful for extending on-premises storage to the cloud, archiving data, and providing scalable storage solutions.

    AWS Outposts:
   - **Description**: AWS Outposts delivers fully managed and configurable compute and storage racks built with AWS-designed hardware to bring AWS services, infrastructure, and operating models to virtually any data center, co-location space, or on-premises facility.
   - **Use Case**: Perfect for workloads that require low latency access to on-premises systems, local data processing, or data residency requirements.

    AWS Snow Family (Snowball, Snowcone, Snowmobile):
   - **Description**: The AWS Snow Family helps physically transfer large amounts of data between your on-premises data centers and AWS. The devices are rugged and secure, designed to withstand transport.
   - **Use Case**: Best for data migration projects, disaster recovery, and edge computing needs when transferring large datasets or when internet transfer is not feasible.

    Amazon RDS on VMware:
   - **Description**: Amazon RDS on VMware allows you to run managed databases in on-premises VMware environments using the Amazon RDS technology. It automates database administration tasks like backups, patching, monitoring, and scaling.
   - **Use Case**: Suitable for extending managed database capabilities to your on-premises VMware environments.


- AWS data services 
-They cater to various needs, including data storage, databases, analytics, migration, and machine learning. Here’s an overview of some key AWS data services:

            Databases
   - **Amazon RDS (Relational Database Service)**: A managed relational database service that supports various database engines like MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora.
   - **Amazon Aurora**: A MySQL and PostgreSQL-compatible relational database designed for performance and availability.
   - **Amazon DynamoDB**: A fully managed NoSQL database service that provides fast and predictable performance with seamless scalability.
   - **Amazon Redshift**: A fully managed data warehouse service that allows you to run complex SQL queries on petabytes of structured and semi-structured data.
   - **Amazon DocumentDB**: A fully managed document database service that is compatible with MongoDB.
   - **Amazon Neptune**: A fully managed graph database service that supports highly connected datasets like social networks or recommendation engines.
   - **Amazon Timestream**: A time series database service designed for IoT and operational applications that need to collect, store, and analyze large amounts of time series data.
   - **Amazon QLDB (Quantum Ledger Database)**: A fully managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log.
   - **Amazon ElastiCache**: A fully managed in-memory data store and cache service, supporting Redis and Memcached.

            Data Storage
   - **Amazon S3 (Simple Storage Service)**: Object storage service that offers industry-leading scalability, data availability, security, and performance.
   - **Amazon EFS (Elastic File System)**: A scalable and fully managed file storage service that is elastic, so it can grow and shrink automatically as you add and remove files.
   - **Amazon FSx**: Managed file systems built on popular file systems like Windows File Server (FSx for Windows) and Lustre (FSx for Lustre).
   - **Amazon Glacier**: A secure, durable, and extremely low-cost cloud storage service for data archiving and long-term backup.
   - **AWS Backup**: A centralized backup service to automate and manage backups across AWS services.

            Data Analytics
   - **Amazon EMR (Elastic MapReduce)**: A cloud big data platform for running large-scale data processing frameworks such as Apache Hadoop, Spark, HBase, and Presto.
   - **Amazon Kinesis**: A platform for real-time data streaming and analytics, enabling you to collect, process, and analyze streaming data.
   - **AWS Glue**: A fully managed ETL (extract, transform, load) service that makes it easy to prepare and load data for analytics.
   - **Amazon Athena**: An interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL.
   - **Amazon QuickSight**: A fast, cloud-powered business intelligence service that allows you to create visualizations and perform ad-hoc analysis of data.
   - **AWS Lake Formation**: A service to set up a secure data lake in days, allowing you to store, catalog, and analyze all your data in one central location.
   - **Amazon OpenSearch Service**: A managed service that makes it easy to deploy, operate, and scale OpenSearch (formerly Elasticsearch) clusters for log analytics, full-text search, application monitoring, and more.

            Data Migration
   - **AWS Database Migration Service (DMS)**: Helps you migrate databases to AWS quickly and securely. The source database remains operational during the migration.
   - **AWS Snow Family**: A collection of physical devices used to move large amounts of data to and from AWS, including Snowcone, Snowball, and Snowmobile.
   - **AWS DataSync**: An online data transfer service that automates moving data between on-premises storage and AWS storage services.

            Machine Learning and AI Data Services
   - **Amazon SageMaker**: A fully managed service that provides every developer and data scientist with the ability to build, train, and deploy machine learning models quickly.
   - **Amazon Comprehend**: A natural language processing (NLP) service that uses machine learning to find insights and relationships in text.
   - **Amazon Rekognition**: A service that makes it easy to add image and video analysis to your applications.
   - **Amazon Polly**: A service that turns text into lifelike speech.
   - **Amazon Textract**: A service that automatically extracts text, handwriting, and data from scanned documents.

            Data Security and Governance
   - **AWS KMS (Key Management Service)**: A managed service that makes it easy to create and control the encryption keys used to encrypt your data.
   - **AWS CloudHSM**: A cloud-based hardware security module (HSM) that enables you to generate and use your own encryption keys.
   - **AWS Identity and Access Management (IAM)**: A service that helps you securely control access to AWS services and resources.


- AWS provides several support plans tailored to different levels of service needs, each offering varying degrees of access to AWS support teams. Below are the main AWS support plans and the types of teams that support them:
    1. Basic Support Plan
Teams Supported:

AWS Community Support: Access to a vast network of AWS customers and partners who share tips and best practices via forums and other online communities.
AWS Trusted Advisor: Basic checks are available to all customers, but the level of support is minimal.
AWS Personal Health Dashboard: Provides alerts and guidance for events that may impact your infrastructure.
Features:

24/7 access to customer service, documentation, whitepapers, and AWS Trusted Advisor's core checks.
Support through the AWS Knowledge Center.
No technical support from AWS Support Engineers.
Best For: Individual developers or businesses getting started with AWS.

2. Developer Support Plan
Teams Supported:

AWS Support Engineers: Limited access to cloud support associates via email during business hours with response times of 12 hours or less for general guidance and 24 hours for system impairment.
AWS Trusted Advisor: Full access to AWS Trusted Advisor's best practice checks and recommendations.
AWS Personal Health Dashboard: Provides real-time alerts and support for events that impact your infrastructure.
Features:

Technical support from AWS Cloud Support Associates during business hours.
General architectural guidance and best practices.
Access to AWS Support API for automated support case management.
Best For: Developers experimenting with or testing AWS services in non-production environments.

3. Business Support Plan
Teams Supported:

AWS Support Engineers: 24/7 access to AWS Support Engineers via phone, chat, and email for fast response times (less than 1 hour for production system issues).
AWS Solutions Architects: Provides guidance on how to use AWS products and features to meet your specific needs.
AWS Trusted Advisor: Full access to Trusted Advisor checks, including cost optimization, security, fault tolerance, and performance.
AWS Personal Health Dashboard: Real-time proactive guidance and notifications.
Features:

24/7 technical support for all issues.
Contextual guidance from AWS Solutions Architects.
Support for third-party software integration.
Best practice recommendations and architectural guidance.
Best For: Businesses with production workloads on AWS requiring technical support and architectural guidance.

4. Enterprise Support Plan
Teams Supported:

AWS Support Engineers: 24/7 access to AWS Support Engineers with the fastest response times (less than 15 minutes for critical business system issues).
AWS Technical Account Manager (TAM): A dedicated Technical Account Manager who provides proactive guidance and expertise, including regular reviews and reports.
AWS Solutions Architects: In-depth architectural guidance and best practice recommendations tailored to your business.
AWS Infrastructure Event Management: Support for launching new applications or migrating workloads to AWS, with focused guidance from AWS experts.
AWS Concierge Support: Assistance with account and billing questions.
AWS Trusted Advisor: Full access to Trusted Advisor checks and recommendations.
Features:

24/7 access to technical support with the fastest response times.
Dedicated TAM who acts as your primary point of contact with AWS.
Strategic business reviews and event management.
Hands-on architectural and operational guidance.
Best For: Large enterprises and organizations with mission-critical workloads that require comprehensive support and dedicated resources.

![image](https://github.com/user-attachments/assets/ef735622-012b-4b34-b89b-9751ad58f1a2)


- Reports generated by the different AWS services

![image](https://github.com/user-attachments/assets/e5b6b931-c297-4b68-9e81-13324aadb9c9)

![image](https://github.com/user-attachments/assets/299b7412-adbc-4208-9fda-7d3e36803b59)

![image](https://github.com/user-attachments/assets/c0aba701-e362-4ddb-903e-701b27f0eddd)


- Route 53 can perform global load balancing
- AWS Snowball can secure transfer of large amounts of data into and out of the AWS. Its 2 way not only into AWS
