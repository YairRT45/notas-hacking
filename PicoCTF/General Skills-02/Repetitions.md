Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/474/enc_flag).

Hints:
1. Multiple decoding is always good.
## Solución 1:
Con pipes y decode de base 64
```
YagooRT-picoctf@webshell:~$ base64 --decode enc_flag | base64 --decode | base64 --decode | base64 --decode | base64 --decode | base64 --decode
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_3f81f7be}
```