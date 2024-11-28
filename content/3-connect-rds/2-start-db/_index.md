+++
title = "Create RDS Instance"
date = 2024
weight = 2
chapter = false
pre = "<b>3.2 </b>"
+++

#### Launch RDS Instance

Create RDS Instance

- Select section: **Databases**
- Select: **Create Database**
  ![Choose DB](/images/3/3_2/1.png?width=90pc)

- Select method: **Standard create**
- Select storage type: **MySQL**
  ![Template](/images/3/3_2/2.png?width=90pc)

- Select template: **Dev/Test**
- Select **Multi-AZ DB instance**
  We can adjust this part to suit your requirements to optimize your costs, but there will also be some limitations so you need to study carefully.
  ![Subnet DB](/images/3/3_2/3.png?width=90pc)

- Enter DB instance name: `fcj-database-instance`
- Enter username: `admin`
- Enter password: `admin2024`
  ![Info DB](/images/3/3_2/4.png?width=90pc)

In the settings section:
![Class & Storage](/images/3/3_2/5.png?width=90pc)

- Connect to the created VPC: **FCJ-Lab-vpc**
- Select the Subnet created from the previous section: **fcj-lab-subnet-group-db**
- Public access: **Yes**
  ![Resource](/images/3/3_2/6.png?width=90pc)

- Select the Security group created for the DB: **FCJ-Lab-sg-db**
- The following part can be left as default or configured as desired
  ![Resource](/images/3/3_2/7.png?width=90pc)

- Check the configurations carefully to avoid confusion affecting the implementation cost
- Select **Create**
  ![Resource](/images/3/3_2/8.png?width=90pc)

- Complete creating DB instance and this process must wait about 15 minutes to show Available
  ![Resource](/images/3/3_2/9.png?width=90pc)
