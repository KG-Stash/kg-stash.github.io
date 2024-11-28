+++
title = "Clean up resource"
date = 2021-06-08T18:57:03+07:00
weight = 7
chapter = false
pre = "<b>7. </b>"
+++

We will clean up resources in the following order:

1. Go to **API Gateway** to delete the created resource

2. Go to **Cognito** to delete the created resource

   - Select Delete Cognito domain
   - Select Deactivate deletion protection

3. Go to **Lambda** to delete the created function.

   - Automatically delete the generated **Network interfaces**. Check again, if it is still related to the resource, delete it to avoid incurring costs.

4. Go to **Amazon RDS** service

   - Open the Amazon RDS console.
   - In the navigation pane, select Subnet groups.
   - Select the DB subnet group related to the lab.
   - Select Delete, then select Delete in the confirmation window.

   - Select the RDS instance that was created
   - Go to Modify. Scroll down and uncheck Enable deletion protection
   - Select Action and select delete
   - Uncheck Create final snapshot
   - Uncheck Retain automated backups
   - Wait a few minutes to delete
   - After deleting the db instance, check the **Snapshot**, **Automated Backup** versions (if any, delete if not necessary to avoid incurring costs)
   - In the subnet group section. Delete the subnet group related to the created VPC.

5. Terminate **EC2 instance**

   - Access EC2 Management Console.
   - On the left navigation bar, select Instances.
   - Select all EC2 Instances related to the lab.
   - Click Actions.
   - Click Manage Instance State.
   - Select Terminate.

   - Open the Amazon EC2 console.
   - Select Amazon EC2 Dashboard, then select Elastic IPs.
   - Select Elastic IP address related to the lab.
   - From Actions, select Release Elastic IP addresses.
   - On the confirmation page, select Release.

   - Go to Network interfaces
   - Check for missing Network interfaces related to the lesson

6. To delete **VPC** and related resources:

   - Access the endpoint, delete the resource that was created during the practice, the endpoint containing the created VPC.

   - Open the Amazon VPC dashboard.
   - Delete the VPC.
   - Select VPC Dashboard, then select VPC.
   - Select the VPC you want to delete.
   - From Actions, select Delete VPC.
   - On the confirmation page, type delete, then select Delete.

   - Open the Amazon VPC dashboard.
   - Select VPC Dashboard, then select Security Groups.
   - Check for missing security groups after deleting the VPC
   - Select the security group related to the lab.
   - Select Actions, select Delete security groups, and then select Delete to confirm.
