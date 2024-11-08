# Description
Figure out how they moved the flag.

# Solution
Upon downloading the file its a format called 'pcapng' and to open it online was hectic ( they be asking for money ) 
So we go to open source software called wireshark. 

upon opening the file there is a lot going on and there is something called TFTP going on which is also the name of the challenge

Filtering out TFTPs we end up with only a few file namely
-instructions.txt, plan, program.deb, picture1.bmp, picture2.bmp, and picture3.bmp

We open each file 
## Instruction.txt 
has gibberish text , prolly would have to decode it . 
Using online decorder tools applying caesershift doesnt do anything but ROT13 does 

`TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN`
Is the decoded text 
Roughly even tho its hard to read it says that TFTP doesnt encrpyt traffiuc it misguides it and in the end says check back for the plan 

## Opening Plan file 
```
VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF
```
Again something gibberish we decode it using ROT13 to get 

```
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
```
in the end it says due dilegence and checkout the photos so we check the photos 

## Checking out the photos 
HOW DO I DO BMP PHOTOS ANALYSIS 
googling it  and youtube and reddit there is something called steghide something steganography program that is able to hide data in various kinds of image- and audio-files . ( from the official site ) 
( will use this for that moonwalk laters hehe ) 

need to use steghide now  dowload it via 
``` 
 apt install steghide
```
Its ask for password
123 doesnt work 
Hide with -DUEDILENGENCE 
so it should be the password . 

using that as password we open up the images 
the image analysis the last image has the flag 
image analysis using 
```
kafka@Kafka:~$ steghide extract -sf picture1.bmp -p DUEDILIGENCE
steghide: could not extract any data with that passphrase!
kafka@Kafka:~$ steghide extract -sf picture2.bmp -p DUEDILIGENCE
steghide: could not extract any data with that passphrase!
kafka@Kafka:~$ steghide extract -sf picture3.bmp -p DUEDILIGENCE
wrote extracted data to "flag.txt".
kafka@Kafka:~$ cat flag.txt
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

The flag is 
>picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}


## Upadating with more images from wireshark and stighide

![image](https://github.com/user-attachments/assets/2caae0c5-46f1-4015-a1a9-393c62234d4e)
The intial window of wireshark ... 

![image](https://github.com/user-attachments/assets/6a4dd661-3ed7-440f-b45b-9a86f4f80883)

on the right side of the file we see that 
![image](https://github.com/user-attachments/assets/deea54de-9ffc-43e6-84d3-dff3a6bd667b)

files like instructions.txt, plan, program.deb exists ...


