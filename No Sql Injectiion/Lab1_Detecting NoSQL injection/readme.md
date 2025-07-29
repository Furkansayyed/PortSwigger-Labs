# Lab: Detecting NoSQL injection

## The product category filter for this lab is powered by a MongoDB NoSQL database. It is vulnerable to NoSQL injection. 

### Here we know the applicatio is running on mongodb as database, now I will start my Burpsuite Proxy and see the responses for different endpoints

-> Here's the webpage we have to inject NOSQL Injection,
![webpage](../screenshots/image.png)

-> Now I will Accessories and intercept the request and send it repeater
![intercepted request](../screenshots/image-1.png)

-> Now in Repeater I will try to get the error message using the parameter like:

```bash
"
'
{
}
```

I used ' and it worked
![alt text](../screenshots/image-2.png)

### Now as we do in SQL Injection we have to use boolean conditions to reveal the hidden products

```bash
' && 1 ==1
' && '1' == '1
' || 1 || '
```

###  I used **' || 1 || '** and worked and Solved my First No Sql Injection LAB
![alt text](../screenshots/image-3.png)