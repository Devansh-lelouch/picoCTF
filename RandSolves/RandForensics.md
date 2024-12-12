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




