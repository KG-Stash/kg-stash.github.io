+++
title = "Launch RDS Instance"
date = 2024
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

### Overview Amazon RDS

**Amazon RDS** is a managed database on AWS, we can only access and manage at the RDBMS level, cannot access and manage at the operating system level. Including Aurora, MySQL, PostgreSQL, MSSQL, Oracle, and MariaDB. Amazon RDS provides the following features:

- Automatic backup (both log and database - up to 35 days).
- Create a read-only replica (Read Replica) to serve reading workloads (reporting).
- Read Replica can be separated and converted into a Primary node.
- Run with automatic failover mechanism, Primary/Standby, also known as Multi-AZ mechanism.
- RDS is often used for OLTP applications.
- RDS provides data encryption at rest and in transit.
- RDS is also protected by firewall features like EC2 (Security Group and NACL).
- Scaling (changing instance size).
- Automatically increase storage capacity (Storage Auto Scale).

### Pricing

- Basically RDS charges based on parameters:
  - Instance size. The larger the instance size, the higher the cost. Supports reserve instances similar to EC2.
  - Amount of data stored (GB/month)
  - Size of snapshots created.
  - Other features such as Backtracking for Aurora.

### RDS Deployment Model

- RDS can be deployed in the following models:

  - **Single Instance**
  - **Single Instance with Multi-AZ option = yes**
  - **Master – Read Only cluster**
  - **Master – Read Only cluster with Multi-AZ option = yes**
  - **Master – Multi Read cluster**

- **Single Instance** Only 1 database instance is created in 1 Availability Zone (AZ). If an incident occurs at the AZ level, the database cannot be accessed. Suitable for Dev-Test environments to save costs

- **Single Instance with Multi-AZ option enabled**

  - A copy of the instance will be created in another AZ and operate in standby mode. The task of this standby instance is to sync data from the master, this instance cannot be accessed.
  - When there is an incident, the standby instance will be promoted to the master (this is done automatically by AWS, the endpoint url is kept the same).
  - If you enable multi AZ, the cost will be x2.
  - Suitable for Database Production.

- **Master – Read Only cluster**

  - An instance with ReadOnly mode will be created and continuously replicate data from the master instance. This instance can only read data.
  - Suitable for systems with read > write workloads, wanting to optimize the performance of the Database. After establishing the relationship, the created instance will be combined into 1 cluster.
  - In the state where 2 instances have formed a cluster, if the Master instance has a problem, failover will be automatically performed, _ReadOnly instance is promoted to Master_.
  - You should create a cluster and then add a read node to manage the connection at the cluster level (the number of read nodes can be optional)

{{% notice note %}}
Note: If 2 instances are created separately and then the read-replica relationship is established, the endpoints of the 2 instances will be separate, so after failover, the connection from the App needs to be adjusted.
{{% /notice %}}

- **Master – Read Only cluster with Multi-AZ option = yes**
  - Similar to the **Master – Read Only** model, but all nodes are multi-AZ enabled. The cost will be 4 times that of the Single Instance model.

#### Should I create an RDS Cluster or an RDS Instance?

AWS provides a mechanism to create an RDS cluster to make node management and failover easier.

Advantages compared to creating a normal RDS instance:

- Endpoint management at the cluster level, not changed when an instance in the cluster has a problem.
- Automatic failover.
- Easy to scale read instances.

### Contents

1. [Create DB Subnet Group](1-db-subnet-group)
2. [Create RDS Instance](2-start-db)
3. [Launch EC2 Instance](3-launch-ec2)
4. [Create lambda function](4-create-lambda-function)
5. [Connect RDS with lambda](5-connect-lambda-rds)
