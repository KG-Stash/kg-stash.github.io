+++
title = "VPC Configuration"
date = 2024
weight = 1
chapter = false
pre = "<b>2.1 </b>"
+++

### VPC Configuration

1. In the AWS console interface, perform
   - Search and select **VPC**

![VPC Search](/images/2/2_1/1.png?width=90pc)

2. In the VPC management interface
   - Select **Your VPC**
   - Select **Create VPC**

![VPC Search](/images/2/2_1/2.png?width=90pc)

3. The configuration table for VPC appears
   - Select **VPC and more**
   - Name `FCJ-Lab`

![VPC Search](/images/2/2_1/3.png?width=90pc)

- Select **Availability Zones (AZs)**: **2**
- Select **public subnets**: **2**
- Select **private subnets**: **2**

- In the **VPC endpoint** section
  - Select **None**
  - Select **Create VPC**

![VPC Search](/images/2/2_1/4.png?width=90pc)

4. After creating the VPC, we proceed to check the information of the newly created VPC.
   - Select **FCJ-Lab-vpc** just created to see the overview

![VPC Search](/images/2/2_1/5.png?width=90pc)

5. Configure Public Subnet
   In the VPC management interface, in the left selection, scroll down
   - Select **Subnets**
   - Search for **_FCJ-Lab_**

![VPC Search](/images/2/2_1/6.png?width=90pc)

We will see that there are **2 public subnets**: **FCJ-Lab-subnet-public1-ap-southeast-1a, FCJ-Lab-subnet-public2-ap-southeast-1b**

- First we will set up **FCJ-Lab-subnet-public1-ap-southeast-1b**
  - Select **FCJ-Lab-subnet-public1-ap-southeast-1a**
  - Select Action
  - Select Edit subnet settings

![VPC Search](/images/2/2_1/7.png?width=90pc)

- The configuration table for the public subnet appears
  - Click to select **Enable auto-assign public IPv4 address**
  - Select **Save**

![VPC Search](/images/2/2_1/8.png?width=90pc)

Similarly, we will set for **FCJ-Lab-subnet-public2-ap-southeast-1b**
![VPC Search](/images/2/2_1/9.png?width=90pc)

Thus, we have just configured VPC and enabled public IPv4 for the public subnet.
