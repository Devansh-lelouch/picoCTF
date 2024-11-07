# Description

Who doesn't love cookies? Try to figure out the best one. http://mercury.picoctf.net:17781/

The web portal looks like-
![image](https://github.com/user-attachments/assets/bbf1a0da-4e59-442d-9e26-e889213b99f2)

Passing the `snickerdoodle` as the cookie , we see that nothing happens. 
It shows that - 
![image](https://github.com/user-attachments/assets/c9f84539-cf40-45fc-a35c-dc1aa8cbcc3e)

Checking the cookie tab on the application section of the developers tools 
We see something like 
![image](https://github.com/user-attachments/assets/ee880aef-478e-450a-bbbf-06f777bfc839)

With nothing else coming to my mind i tried entering random cookie names. 
-Choco gives an msg in red `Enter valid cookie` and the  value on the cookie tab becomes -1. 
-Googling cookie names and entering shortbread,gingerbread gives value of 4 and 23 respectively in the value section.
-Noticed that the name of cookie for it to give a positive value has to be in small letters with no spaces.
-Figured out that we can also just input value and the name of cookie would change if we refresh ( downloading auto refresh)
-With auto refresh changing the values from 1 to 23 ( cuz 23 was the what i got at gingerbread) started from the backwards 
-Got the flag at value 18
-Could have written a code to do that, but that would have taken long time and the value was smaller if it didnt happen 
after a long time there was no choice but to figure out some kinda code ?

![image](https://github.com/user-attachments/assets/4f450809-12fb-4905-8ce8-980749593117)

The flag is -
>>picoCTF{3v3ry1_l0v3s_c00k135_bb3b3535}
