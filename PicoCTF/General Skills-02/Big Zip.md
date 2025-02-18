Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/503/big-zip-files.zip)

Hints:
1. Can grep be instructed to look at every file in a directory and its subdirectories?

## Solución 1:
Con grep recursivo:
```
YagooRT-picoctf@webshell:~$ grep -r pico big-zip-files
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}

picoCTF{gr3p_15_m4g1c_ef8790dc}
```