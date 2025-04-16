Can you win in a convincing manner against this chess bot? He won't go easy on you!You can find the challenge [here](http://verbal-sleep.picoctf.net:61344/).

Hints:
1. Try understanding the code and how the websocket client is interacting with the server

## Solución:
Si revisamos el código vemos que sus respuestas se basan en los valores de 'eval' y 'mate', mate hace referencia a nuestro comportamiento y eval al de el, si asignamos un valor negativo a eval por medio de la consola, como:
```
sendMessage("eval -1000000")

Nos da la flag al sentirse derrotado:
Huh???? How can I be losing this badly... I resign... here's your flag: picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_a2a9bbe9}
```