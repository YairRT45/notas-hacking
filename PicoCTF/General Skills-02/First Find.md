Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/502/files.zip)

Hints:
None
## Solución 1:
Con grep recursivo
```
YagooRT-picoctf@webshell:~$ grep -r picoCTF files
files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt:picoCTF{f1nd_15_f457_ab443fd1}

picoCTF{f1nd_15_f457_ab443fd1}
```