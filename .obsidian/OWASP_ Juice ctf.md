
# Information
- CTF Name:  OWASP juice shop
- CTF Level: Easy
- CTF Description: This room uses the Juice Shop vulnerable web application to learn how to identify and exploit common web application vulnerabilities.
- Date: 9/24/2024
- Platform: Try Hack me
- Category: machine
- IP:  

# Findings
### Credentials
`FoundCREDs`
- Kali Linux (2016.2 >=) tools:
    - Burp Suite
    - dirb
    - sqlmap
- Google Account for challenges 28 & 34 (OAuth2.0)
- _search engine (Internet)_
## External
### Enumeration
- As usual scanning is the way to find info of what we test , so i have found the open port 80 
![[Pasted image 20240924143743.png]]

### Gaining Access
-  Next i Start Burp and set a proxy to 127.0.0.1, port 8080 (this is the Burp proxy). i usually use the FireFox Plug-In 'FoxyProxy Basic' to quickly switch on/off using a proxy. 
- I am assured that in order to forward and get the flag i've to turn the intercept mode.
- Now, forward that to the server!  

But why don't we put the 1=1?

Well, as the email address is valid (which will return true), we do not need to force it to be true. Thus we are able to use **'--** to bypass the login system. Note the **1=1** can be used when the email or username is not known or invalid. found in task 3 & 4.
![[Pasted image 20240924144651.png]]

- here are  the flags that are founded through burp forwarding
![[Pasted image 20240924144850.png]]
![[Pasted image 20240924155204.png]]
- To get the third flag we have to use intruder to brute force it, For the payload, we will be using the best1050.txt from Seclists. (Which can be installed via: **apt-get install seclists**)

Once the file is loaded into Burp, start the attack. You will want to filter for the request by status.
A failed request will receive a 401 Unauthorized 
Whereas a successful request will return a 200 OK. ![](https://i.imgur.com/q5jcfIA.png)

Once completed, login to the account with the password.  How ever with connection or other problems the status code on mine is 401 but i get it. lol 🤣
- ![[Pasted image 20240925111858.png]]



## Internal
### Enumeration
`$enum$`
we got in to Task 5:
Securing data transmission is crucial, but sometimes developers may unintentionally fail to do so properly. It's not that the developer deliberately set out to create a security issue—they may simply overlook a misconfiguration. However, we’re going to take advantage of that! Navigate to the "About Us" page, hover over the “Check out our boring terms of use…” link, and observe that it points to the /ftp/ directory.
![[Pasted image 20240925172944.png]]
- It is easy to download and even to login and get the flag, by downloading the aquisitions.md file we got one,Mr. Noodles with the some vowels changed to zeros. 
- Head back to the FTP page. Try to download the package.json.bak file but you will get a 403 error page because only .PDF and .MD can be downloaded. To get passed this, i use a character bypass called “Poison Null Byte” by using a URL Encoded Format which is a Null Terminator, by placing a NULL charater in the string,i am literally  telling the sever to terminate at the point given and the rest of the string is null. We will navigate to /ftp/package.json.bak%2500.md to receive this flag.
### Gaining Access
Admin pages manage site content, and Broken Access Control vulnerabilities fall into two types: Horizontal (accessing another user's data with the same permissions) and Vertical (accessing higher-level user actions).
In Firefox, open the Debugger (Ctrl+Shift+I), search for `path:administration` in `main-es2015.js`, revealing the `/#/administration` page.  admin credentials  are needed to access it.
Using Burp Suite, intercept a request from your basket, forward until `GET /rest/basket/1`, change `basket/1` to `basket/2`, and get the flag.
Then, go to `/#/administrator`, delete the 5-star review, and get another flag.

![[Pasted image 20240925143739.png]]

- Another flag gained by making xss attackes by pasting this code to the search bar
```
 <iframe src="javascript:alert(`xss`)"> 
```

![[Pasted image 20240925175131.png]]
### Maintaining Access

- i am trying to intercept with burpsuite by Opening the Headers tab where and adding the new header to True-Client-IP. Forward the request to the server. Sign back into the admin account and navigate to the Last Login IP page. We will get the XSS message again. Sending this header is similar to the X-Forwarded-For header, both tell the server what the IP of the client is.


![[Pasted image 20240925185702.png]]

- and i will add the header "_True-Client-IP_" and "_iframe src="javascript:alert(`xss`)""

![[Pasted image 20240925185440.png]]

Task 8:

This last flag is easy, head to /#/score-board and this will give you the last flag. However, this does show you the scoreboard with more optional to find items.
# Random Notes

- I have done the OWASP challenge and learn  a lot from it!!