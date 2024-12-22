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


# findme
![image](https://github.com/user-attachments/assets/4335a0dd-dd20-49ff-b9d9-ceb5939872fa)

## Solution 
Opening the instance website 
![image](https://github.com/user-attachments/assets/fae9f6ad-b6b0-4b34-8b23-a5ad9493937c)

Putting in the username and password as test would lead to this webpage 
![image](https://github.com/user-attachments/assets/ea85b37b-2081-40a1-aaab-5e9da1613ae1)

Also since the hint is redirections i tried opening the Robots.txt for the website but that lead me back to the same page.
![image](https://github.com/user-attachments/assets/362efcd3-f9c1-4a4b-a8d6-1a4184a9c8c6)

opening burp suite in its own broswer now 
![image](https://github.com/user-attachments/assets/289f5a90-cdcb-40c7-9be8-f9d62ea01d63)

Loging via burp , forwarding the request would result in 

![image](https://github.com/user-attachments/assets/81160c5c-cf40-43bc-8636-947cd3822918)

Forwarding it to the repeater so i can inspect and try more things 

![image](https://github.com/user-attachments/assets/37fbe80e-dc3e-4507-95cd-63f54edcb2a9)

I could see the first part of the flag here and the second part in the response as a html comment 
![image](https://github.com/user-attachments/assets/a1149249-6fb4-43da-a2ad-c19a36142751)

The flag would be 
picoCTF{proxies_all_the_way_25bbae9a}
