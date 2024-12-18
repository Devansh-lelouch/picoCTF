# GDB Baby Steps 1
![image](https://github.com/user-attachments/assets/66e6cbd9-63d3-45fc-9b7d-3e2bc9999483)

## Solution 
As I had no clue whats going on , I first watched  this youtube video on intro to debugging via gdb to understand about gdb and debugging 
https://www.youtube.com/watch?v=Tmdnsre9z7s

Coming back to the challenge since its a GDB challenge , we open it in via gdb `gdb debugger0_a` . We know that `main` is the function we have to work on , so getting to know all the functions via `info functions` 

```
Undefined command: "eax".  Try "help".
(gdb) info function
All defined functions:

Non-debugging symbols:
0x0000000000001000  _init
0x0000000000001030  __cxa_finalize@plt
0x0000000000001040  _start
0x0000000000001070  deregister_tm_clones
0x00000000000010a0  register_tm_clones
0x00000000000010e0  __do_global_dtors_aux
0x0000000000001120  frame_dummy
0x0000000000001129  main
0x0000000000001140  __libc_csu_init
0x00000000000011b0  __libc_csu_fini
0x00000000000011b8  _fini
(gdb)
```

eax is in main function looking into main function with `dissamble main` to get : 
```
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.

```
We see that the hexademical is `0x86342` converting hexademical to decimal via online tools to get the flag as : 
>picoCTF{549698}


# ARMssembly 1

![image](https://github.com/user-attachments/assets/86418dd0-c436-4698-ba42-ce851aa394a5)

## Solution 

Since i dont know anything about ARM I google to find out that its a low level langague dealing with assembly code. 
Opening the file in VS code, 

![image](https://github.com/user-attachments/assets/005981a3-9ac8-43a6-a04e-c541714eb226)

No clue whats going on here , so using ChatGPT to understand the code. 
Understand the code : 
``` 
func:
	sub	sp, sp, #32
``` 
`sub` means subtract and `sp` means stack pointer , `#32` is the number of bytes . More context : 
> Stack pointer is a register that stores memory adress on itself . Register is a memory built on CPU that stores and manipulates Data

The syntax of a function like sub would be 
`sub <destination>, <source1>, <source2>` where 
>destination: The register where the result of the subtraction is stored.
>source1: The value (or register) from which the second operand is subtracted.
>source2: The value (or register/immediate) to subtract from the first operand.

so `sub sp, sp, #32` subtracts 32 bytes from `sp` and points to `sp` which is lower by 32 bytes then it was originally.
Looking further 
```
str	w0, [sp, 12]
mov	w0, 85
str	w0, [sp, 16]
mov	w0, 6

```

`str w0, [sp,12]` here means that store the value of sp+12 in the w0 register. str is for store sp,12 is 12 bytes away from the stack pointer. 

`mov w0, 85` move the value 85 into w0. 
similar code follows till 
```
ldr	w1, [sp, 16]
lsl	w0, w1, w0
``` 
Load the value from memory at the address sp + 16 into register w1. ldr is for load 
Logical shift left (LSL) moves the binary bits of the value in w1 to the left by the number of positions specified in w0. The empty positions on the right are filled with 0s.

now making sense of the whole function command : ( Look the comments ) 

![image](https://github.com/user-attachments/assets/5222cc7d-116e-4d6f-ab46-3afd60bef820)

Looking in the main function 

![image](https://github.com/user-attachments/assets/cabad4d6-e708-41a8-a0f0-d8fce92b8161)

Solving it ,
w0 = 0 
1813 - x = 0 
x = 1813 

convert 1813 into hexadecimal and putting it in flag format to get flag as : 
>picoCTF{00000715}


