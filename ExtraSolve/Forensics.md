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

# Very Very Very hidden 
![image](https://github.com/user-attachments/assets/76bda7e6-0f16-422a-8d0d-bfef7575b3e6)

# Solution
A pcap file was given so opened up with wireshark . 
I saw lot of tcp , quic , tslv 
Filtered out the http to get 

![image](https://github.com/user-attachments/assets/19757a75-7b3b-4a70-9dfe-596a1de4a776)

There was a evilduck and a normal duck  
Doing `file => Export object => HTTP` and saving all what we get from 
![image](https://github.com/user-attachments/assets/151043fe-3507-45f5-bb8a-dd82a433703b)

Opening the files 
![image](https://github.com/user-attachments/assets/04de84e4-89db-4a73-acf1-643d565d19f8)

The evil duck has more pixeleted image , clouds and oceans .

Nothing sus contains 
![image](https://github.com/user-attachments/assets/7f868fc8-eae9-4dfd-be7b-c86436d213f7)

Favicon is a ISO file. 

Trying exiftool,hex dump on the ducks but that didnt reveal anything. 
I also tried steghide on the ducks and stegosuite but couldnt find anything on it. 
![image](https://github.com/user-attachments/assets/5dedf360-586b-4a56-bdcc-6752ef0ec801)


I went back to the hint and looking back at the wireshark saw 
![image](https://github.com/user-attachments/assets/d91dcd0a-027f-4a0f-a173-af47cdd1d375)

I didnt know why powershell was here , after lot of here there i searched powershell decoder and wasting time there, got to 
powershell steganography  [here ](https://malware.news/t/powershell-steganography/41866) 

After reading the article and seeing the second hint i was sure this is what happened to evil ducks as well.
Now i had to get a tool to do that , i tried a 2 github repostitory and got one working [here](https://github.com/PCsXcetra/Decode_PS_Stego)

Viewing the evil duck would get us : 
![image](https://github.com/user-attachments/assets/194ee38e-b595-4637-9741-07d326c863a9)

I treid to check if that was a encoded data but it wasn't 
![image](https://github.com/user-attachments/assets/e0430343-1411-48d7-8522-22e56f3e001b)

I asked chatgpt what it is and it was a powershell script . 
![image](https://github.com/user-attachments/assets/13f944c5-1113-455d-a5b2-b57fd657d7a6)

Ran it in the powershell and got 
![image](https://github.com/user-attachments/assets/44610c8e-dbbf-476e-aabd-f71a0d9fc3a7)

Flag is 
>picoCTF{n1c3_job_f1nd1ng_th3_s3cr3t_in_the_im@g3} 

This challenge took me a long while to solve.
