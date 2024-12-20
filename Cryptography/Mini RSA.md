# Challenge 
![image](https://github.com/user-attachments/assets/ddba4dbf-6d2e-4a28-932a-7254c897a4d3)

#Solution 
Looking up RSA encrpytion , via the pico learn  
![image](https://github.com/user-attachments/assets/b6dca8ac-86da-45bc-aaf6-7d9c2d5841c3)

basically , we have two keys : public key and private key .
A public key is used for encyption and is of the form (n,e) and a private key is used for decryption and is of the form (n,d) 

n = p x q ( where p and q are large prime numbers ) 
and e is a number between 1 and (p-1)x(q-1) , d is a number such that e.d = 1 

The ciphertext is calculated using the formula : 
![image](https://github.com/user-attachments/assets/bc655c6c-1e9a-437a-b291-874d944521ea)

and the encrpted text is calculated using the formula : 
![image](https://github.com/user-attachments/assets/f0e40203-d4d1-418d-b6e5-0989dec1812b)

Now coming back to this challenge , 
we are given a text file containg the the values of n,e,c 
![image](https://github.com/user-attachments/assets/96c0b400-08a8-4e66-bf30-f7c40949a6f4)

Looking online for rsa tools didnt work, found a useful stack exhange which built a tool but got multiple python scripts which solves RSA, understanding and 
implimenting it , 
![image](https://github.com/user-attachments/assets/599e4d95-d10e-4e4d-9c47-373a51935dc1)

we get the flag as : 
>picoCTF{n33d_a_lArg3r_e_606ce004}'
