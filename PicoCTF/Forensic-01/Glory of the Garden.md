This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

Hints:
1. What is a hex editor?

## Solución 1:
Si le realizamos un strings a la imagen y filtramos con grep para encontrar la flaj:
```
┌──(kali㉿kali)-[~/Downloads]
└─$ strings garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y33dd2eEF5}"

```