To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.

Hints:
1. I hear python can convert things.
2. It might help to have multiple windows open.

## Solución 1:
Usando Cyberchef:
```
YagooRT-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
socket
Please give the 01110011 01101111 01100011 01101011 01100101 01110100 as a word.
...
you have 45 seconds.....

#Cyberchef
#Input: 01110011 01101111 01100011 01101011 01100101 01110100
#Recipe: From binary
#Output: socket

Input:
socket
Please give me the  155 141 160 as a word.

#Cyberchef
#Input: 155 141 160
#Recipe: From octal
#Output: map

Input:
map
Please give me the 616e696d6174696f6e as a word.

#Cyberchef
#Input: 616e696d6174696f6e
#Recipe: From hex
#Output: animation

Input:
animation 
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}

picoCTF{learning_about_converting_values_02167de8}
```