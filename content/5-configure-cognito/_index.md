+++
title = "Configure Cognito"
date = 2024
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

### Overview of AWS Cognito

**AWS Cognito** is an identity management and user authentication service from Amazon Web Services (AWS). This service allows you to create secure web and mobile applications with user authentication, authorization, and login with multiple options such as user account, Social login or login via Identity Provider.

#### Cognito Features

- Register & Authenticate users using username/pw/email or social network account.
- Authorize users to applications or resources
- Verify email/phone number.
- Integrate with other services (API Gateway, Lambda) to build applications.
- Support for mobile applications (iOS, Android) through SDK
- Cognito sync: sync data between mobile devices
- Advanced Security: monitor & analyze user access to detect and prevent unusual access (optional).

#### Cognito Pricing

**Cognito** pricing is based on:

- Number of Monthly Active Users. For example, in Singapore, it is $0.0055/MAU (the higher the cheaper)
- User sign in via SAML or OIDC: $0.015/MAU
- Advance Security feature: $0.05/MAU if enabled
- SMS in case of sending MFA messages: Depends on the region.

#### Cognito's limitations

- Number of Users per user pool: 40M (contact AWS if you want to increase)
- Maximum number of user pools: default 1,000, max 10,000
- Custom attribute: 50
- **Limitations on Admin API call frequency, e.g.:**
  - UserCreation: 50 RPS. Increase by 10RPS for every 1 million MAUs
  - AdminUserRead: 120 RPS. Increase 40 RPS for every 1 million MAU
  - RevokeToken: 120 RPS. Increase 40 RPS for every 1 million MAU
  - UserUpdate: 25 RPS cannot be increased.

**Note on Cognito's token verification mechanism**

- **JWT tokens** issued by Cognito will normally use client side verification (using the Public Key provided by Cognito. **_Note that AWS does not provide Cognito's private key)_**.
- This means that if the user logs out, the access-token is still valid until it expires
  (eg 30 minutes).
- If the system needs to revoke the issued access-token when the user has actions such as changing password, logging out, it cannot be done with Cognito. Of course, it is possible to workaround using Caching/DB techniques.

### Content

1. [Create user pool](1-create-user-pool)
2. [Create user & group cognito](2-create-group-cognito)
