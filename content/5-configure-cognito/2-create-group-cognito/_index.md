+++
title = "Create User And Group Cognito"
date = 2024
weight = 2
chapter = false
pre = "<b>5.2 </b>"
+++

#### Create users and groups for Cognito

1. After successfully creating **user pool**, go to the user pool information: **test-lambda-pool-01**

- In the **Users** tab. Select **Create Users**
  ![Users](/images/5/5_2/1.png?width=90pc)

2. In the user information section

- Create an account including **username, email and password**
  ![Info Users](/images/5/5_2/2.png?width=90pc)

3. Select **Create User**
   Then **cognito** will send the username and password when the user is registered.
   ![Mail info](/images/5/5_2/3.png?width=90pc)

4. Go back to the pool to create a group

- Select Create group
  ![Back user pool](/images/5/5_2/4.png?width=90pc)

5. In the group information section

- Enter the group name, such as: `admin`
- Scroll down and select **Create Group**
  ![Create Group](/images/5/5_2/5.png?width=90pc)

- After successfully creating the user and group
- Go to Group: **admin**
- Select **Add user to group**
  ![Add user to group](/images/5/5_2/6.png?width=90pc)

6. Select the user just created
   Click **Add**
   ![Add user to group](/images/5/5_2/7.png?width=90pc)
   ![Add user success](/images/5/5_2/8.png?width=90pc)
