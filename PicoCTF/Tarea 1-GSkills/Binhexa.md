How well can you perfom basic binary operations?
Start searching for the flag here `nc titan.picoctf.net 60635`

Hints: 
1. None


## Solución 1:
Respondiendo las cuestiones
```
┌──(yair㉿Yair)-[~]
└─$ nc titan.picoctf.net 60635

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01111110
Binary Number 2: 11100100


Question 1/6:
Operation 1: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111110
Correct!

Question 2/6:
Operation 2: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0111000000111000
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01100101
Incorrect. Try again
Enter the binary result: 01100100
Correct!

Question 4/6:
Operation 4: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 101100010
Correct!

Question 5/6:
Operation 5: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01110010
Correct!

Question 6/6:
Operation 6: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 11111100
Correct!

Enter the results of the last operation in hexadecimal: fc

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_aeaf4b09}
```