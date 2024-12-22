# picobrowser

![image](https://github.com/user-attachments/assets/f0ea157f-9753-4cd0-90aa-e42a866faaf0)

## Solution 
The Instance webstie 
![image](https://github.com/user-attachments/assets/269745be-b65d-4af1-a55e-ce335971f283)

As the Error message says, we have to fool the website into thinking that we are using picobrowser and not any other browser . 
I googled to check how does the website find which broswer we are using and got this stackexhange , which says something about `user agent specification`
which basically tells the website about the broswer.

[stack exhange](https://superuser.com/questions/1365300/tricking-website-that-you-are-using-different-browser-or-os)

Building on that and researching how to change the `user agen specification` led me to this tutorial 
[Change user agent ](https://www.browserstack.com/guide/change-user-agent-in-chrome)

Following it, Opening the network conditioning 
![image](https://github.com/user-attachments/assets/15465da6-457d-4ea2-82d9-32aa8c630241)

Changing the browser to picobrowser 

![image](https://github.com/user-attachments/assets/7d6fd156-5f90-4f81-ac9e-f26650b4a91b)

Reloading the website to get the flag as : 
![image](https://github.com/user-attachments/assets/3d656ad9-b89f-4920-8c48-032d42d333f6)

>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865
