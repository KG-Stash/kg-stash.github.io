+++
title = "Create DB Subnet Group"
date = 2020
weight = 1
chapter = false
pre = "<b>3.1 </b>"
+++

#### Create DB Subnet Group

In the AWS console interface, type:

1. Search for the keyword: **RDS**

- Select the section: **Subnet groups**
- Select: **Create DB subnet group**
  ![Subnet DB](/images/3/3_1/1.png?width=90pc)

- Enter the name: `fcj-lab-subnet-group-db`
- Enter the description: `Subnet Group for FCJ Management`
- Select the previously created VPC as **FCJ-Lab-vpc**
  ![Info Subnet DB](/images/3/3_1/2.png?width=90pc)

2. Select Availability Zones that were created with the previously created VPC

- Select **2 Subnet private**
- Check again and select **Create**
  ![Create Subnet DB](/images/3/3_1/3.png?width=90pc)
- Completed creating a Subnet groups
  ![Create Success](/images/3/3_1/4.png?width=90pc)
