+++
title = "Create Role for Lambda"
date = 2024
weight = 3
chapter = false
pre = "<b>2.3 </b>"
+++

### Create Role for Lambda

- In the Console interface:
  - Search for keyword: **IAM**

![IAM](/images/2/2_3/1.png?width=90pc)

- Select Create Role

![IAM](/images/2/2_3/2.png?width=90pc)

Fill in information:

- Select usage type: **AWS service**
- Service: **Lambda**
- Select **Next**

![IAM](/images/2/2_3/3.png?width=90pc)

- Search for the corresponding keyword and select the following permissions:
- Select `AmazonRDSFullAccess`
- Select `AmazonEC2FullAccess`
- Select `AWSLambdaVPCAccessExecutionRole`
- Select `AmazonVPCFullAccess`

![IAM](/images/2/2_3/4.png?width=90pc)

- Enter the role name: `RoleLambdatochangedataRDS`

![IAM](/images/2/2_3/5.png?width=90pc)

- Double check and select **Create role**

![IAM](/images/2/2_3/6.png?width=90pc)
