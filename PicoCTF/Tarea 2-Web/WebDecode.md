Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:57555/) to find the flag

Hints:
1. Use the web inspector on other files included by the web page.
2. The flag may or may not be encoded

## Solución 1:
Sí vemos las 3 páginas vemos que en el index y en contact que siga buscando, pero en about me dice que intente revisarla que la puedo encontrar, al entrar no se observa nada relacionado, pero se puede observar un valor que posiblemente este cifrado
```
<section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9">

Y al intentar descifrarlo con CyberChef
Input: cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9
Recipe: From Base64
Output: picoCTF{web_succ3ssfully_d3c0ded_283e62fe}
```