+++
title = "Testing API with Cognito"
date = 2024
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

### Check operation

**//Syntax**

```
https://<your user pool domain>/authorize?client_id=<your app client ID>&response_type=<code/token>&scope=<scopes to request>&redirect_uri=<your callback URL>
```

**Or the following syntax:**

```
https://<your user pool domain>/authorize?client_id=<your app client ID>&response_type=token&scope=openid&redirect_uri=https://google.com
```

1. Copy **Cognito domain**
   ![Copy Cognito domain](/images/6/1.png?width=90pc)

2. Copy **Client ID**
   ![Copy Client ID](/images/6/2.png?width=90pc)

3. Edit the syntax above to access cognito via the link.
   Use the **username and password** of the user created in cognito to log in.
   ![Access Cognito](/images/6/3.png?width=90pc)

4. Enter information to change change password:
   ![Go to Cognito](/images/6/4.png?width=90pc)

Then you rollback to the url **https://google.com with the token information**.
![Access Cognito](/images/6/5.png?width=90pc)

5. We copy to the editor to get the token
   ![Copy token](/images/6/6.png?width=90pc) 6. Learn about Token content
   ![data token](/images/6/7.png?width=90pc)

6. Return to API Gateway

- Go to the API Gateway created in the **API Gateway Deployment** section
- Select **Create an authorizer**
  ![Create an authorizer](/images/6/8.png?width=90pc)

8. Set up information for cognito authentication

- Authorizer name: `coginito-authorizer`
- Authorizer type : **Cognito**
- Cognito user pool: **test-lamda-pool-01**
  ![coginito-authorizer](/images/6/9.png?width=90pc)

- **Create authorizer**
  ![Create authorizer success](/images/6/10.png?width=90pc)

9. Return to resources
   Select the **POST** method. Current Authorization: **NONE**
   Select **Edit**
   ![Choose Edit Method POST](/images/6/11.png?width=90pc)

10. Edit method information

- Select the created Authorization: \* \*cognito-authorizer\*\*
- Select Save
  ![Edit Method POST](/images/6/12.png?width=90pc)

11. **Deploy** to run the method with the authorizer just assigned to the method
    ![Deploy API ](/images/6/13.png?width=90pc)

12. Now we copy **Invoke URL**
    ![Copy Invoke URL](/images/6/14.png?width=90pc)

13. Go to **postman** tool.

Click on the **+** sign, to add a new tab

- Select method **POST**
- Enter **InvokURL** of the POST API recorded from the previous step
- Enter RequestBody in raw form:

```
{ "method": "GET"
}
```

- Press the **Send** button

Result: **We get an authentication error (401 - Unauthorzierd)**
![Request API](/images/6/15.png ?width=90pc)

14. Highlight and copy **id_token** obtained from **_Step 6_**
    ![Request API](/images/6/16.png?width=90pc)

15. Go to ** Postman**

- Select **Authorization**
- Type: **Bearer Token**
- **Paste the copied id_token** into the token box on the right. Then Resend the request
- The result returns user information
  ![Request API](/images/6/17.png?width=90pc)

16. **Add new** user to database

- With Authorization: token pasted
- Result: New addition successful
  ![Create New User](/images/6/18.png?width=90pc)

17. Check User table via EC2 connected to RDS
    ![Check New User with EC2](/images/6/19.png?width=90pc)

18. Check the log in **Cloud Watch**
    ![Cloud Watch](/images/6/20.png?width=90pc)

! [Cloud Watch log](/images/6/21.png?width=90pc)
