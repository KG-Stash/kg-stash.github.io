+++
title = "Create lambda function"
date = 2024
weight = 4
chapter = false
pre = "<b>3.4 </b>"
+++

#### Create lambda function

1. In AWS Console interface.

- Search and select Lambda
  ![Lambda](/images/3/3_4/1.png?width=90pc)
- Create lambda function
  ![Create lambd](/images/3/3_4/2.png?width=90pc)

2. In the Create function section

- Select **Author from scratch**
- In the Basic information section - Function name: `ChangeDataRDS` - Runtime: **Node.js 20.x**
  ![Basic information](/images/3/3_4/3.png?width=90pc)

- Select Role: **RoleLambdatochangedataRDS**
  ![Choose Role](/images/3/3_4/4.png?width=90pc)

3. Check **Enble VPC**

   - Select the information that has been initialized before:
     - VPC **FCJ-Lab-vpc**
     - Select public subnet: **FCJ-Lab-subnet-private2-ap-southeast-1b** & **FCJ-Lab-subnet-private1-ap-southeast-1a**
   - Select **Select existing security group**
   - Select **FCJ-Lab-sg-public** & **FCJ-Lab-sg-db**
     ![Enble VPC](/images/3/3_4/5.png?width=90pc)

- After setting up, finally select **Create**
  ![Create](/images/3/3_4/6.png?width=90pc)

4. Download the Lambda function file with the following functions:
   - Add new user & Delete user in the database.

- Download the .zip file containing the lambda function.

{{%attachments style="orange" title="Lambda Function" pattern=".*(zip)"/%}}

5. Select **Upload form**
   ![Upload Zip](/images/3/3_4/7.png?width=90pc)

- Select **Upload**
- Select Zip file here
  ![Choose Zip](/images/3/3_4/8.png?width=90pc)

Uploaded .zip file successfully
![Upload Zip success](/images/3/3_4/9.png?width=90pc)

6. At the **Configuration** tab in the lambda

- Select **Environment variables**
- Click **Edit**
  ![Edit Environment variables](/images/3/3_4/10.png?width=90pc)

- Select **Add environment variable**:

```
RDS_LAMBDA_HOSTNAME: endpoint_your_rds_instance
RDS_LAMBDA_USERNAME: admin
RDS_LAMBDA_PASSWORD: admin2024
RDS_LAMBDA_PORT: 3306
JWT_SECRET: 0bac010eca699c25c8f62ba86e319c2305beb94641b859c32518cb854addb5f4
```

- Select **Save** to save the environment.
  ![Edit Environment variables](/images/3/3_4/11.png?width=90pc)
  ![Edit Environment variables](/images/3/3_4/12.png?width=90pc)
