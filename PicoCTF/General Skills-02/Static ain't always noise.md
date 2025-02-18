Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/static)? This [BASH script](https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/ltdis.sh) might help!

Hints:
1. None

## Solución 1:
Ejecutando el script y aplicando un grep
```
YagooRT-picoctf@webshell:~$ bash ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt

YagooRT-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico 
   1020 picoCTF{d15a5m_t34s3r_6f8c8200}

```