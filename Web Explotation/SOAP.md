# Challenge 
![{CBF1A1C4-FCCD-442C-AC6B-3EA91BE5DCFB}](https://github.com/user-attachments/assets/0b73a273-574e-46bb-9208-dc8a1c161962)


# Solution
Since i dont know much about XML/ XXE watching a video on it.

Opening the Web portal and inpecting : 

![image](https://github.com/user-attachments/assets/c2d48871-1448-4e1e-a410-fcccd1c9939e)

The Special info changes with when we press the buttons other than that there is no function of UI.
Going for the source code , i only notice the xml payload 

![image](https://github.com/user-attachments/assets/c63d4e92-5557-4aa4-96f3-ceefdadfc6d9) 

Also got to know that 
![image](https://github.com/user-attachments/assets/b795bdd4-c73a-4ea6-8b64-6844c078cd51)

So the challenge name makes sense .

researching more on how to do XML injection, and using Burp suite to do so. Since I didnt know about burp suite i had to watch a couple of videos to get it right, links of which are in the refrences in the last. 

Opening the link in Burp's browser with intercept off and then clicking on any details of the webpage and turing intercept on

![image](https://github.com/user-attachments/assets/d56743e4-8af7-4534-a8fb-be69f00ba95f)

Selecting the code to send it to the repeater and turning the intercet off

![image](https://github.com/user-attachments/assets/8d57d24e-c029-4fb4-b9eb-b56cc0ac5a00)


The repeater window looks like this .

![image](https://github.com/user-attachments/assets/44f553a0-86c6-4c54-a341-245f736b8da4)

We have to give this code in the request,This is a pretty standard code in such attacks 

```
<!DOCTYPE test[
<!ENTITY name SYSTEM "file:///etc/passwd>
]>
```

Sending the request would fetch us a response : 

![image](https://github.com/user-attachments/assets/7a67cffb-c6e2-4744-a3d4-04a8175477cf)

The flag is 
>picoCTF{XML_3xtern@l_3nt1t1ty_540f4f1e}

>Refrence Videos :

>https://youtu.be/QiNLNDSLuJY?si=qPyksBMKJmqtf_hq

>https://www.youtube.com/watch?v=xwcPgeEFnuM

>https://youtu.be/gjm6VHZa_8s?si=VoAlixK9E8jU0O21
