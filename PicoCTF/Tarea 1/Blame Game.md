Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/73/challenge.zip)

Hints:
1. In collaborative projects, many users can make many changes. How can you see the changes within one file?
2. Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
3. You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.

## Solución 1:
Revisamos el log y buscamos alguno que contenga el formato de la flag
Encontramos que la flag es un autor
```
┌──(yair㉿Yair)-[~/drop-in]
└─$ git log | grep picoCTF{
Author: picoCTF{@sk_th3_1nt3rn_e9957ce1} <ops@picoctf.com>
```