+++
title = "Configure API Gateway"
date = 2024
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

### Overview API Gateway

An **API Gateway** service provided by AWS. It provides a simple way to build, manage, and secure **RESTful APIs** or **WebSockets**. AWS API Gateway is an important service in the AWS-based microservices architecture and is often used in conjunction with other AWS services such as **_AWS Lambda, EC2, S3, Amazon DynamoDB_**.

#### What features does AWS API Gateway provide?

- Allows designing and developing RESTful or WebSocket APIs through a web GUI.
- Coordinates API requests to different systems or services.
- Authen/Author requests to APIs.
- Manage and monitor API requests, such as number of requests, response time...• AWS API Gateway also provides security features, including authentication and authorization of API requests and encrypted secure communication between different systems.

#### Features of API Gateway

- Is a fully managed service of AWS.
- Unlimited scalability and High Availablity.
- Zero idle cost
- Easy to setup
- Easy to combine with other services such as CloudWatch, WAF for monitoring & security purposes.

#### When to use API Gateway?

- API Gateway is suitable for the following problems
  - Micro-service architecture using lambda as backend
  - Backend API for most use cases (web API, IoT)
  - Gateway receives data directly from the client and then stores it in DynamoDB (DB First)
  - Web Socket for realtime communication systems.

#### Cost of API Gateway ?

API Gateway PricingAPI Gateway is a service with idle cost = 0. Users only pay for the actual running cost,

- **With REST API**
  - Number of requests (eg Singapore region: $ 4.25/1M requests)
  - Data transfer out ($/GB)
  - Caching size in GB/hour
- **With Web socket**
  - Message number (for Web socket). Eg $1.15/1M message with 32KB block.
  - Connection minutes: $0.288/1M connection minutes

#### Authentication for API Gateway ?

API Gateway provides 2 commonly used direct authentication methods (authorizers):

- **Cognito Authorizer**
  Directly linked to a Cognito User Pool used as an authorizer. When accessing the API, the client passes the token obtained directly through login with Cognito, API Gateway will check the token and allow access if the token is valid.

- **Lambda Authorizer** (custom authorizer)
  When using this type of authorizer, you will implement the authen logic yourself on Lambda. There are 2 forms: authen based on TOKEN (JWT) or request parameter based (eg username/password).

- **Model using Lambda as authorizer**
  ![Lambda làm authorizer](/images/4/4_1/000.png?width=90pc)

### Content

1. [Create REST API](1-create-rest-api)
2. [Check API with Postman](2-check-api-with-postman)
