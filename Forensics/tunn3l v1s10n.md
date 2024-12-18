# tunn3l v1s10n
![image](https://github.com/user-attachments/assets/7f3695f2-02e6-4acf-a067-5f0d54cc1a45)

# Solution
Using exiftool to get metadata tells that it is bmp file , a bit image file . 
![image](https://github.com/user-attachments/assets/23ec3a9b-a669-46ec-ac83-24a9af93fb9b)

Trying to open it via hexdump / gimp or getting steghide info didnt do anything . 
Changing the file to .jpg /png using online tool also didnt help.  
Using Hex editor to open the file 

![image](https://github.com/user-attachments/assets/9f338312-cd77-444b-91d1-6131f9500ac4)

As the header showed BA D meaning that could be a hint , building on it and reasearching about bit map  a bit more ( pun ?)
Standard bmp hex data would look like this : 

in place of Ba d0 it should have been something else, reasarching bit more ( again pun ) 

![image](https://github.com/user-attachments/assets/3ceb5485-6f16-406c-a01c-995a7e7c7b07)

Using hex editor to edit the hexcode of the image 
![image](https://github.com/user-attachments/assets/418f221a-1f97-4f20-853d-3b270d27f48c) 
saving it and opening it again to see this : 
![image](https://github.com/user-attachments/assets/2bbbb5de-419e-4bb1-a729-4f0733fe7a1a)

i made a mistake there and only changed a part of the hex and not the ba d0 ( the second one ) so doing that
 
![image](https://github.com/user-attachments/assets/371cc514-8add-431a-9531-3ed6b4591a01)
 would reveal 
![image](https://github.com/user-attachments/assets/3752580c-c486-4128-a951-37c0b47505dd)

as this image and the one before suggest that these are part of images and we need to know the whole bytes of the image to display the whole image . 

Working on that the second row of the hex would justify the height so playing with it 

![image](https://github.com/user-attachments/assets/9fd9d264-d434-40e7-bde7-98e2c95e21a8) 

To make it 
![image](https://github.com/user-attachments/assets/d236112e-ea89-46e8-abc3-2e7111ecb6f4)

would reveal the image as : 
![image](https://github.com/user-attachments/assets/473ff395-a874-44c4-873e-59c037ef83e5)

The flag is : 
>picoCTF{qu1t3_a_v13w_2020}
