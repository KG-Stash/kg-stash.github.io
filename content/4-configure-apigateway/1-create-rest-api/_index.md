+++
title = "Create REST API"
date = 2024
weight = 1
chapter = false
pre = "<b>4.1 </b>"
+++

Next, we will set up API Gateway to interact with the Lambda functions created in the previous section:

#### Create REST API

1. In the Console interface:

- Search for keyword: **API Gateway**
  ![API Gateway](/images/4/4_1/1.png?width=90pc)

2. Select **REST API**
   ![Choose Rest API](/images/4/4_1/2.png?width=90pc)

- Select **New API**
- API name: `api-dcj-rds`
- Description – optional: **test**
- API endpoint type: **Regional**
- Select **Create API**
  ![Info Create API](/images/4/4_1/3.png?width=90pc)

- REST API successfully created
- Next select **Create resource**
  ![Create API success](/images/4/4_1/4.png?width=90pc)

So we have created a new REST API and resources for it. Next, we will create methods that interact with the Lambda function and implement them.

3. Create Method API

- Select **Create Method**
  ![Create Method](/images/4/4_1/5.png?width=90pc)

- Method type: **POST**
- Integration type: **Lambda function**
- Lambda function: **ChangeDataRDS**
- Select **Create Method**
  ![Info Method](/images/4/4_1/6.png?width=90pc)

4. After successfully creating the POST method, next select **Deploy API**
   ![Create Deploy](/images/4/4_1/7.png?width=90pc)

- Select Stage: **New stage**
- Stage name: `changdata`
- Select **Deploy**
  ![Deploy API](/images/4/4_1/8.png?width=90pc)

5. Copy the **Invoke URL** of the created **POST** method
   ![Copy Invoke URL](/images/4/4_1/9.png?width=90pc)
