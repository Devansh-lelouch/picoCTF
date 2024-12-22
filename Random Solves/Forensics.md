# Scan Surprise [E]

Just create an instance of it and then scan the QR to get the flag.

# Secrets of Polygot [E]
Looked like a simple change the extension but simply changing the name to png would do it. 
![flag2of2-final](https://github.com/user-attachments/assets/fe5bf44e-1a57-4e98-be09-efd7219b6ab8) + the flag part in the pdf.

# Can you see [E]
The image given is a weird AI generated image not much , as its says web solvable we open it in the pico webshell.
open the image link with `wget` in the browser shell unzip the folder and use exiftool ( tool to analyze the images, you will get a metadata ) 
this looks like base64 so the flag is `picoCTF{ME74D47A_HIDD3N_deca06fb}`
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==

# Information [E]
Same as the one above

# Glory of the Garden[E]
This one makes you use hex editor . 
JFIF in the start means its a jpeg file and way at the end there is the flag.

# Sleuthkit Apprentice [M]
This time the file format is .gz so we are using the `gzip -d disk.flag.img.gz` to dezip it in the webshell or `gunzip`
When we use `file` to get the type of data we realize it has partitions so we use whats called `mmls` command  from the " The sleuth Kit " which displays it in a better format.

The fls command is used to list files and directories within a specific partition. In this case, the -o option specifies the offset (0000360448) of the Linux partition found earlier using mmls.

then use icat because we want to exctract directrly from the node , cat just reads and displays.
finallys the flag is 
> picoCTF{by73_5urf3r_3497ae6b}

# So Meta [M]
We are given a png file and have to retrieve the flag , we use something called exiftool which gives the metadata of the image, as the name suggests the file is there. 

>picoCTF{s0_m3ta_d8944929}

# Shark on the wire 1
![image](https://github.com/user-attachments/assets/fa7160e7-c431-443f-b4c2-24595451b1de)

## Solution 
This is a pcap  file so we have to use wiresharks , here we have tcp and udp protocals and we are given the hint of streams so 
![image](https://github.com/user-attachments/assets/01c15db6-b6fa-4c61-acf2-aa4af6bba490)

Now searching the streams by increasing the streams 

![image](https://github.com/user-attachments/assets/063dd699-8218-411a-92a9-0b771a40dd32)
![image](https://github.com/user-attachments/assets/1a8f03fa-a4a9-4454-b4db-c0d6b1c717c4)

>picoCTF{StaT31355_636f6e6e}

#Web Net 0 [H]
![image](https://github.com/user-attachments/assets/c1f6198a-e896-4ad3-a38c-3c7e21da69e4)

## Solution
The challenge had pcap file and a key file , opening the pcap in wireshark showed me bunch of random things 
I understood that we have to use the key, and found out that there is a preference tab on whireshark where rsa key can be uploaded . 
When i uploaded it and reloaded the wireshark, the earlier encrypted TCP became https 
Filtering all https and checking each one of them revealed the flag to me . 

![image](https://github.com/user-attachments/assets/a24aa271-fde3-4656-bd21-02cb6f87127e)

the flag is : 
>picoCTF{nongshim.shrimp.crackers}
