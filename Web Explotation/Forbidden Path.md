# Challenge
We know that the website files live in /usr/share/nginx/html/ and the flag is at /flag.txt but the website is filtering absolute file paths.
Can you get past the filter to read the flag?

# Solution
We create the instance which leads us to the website like this 

![image](https://github.com/user-attachments/assets/d41ef9fb-7dd4-481d-8094-f26c7866af48)


- The website filters out absolute paths , so we have to use relative paths. 
- The file we wanna access is flag.txt 
- ..

divine-comedy.txt

oliver-twist.txt

the-happy-prince.txt

Are the folders before  we can reach the root directory , `../` is used to go to the previous directory and we have to go to root directory to access flag.

- `../../../../flag.txt` would do that

# Flag

>>picoCTF{7h3_p47h_70_5ucc355_6db46514}
![image](https://github.com/user-attachments/assets/107dcdd7-e10f-4ef8-b1e9-ededb13789e2)
