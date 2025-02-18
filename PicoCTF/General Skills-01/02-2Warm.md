Can you convert the number 42 (base 10) to binary (base 2)?

Hints:
1. Submit your answer in our competition's flag format. For example, if your answer was '11111', you would submit 'picoCTF{11111}' as the flag.

## Solución 1:
Con cyberChef
```
Input: 42

Recipe: From decimal, to binary

Outpout: 101010

picoCTF{101010}
```

## Solución 2 
Con python
```
YagooRT-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)[2:]
'101010'

picoCTF{101010}
```