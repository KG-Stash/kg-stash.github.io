+++
title = "Check API with Postman"
date = 2024
weight = 2
chapter = false
pre = "<b>4.2 </b>"
+++

**Postman** is currently one of the most popular tools used in testing APIs.

As we know, API is responsible for connecting applications together, having Postman will make working with this API easier. Normally, Postman will be used for REST API. With Postman, we can call Rest API without writing any code.

Download [Postman](https://www.postman.com/downloads/).

#### Test API with Postman

Click on the **+** ,sign to add a new tab

- Select POST method
- Enter **InvokURL** of the POST API recorded from the previous step
- Enter **RequestBody** in **raw** format:

```
{
"method": "GET"
}
```

- Press **Send** button

The returned result is all the processed data of the User table

![Test API](/images/4/4_2/1.png?width=90pc)
