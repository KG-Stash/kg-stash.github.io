+++
title = "Create Security Group"
date = 2024
weight = 2
chapter = false
pre = "<b>2.2 </b>"
+++

### Configure Security Group

**Configure Security Group for EC2 instance**

1. In the VPC management interface, select the left option.
   - Select **Security Groups**
   - Select **Create security group**

![Security Group](/images/2/2_2/1.png?width=90pc)

- Configuration for Security Group
- In the **Basic details** section
  - Name the security group: `FCJ-Lab-sg-public`
  - Description: `Security group for FCJ Lab`
  - VPC: **FCJ-Lab-vpc**

![Basic details](/images/2/2_2/2.png?width=90pc)

2. In the Inbound rules section
   We will add the following rules:
   - Type **SSH** source **Anywhere-IPv4**
   - Type **HTTP** source **Anywhere-IPv4**
   - Type **HTTPS** source **Anywhere-IPv4**
   - Type **Custom TC**P, port range **3000**, source **Anywhere-IPv4**

![Inbound rules](/images/2/2_2/3.png?width=90pc)

- In the Outbound section, we will leave it as default
- Click **Create security group**

**Configure Security Group for database instance**

3. Similar to the step of creating a security group above. Configure Security Group DB
   - In the Basic details section
     - Security group name `FCJ-Lab-sg-db`
     - Description **Security group for RDS database instance**
     - VPC **FCJ-Lab-vpc**
   - In the Inbound section
     - Select Type **MYSQL/Aurora**
     - Source select **FCJ-Lab-sg**
     - In the **Outbound** section. We leave it as default

![Inbound rules](/images/2/2_2/4.png?width=90pc)

- Select **Create security group**

![Inbound rules](/images/2/2_2/5.png?width=90pc)
