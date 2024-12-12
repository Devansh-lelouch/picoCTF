# Scan Surprise

Just create an instance of it and then scan the QR to get the flag.

# Secrets of Polygot 
Looked like a simple change the extension but simply changing the name to png would do it. 
![flag2of2-final](https://github.com/user-attachments/assets/fe5bf44e-1a57-4e98-be09-efd7219b6ab8) + the flag part in the pdf.

# Can you see 
The image given is a weird AI generated image not much , as its says web solvable we open it in the pico webshell.
open the image link with `wget` in the browser shell unzip the folder and use exiftool ( tool to analyze the images, you will get a metadata ) 
this looks like base64 so the flag is `picoCTF{ME74D47A_HIDD3N_deca06fb}`
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fZGVjYTA2ZmJ9Cg==
