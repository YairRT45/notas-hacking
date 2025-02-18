Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

Hints:
1. [strings](https://linux.die.net/man/1/strings)

## Solución 1:
Usando strings y grep:
```
YagooRT-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}
```