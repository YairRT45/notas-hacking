I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

Hints:
1. None

## Solución 1:
Generamos un script de python usando pwntools
```
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())

data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')

data = data.decode('ascii') 
data= unbits(data) 

print(data)
----------------------------------------------------------------
Al ejecutarlo nos da el siguiente resultado, donde encontramos la flag:
┌──(kali㉿kali)-[~/Documents/forensic/whitepages]
└─$ python exp.py
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'

picoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}

```