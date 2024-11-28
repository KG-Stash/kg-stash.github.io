+++
title = "Introduction"
date = 2024
weight = 1
chapter = false
pre = "1. "
+++

#### Introduction

You will learn how to integrate services such as **Amazon RDS**, **AWS Lambda**, **Amazon Cognito**, **Amazon API Gateway** to build a web system or serverless application (no need to manage servers).

- **Amazon RDS**: You will understand how to create and manage relational databases (MySQL, PostgreSQL, etc.) on AWS to store data.

- **AWS Lambda**: You will learn how to create Lambda functions to handle application logic without having to manage servers. Lambda can connect to RDS and S3 to manipulate data.
- **Amazon Cognito**: You will learn how to use Amazon Cognito to authenticate and manage users, secure your APIs, and authenticate requests from users.

- **API Gateway**: You will learn how to configure an **API Gateway** to provide HTTP endpoints that allow users or applications to communicate with Lambda, and secure the API using Cognito for authentication.

#### Services covered in the workshop include:

- **Amazon Relational Database Service (Amazon RDS)**

  - Amazon Relational Database Service is a managed service that allows you to deploy and manage relational databases on AWS.
  - Amazon RDS is an online transaction processing (OLTP) database.
  - The primary use case is transactional databases (rather than analytical databases).
  - It is best suited for structured and relational data storage requirements.
  - It is intended to be an easy alternative to traditional on-premises instances of the same database.
  - Automatic backups and patching are performed during customer-defined maintenance windows.
  - Scaling, replication, and availability are a click away.

- **AWS Lambda**

  - What it does: Lets you run code without managing servers. Lambda automatically scales to handle thousands of requests per second.
  - What it is: Run serverless functions, such as processing API requests, interacting with RDS databases, without maintaining a server.

- **Amazon API Gateway**

  - What it does: Provides an API to connect applications to back-end services like Lambda.
  - What it does: Create and manage RESTful or WebSocket APIs that allow users or applications to call Lambda functions over HTTP/HTTPS. API Gateway provides security, monitoring, and access control.

- **Amazon Cognito**

  - What it does: Provides user authentication, login management, and access rights for mobile and web applications.
  - What it does: Manage users and authenticate users in applications, protect APIs by integrating authentication with API Gateway, ensuring only logged-in users can access resources.

#### AWS Service Deployment and Configuration Steps:

You will practice creating AWS services and connecting them together, thereby creating a complete system. You will understand the deployment process, from creating AWS services to integrating them into a seamless operating system.

- Create VPC and security group
- Create and configure Amazon RDS for database.
- Create EC2 to connect and add data to RDS instance
- Build Lambda functions and connect to RDS.
- Create an API Gateway and integrate with Lambda to handle requests from users.
- Create a user pool and authenticate with Amazon Cognito.
- Configure API Gateway security via Cognito, ensuring only authenticated users can call the API.
