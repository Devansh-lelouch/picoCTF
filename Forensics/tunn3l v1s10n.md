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

![image](https://github.com/user-attachments/assets/0095a1f0-5b27-4629-b8e4-e8501b526978)

in place of Ba d0 it should have been something else, reasarching bit more ( again pun ) 

![image](https://github.com/user-attachments/assets/3ceb5485-6f16-406c-a01c-995a7e7c7b07)
