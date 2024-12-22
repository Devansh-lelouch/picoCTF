# WebNet1
![image](https://github.com/user-attachments/assets/5fa98dda-5471-430a-8dcf-5fe37e551aea)

## Solution 
Since I have already done WebNet0 [here](https://github.com/Devansh-lelouch/picoCTF/blob/main/Random%20Solves/Forensics.md#web-net-0-h) I had an idea of what was going on. 
Opening the .pcap file in Wireshark and editing the preference with the key provided would reveal the http requests.
The picopico file is a private key , prolly a rsa private key 

![image](https://github.com/user-attachments/assets/2f2677ec-25cd-4c42-ba84-11b4847624b3)


Edit-> preferences and uploading the flag file here .
![image](https://github.com/user-attachments/assets/4c9a532a-56bb-4e4d-abf6-63a339cf603f)

Filtering the http , would get us 
![image](https://github.com/user-attachments/assets/b6f17d57-f891-4872-9eeb-e4b1047f20d5)

But this time there is no flag there, and I saw `/vultures.jpg` and similar files in the lenght info . 

Inspecting them 
![image](https://github.com/user-attachments/assets/e86be7be-1ef2-462d-a37d-e4c5cd23b0a5)

I tried opening the url given here but that didnt open up anything 
I then tried to follow each stream and searching for pico 
![image](https://github.com/user-attachments/assets/79690f4b-6cc5-49bd-923c-8b31f64015d6)

I found this 
![image](https://github.com/user-attachments/assets/6159d5fa-847a-4b37-93a2-dc11c30f7f59)

The flag is :
>picoCTF{honey.roasted.peanuts}
