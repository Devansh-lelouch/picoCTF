
# Description
Decode this message from the moon.
The message is an audio file in the format .wav


# Solution

It felt like a very high frequency beeping listening to which was very annoying . 
My first thought process was could it be Morse code just high pitched and fast ? 
So i used online morse code adaptive to check if there is some morse code associated with it . The morse code decoder in the start showed 
` EE E E KNE` which makes no sense 
So i slowed down the audio and checked it again. 
Again got a gibberish message 
Also tried looking at the graph plotted by the audio msg via the morse code decorder 
And visualising the audio file with online tool  with no avail.

There are two hints for the solution. 
### First Hint
How did pictures from the moon landing get sent back to Earth? 

The hint makes me think if they sent it though some kind of analog signal or radio which got converted in digital but it was 1960s so hard, googling the hint
there were three possible ways , through radio signals , camera feed via satelleite TVs and the last method was SSTV format via radio telescopes.

Looking more into SSTV
`
SSTV, or Slow-scan Television, is a method of transmitting and receiving static pictures over radio waves. It's primarily used by amateur radio operators, and is different from regular television in a few ways:
Picture transmission
SSTV sends one picture very slowly, whereas regular television sends 24 or 30 pictures per second.
Bandwidth
SSTV uses a narrow bandwidth, meaning it uses less of the radio spectrum than regular television.
Transmission
SSTV transmits a picture by turning it into sounds that represent the color and brightness of each line in the picture. These sounds can then be transmitted over the radio and decoded by others.
`

so we need to use sstv converter to get our flag 

[Long ass tutorial makes you download aton](https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04) Tells us how to convert SSTV audio to image

Downloading all the packages and running QSSTV 
![image](https://github.com/user-attachments/assets/f7366372-320e-484f-b58e-93f76994d090)

Completing all the steps from the above tutorial and opening the message.wav file via 
```
kafka@Kafka:/mnt/c/Users/devdi/Downloads$ paplay -d virtual-cable msg.wav
```
![image](https://github.com/user-attachments/assets/a93b3e5c-a100-4de7-b271-208de5ad9ff7)

I was getting the image but only half of the image was getting through it , coming to the second hint 

![image](https://github.com/user-attachments/assets/1b4540a0-ca1b-4313-a830-8b79bd21b08a)

Googling the mascot , its Scotty so selecting Scottie 1 as the mode and doing the previous step again to get : 
![image](https://github.com/user-attachments/assets/0e2f9933-0d8b-4cb4-9143-9406d55b9e99)

>picoCTF{beep_boop_im_in_space}
