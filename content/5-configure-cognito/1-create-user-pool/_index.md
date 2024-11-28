+++
title = "Create User Pool"
date = 2024
weight = 1
chapter = false
pre = "<b>5.1 </b>"
+++

#### Create User pool

1. In the Console interface:
   Search for keyword: **Cognito**
   ![Search Cognito](/images/5/5_1/1.png?width=90pc)

2. Select User pools on the left menu
   Click **Create user pool**
   ![Click Create user pool](/images/5/5_1/2.png?width=90pc)

3. Select User name, Email

- Check **Allow users to sign in with a preferred user name**
- Click **Next**
  ![Select User name](/images/5/5_1/3.png?width=90pc)

4. Select **Cognito defaults** for Password policy
   ![Select Cognito defaults](/images/5/5_1/4.png?width=90pc)

5. Scroll down, select **No MFA** for Multi-factor authentication

- Select **Email only** for Delivery method
- Click **Next**
  ![Delivery methodChoose Cognito defaults](/images/5/5_1/5.png?width=90pc)

6. Leave **_default_** options

- Scroll down to the **Additional required attributes** section: Select **name**
- Click **Next**
  ![Additional required attributes](/images/5/5_1/6.png?width=90pc)

7. Select **Send email with Cognito**

- Click **Next**
  ![Send email with Cognito](/images/5/5_1/7.png?width=90pc)

8. In the **SMS** configuration section:

- Select **Create a new IAM role**
- IAM role name: `cognito-sms-role`
- Click **Next**
  ![Configuration sms](/images/5/5_1/8.png?width=90pc)

9. Create **User pool**

   - Enter a name for the user pool, for example: `test-lamda-pool-01`
   - Select **Use the Cognito Hosted UI**
   - Domain: Select **Use a Cognito domain**
   - Enter a domain, for example: **https://test-fcj-cloud**
     ![Create User pool](/images/5/5_1/9.png?width=90pc)
     ![Create User pool](/images/5/5_1/10.png?width=90pc)

10. Create **App Client**

    - Select **Public client**
    - Enter a name for the app client, for example: `test-change-data-rds`
      ![Create App Client](/images/5/5_1/11.png?width=90pc)

11. At **Advanced app client settings**

- Select **ALLOW_USER_PASSWORD_AUTH**
- Select **ALLOW_USER_SRP_AUTHSRP**
- Select **ALLOW_CUSTOM_AUTH**
  ![Advanced app client settings](/images/5/5_1/12.png?width=90pc)
  ![Advanced app client settings](/images/5/5_1/13.png?width=90pc)
  Then select **Next**, Select **Create user pool**
