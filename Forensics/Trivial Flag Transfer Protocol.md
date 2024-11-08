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
``
